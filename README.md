# HSDL Image Feed

Custom Torizon OS image for automation.

## Feed URL for Easy Installer

```
https://YOUR_USERNAME.github.io/YOUR_REPO/image_list.json
```

Replace `YOUR_USERNAME` and `YOUR_REPO` with your GitHub username and repository name.

## Quick Start

### For New Images/Upgrades

1. **Build and publish**:
   ```bash
   cd scripts
   ./build-menu.sh
   # Choose option 2 (Build + Publish to AWS S3)
   ```

2. **Commit feed to GitHub**:
   ```bash
   git add image_list.json
   git commit -m "Update feed with new image version"
   git push
   ```

3. **Easy Installer will see the update** (after GitHub Pages rebuilds)

### Initial Setup

See `scripts/QUICK_START.md` for complete setup instructions.

## Architecture

This feed uses a hybrid approach:

- **GitHub Pages**: Serves `image_list.json` (small metadata file)
- **AWS S3**: Hosts all actual image files (large files, no redirects)

### File Flow

```
Easy Installer
    ↓
GitHub Pages: image_list.json
    ↓ (contains S3 URL)
S3: image.json
    ↓ (contains S3 URLs for all files)
S3: All Tezi files
```

## Repository Structure

- `image_list.json` - Feed file pointing to S3-hosted images
- `scripts/` - Build and deployment scripts
- All actual image files are hosted on AWS S3

## Setup Guides

- **GitHub Pages Setup**: See `scripts/GITHUB_PAGES_SETUP.md`
- **AWS S3 Setup**: See `scripts/AWS_S3_SETUP.md`
- **Quick Start**: See `scripts/QUICK_START.md`

## Benefits

✅ **No redirect issues**: Direct S3 URLs (solves GitHub Releases problem)  
✅ **Small repository**: Only metadata files in GitHub  
✅ **Fast updates**: Update feed without re-uploading large files  
✅ **Scalable**: Easy to add multiple images  
✅ **Free**: GitHub Pages is free for public repos
