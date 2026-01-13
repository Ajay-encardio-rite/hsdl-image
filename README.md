# HSDL Image Feed

Custom Torizon OS image for automation.

## Feed URL for Easy Installer

```
https://ajay-encardio-rite.github.io/hsdl-image/image_list.json
```

## Usage

1. Open Toradex Easy Installer on your device
2. Press **Feeds (f)**
3. Add the feed URL above
4. Press **Refresh (r)**
5. Select and install the image

## Repository Structure

- `image_list.json` - Feed file for Easy Installer
- `HSDL_ZMQ_ZERO_TOUCH/` - Image directory containing:
  - `image.json` - Image metadata
  - `imx-boot` - Bootloader
  - Other installation files

## GitHub Pages Setup

This repository is configured to serve files via GitHub Pages from the root directory.

- **Branch**: `main`
- **Folder**: `/` (root)
- **URL**: `https://ajay-encardio-rite.github.io/hsdl-image/`
