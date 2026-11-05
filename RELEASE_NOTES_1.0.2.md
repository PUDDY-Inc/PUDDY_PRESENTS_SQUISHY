# PUDDY PRESENTS: SQUISHY 1.0.2

PUDDY PRESENTS: SQUISHY - Compress to the File Size You Name. It compresses a file to a target size you name, in the browser. It is free, needs no account, and runs at https://squishy.puddystudios.com.

Release date: 2026-11-05.

## How it works

- SQUISHY has two modes. TO A SIZE looks for the closest fit under the target. MAX QUALITY is a conversion with no target.
- Sizes are decimal: 1 MB is 1,000,000 bytes.
- SQUISHY installs as a web app. Its service worker keeps the page's own files in the browser's Cache Storage, and an image or SVG job with JPG, PNG, WEBP or SVG output loads no engine.

## Formats

| kind | in | out |
|---|---|---|
| Images | JPG, PNG, WEBP, BMP | JPG, PNG, WEBP, PDF |
| GIF | GIF | GIF, MP4, MOV, MKV |
| Video | MP4, MOV, MKV, AVI, WEBM and more | MP4, MOV, MKV, GIF |
| Audio | MP3, WAV, M4A, FLAC and more | MP3, M4A |
| PDF | PDF | PDF, JPG, PNG, WEBP |
| SVG | SVG | SVG, PNG, JPG, WEBP, PDF |

## Privacy

- The file is never uploaded. The work runs on the device, and the file stays in the browser tab. No call in SQUISHY's code sends a file.
- SQUISHY's page files, app.js, index.html and sw.js, and the site script puddy-tools.js use no cookie, localStorage, sessionStorage or IndexedDB.
- The service worker keeps SQUISHY's own site files, from its own origin, in the browser's Cache Storage.
- A GIF, video, audio or PDF job, and an image or SVG job with PDF output, fetches its engine from cdn.jsdelivr.net, which receives the request and never the file, as the table below gives it. An image or SVG job with JPG, PNG, WEBP or SVG output loads nothing.

## The engines

The four engines below are not part of this repository. Each loads from cdn.jsdelivr.net into the browser when a job needs it.

| engine | version | declared licence | loaded when |
|---|---|---|---|
| @ffmpeg/core | 0.12.10 | GPL-2.0-or-later | any video or audio job, a GIF to video, a video to GIF |
| gifsicle-wasm-browser | 1.5.19 | MIT | a GIF comes in |
| pdfjs-dist | 3.11.174 | Apache-2.0 | a PDF comes in |
| pdf-lib | 1.17.1 | MIT | the output is PDF |

The declared licence is the one each package declares for itself, read from its own package file on 2026-11-04. The gifsicle-wasm-browser package carries the gifsicle program, which its author offers under the GNU General Public License, version 2 only, or under an alternative licence stated in its README.

## Known limits

- A PDF is rebuilt from page images, so its text is no longer selectable.
- PDF to image takes the first 20 pages.
- Video to GIF takes the first 30 seconds.
- Large files are bounded by the device's memory.
- HEIC and TIFF are not supported.
- An SVG that carries text, styles or scripts is returned unchanged, and the page says so when the target cannot be reached.
- At a very small target a video is shortened to fit, and the result names the trim.
- A GIF, video, audio or PDF job, and an image or SVG job with PDF output, needs a connection to fetch its engine.

## This repository

This repository is SQUISHY's public release record. SQUISHY's source code is not part of it.

## Credits

THE MASTER CUBE, PUDDY✵SQUISHY, PUDDY✵MARKETING, Colton Dempsey 𓅇 ([@cubedivisiondev](https://github.com/cubedivisiondev))
