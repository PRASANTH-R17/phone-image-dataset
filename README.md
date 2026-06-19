# Phone Image Dataset

A public dataset of mobile phones and their images, sourced from
[gadgets.beebom.com](https://gadgets.beebom.com).

## Contents

- `devices.json` — one entry per device with:
  - `slug` — URL-safe identifier (e.g. `acer-super-zx-8gb-128gb`)
  - `name` — human-readable device name
  - `local_image` — path to the device image in this repo
    (e.g. `images/acer-super-zx-8gb-128gb.png`)
  - `brand` — normalized brand slug (e.g. `acer`)
- `images/` — device images (~1,633 PNG files), one per device, named by slug.

`devices.json` also contains a `meta` block with the dataset generation
timestamp and counts.

## Source

Data and images are sourced from
[gadgets.beebom.com](https://gadgets.beebom.com). This repository contains
the cleaned public dataset.
