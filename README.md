# exam-photo-kb-dimension-presets

Open JSON dataset of official photo and signature file-size (KB) and pixel dimension requirements (**GATE**, **NEET**, **JEE Main**, **SSC**, **TNPSC**, **US Visa 2x2**) for client-side image tools and form validators.

Live browser presets built on this specification are available at [CompressTo100KB](https://compressto100kb.com/), including dedicated tools for [GATE Photo Resizer](https://compressto100kb.com/gate-photo-resizer), [NEET Photo Resizer](https://compressto100kb.com/neet-photo-resizer), and [JEE Main Photo Resizer](https://compressto100kb.com/jee-main-photo-resizer).

> **Tip for video/webcam captures:** If you are capturing a clean passport or exam ID still from a recorded video clip, use [VidToImage](https://vidtoimage.com/) to extract a lossless PNG reference frame in-browser before resizing and KB compression.

## Official Photo & Signature Specifications (20 KB – 200 KB)

| Preset ID | Exam / Portal | Asset Type | File Size (KB) | Pixel Dimensions / Aspect Ratio | DPI | Head-Height / Notes |
| :--- | :--- | :--- | :--- | :--- | :--- | :--- |
| `gate_photo` | GATE (GOAPS) | Passport Photo | `5 KB – 200 KB` (recommended `20–150 KB`) | `480 x 640 px` min `240 x 320 px` (`3:4` / `3.5 x 4.5 cm`) | `200–300 DPI` | Face covers `60%–70%` of frame height; white background |
| `gate_signature` | GATE (GOAPS) | Signature | `5 KB – 200 KB` | `160 x 560 px` / `3.5 x 1.5 cm` | `200 DPI` | Black or dark blue ink on plain white paper |
| `neet_postcard` | NEET UG (NTA) | Postcard Photo | `10 KB – 200 KB` | `4 x 6 in` (`1200 x 1800 px` at 300 DPI) | `200–300 DPI` | `80%` face coverage; white background |
| `neet_passport` | NEET UG (NTA) | Passport Photo | `10 KB – 200 KB` | `3.5 x 4.5 cm` (`413 x 531 px`) | `200–300 DPI` | `80%` face coverage; ears clearly visible |
| `jee_main_photo` | JEE Main (NTA) | Passport Photo | `10 KB – 200 KB` | `3.5 x 4.5 cm` (`413 x 531 px`) | `200–300 DPI` | `80%` face coverage without mask; white background |
| `ssc_photo` | SSC (CGL / CHSL) | Passport Photo | `20 KB – 50 KB` | `3.5 x 4.5 cm` (`275 x 354 px` at 200 DPI) | `200 DPI` | `55%–65%` head height; JPEG format |
| `tnpsc_photo` | TNPSC | Passport Photo | `20 KB – 50 KB` | `3.5 x 4.5 cm` (`165 x 200 px` to `413 x 531 px`) | `200 DPI` | Name & date printed if specified by notification |
| `us_visa_2x2` | US Visa (DS-160) | Square Photo | `<= 240 KB` (target `50–180 KB`) | `600 x 600 px` to `1200 x 1200 px` (`1:1`, `2 x 2 in`) | `300 DPI` | Head height `50%–69%` of total image height |

## Sample JSON Preset Dataset

```json
{
  "schema_version": "1.0.0",
  "presets": [
    {
      "id": "gate_photo",
      "label": "GATE Passport Photograph",
      "format": "image/jpeg",
      "min_kb": 20,
      "max_kb": 200,
      "target_kb": 100,
      "width_px": 480,
      "height_px": 640,
      "aspect_ratio": "3:4",
      "dpi": 300,
      "head_height_pct": [60, 70]
    },
    {
      "id": "neet_passport",
      "label": "NEET UG Passport Photograph",
      "format": "image/jpeg",
      "min_kb": 10,
      "max_kb": 200,
      "target_kb": 100,
      "width_px": 413,
      "height_px": 531,
      "aspect_ratio": "7:9",
      "dpi": 300,
      "head_height_pct": [75, 85]
    },
    {
      "id": "jee_main_photo",
      "label": "JEE Main Photograph",
      "format": "image/jpeg",
      "min_kb": 10,
      "max_kb": 200,
      "target_kb": 95,
      "width_px": 413,
      "height_px": 531,
      "aspect_ratio": "7:9",
      "dpi": 300,
      "head_height_pct": [75, 85]
    },
    {
      "id": "ssc_photo",
      "label": "SSC Photo (20-50 KB)",
      "format": "image/jpeg",
      "min_kb": 20,
      "max_kb": 50,
      "target_kb": 40,
      "width_px": 275,
      "height_px": 354,
      "aspect_ratio": "7:9",
      "dpi": 200,
      "head_height_pct": [55, 65]
    },
    {
      "id": "tnpsc_photo",
      "label": "TNPSC Photo (20-50 KB)",
      "format": "image/jpeg",
      "min_kb": 20,
      "max_kb": 50,
      "target_kb": 40,
      "width_px": 350,
      "height_px": 450,
      "aspect_ratio": "7:9",
      "dpi": 200,
      "head_height_pct": [55, 70]
    },
    {
      "id": "us_visa_2x2",
      "label": "US Visa DS-160 (2x2 inch)",
      "format": "image/jpeg",
      "min_kb": 20,
      "max_kb": 240,
      "target_kb": 120,
      "width_px": 600,
      "height_px": 600,
      "aspect_ratio": "1:1",
      "dpi": 300,
      "head_height_pct": [50, 69]
    }
  ]
}
```

## License

Released under the [MIT License](./LICENSE).
