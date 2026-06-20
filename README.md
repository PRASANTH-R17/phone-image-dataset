# Phone Image Dataset

A public dataset of mobile phones and their images.

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

## Access via GitHub Pages

The dataset is published with GitHub Pages and can be loaded directly over HTTPS.

- Base URL: `https://prasanth-r17.github.io/phone-image-dataset/`
- JSON: `https://prasanth-r17.github.io/phone-image-dataset/devices.json`
- Images: `https://prasanth-r17.github.io/phone-image-dataset/images/<slug>.png`
  (e.g. `https://prasanth-r17.github.io/phone-image-dataset/images/acer-acerone-liquid-s272e4.png`)
- Raw fallback: `https://raw.githubusercontent.com/PRASANTH-R17/phone-image-dataset/master/devices.json`

The JSON is served with `Content-Type: application/json` and
`Access-Control-Allow-Origin: *`, so it can be fetched directly from a browser.
Pages caches responses for about 10 minutes (`Cache-Control: max-age=600`).

### Examples

Browser / JavaScript:

```js
const res = await fetch('https://prasanth-r17.github.io/phone-image-dataset/devices.json');
const data = await res.json();
console.log(data.meta, data.devices.length);
```

Python:

```python
import requests

data = requests.get('https://prasanth-r17.github.io/phone-image-dataset/devices.json').json()
print(data['meta'], len(data['devices']))
```

curl:

```bash
curl -s https://prasanth-r17.github.io/phone-image-dataset/devices.json
```
