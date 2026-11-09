# PUDDY PRESENTS: SQUISHY - Compress to the File Size You Name

PUDDY PRESENTS: SQUISHY - Compress to the File Size You Name. It compresses a file to a target size you name, in the browser. It is free and needs no account.

This repository holds SQUISHY's public release record: the release notes, the press release and the security contact. The tool runs at https://squishy.puddystudios.com. SQUISHY's source code is not part of this repository.

## What it does

- SQUISHY has two modes. TO A SIZE looks for the closest fit under the target. MAX QUALITY is a conversion with no target.
- Sizes are decimal: 1 MB is 1,000,000 bytes.
- A HEIC photo opens on a target of twice the photo's size, with MAX QUALITY one click away.
- SQUISHY installs as a web app. Its service worker keeps the page's own files in the browser's Cache Storage.
- Video and audio run on the browser's own codecs, and GIF to video and video to GIF on SQUISHY's own GIF reader and writer. These jobs, HEIC photos, and image or SVG jobs with JPG, PNG, WEBP or SVG output load no engine.

## Formats

| kind | in | out |
|---|---|---|
| Images | JPG, PNG, WEBP, BMP | JPG, PNG, WEBP, PDF |
| HEIC photos | HEIC, HEIF, one or many at once | JPG, PNG, PDF |
| GIF | GIF | GIF, MP4, MOV, MKV |
| Video | MP4, MOV, MKV and WEBM, and any other video the browser plays | MP4, MOV, MKV, GIF |
| Audio | MP3, WAV, M4A, FLAC, and any other audio the browser plays | M4A, WEBM |
| PDF | PDF | PDF, JPG, PNG, WEBP |
| SVG | SVG | SVG, PNG, JPG, WEBP, PDF |

## Privacy

- The file is never uploaded. The work runs on the device, and the file stays in the browser tab. No call in SQUISHY's code sends a file.
- SQUISHY's page files, app.js, heic.js, media.js, index.html and sw.js, and the site script puddy-tools.js use no cookie, localStorage, sessionStorage or IndexedDB.
- The service worker keeps SQUISHY's own site files, from its own origin, in the browser's Cache Storage.
- Nothing of a file's own metadata (a photo's location and Exif data, a video's or a sound's location, camera and tags) is written to the output.
- A GIF kept as a GIF, a PDF that comes in, and an image or SVG job with PDF output fetch their engine from cdn.jsdelivr.net, which receives the request and never the file, as the table below gives it. Every other job loads nothing.

## The engines

The three engines below are not part of this repository. Each loads from cdn.jsdelivr.net into the browser when a job needs it.

| engine | version | declared licence | loaded when |
|---|---|---|---|
| gifsicle-wasm-browser | 1.5.19 | MIT | a GIF is kept as a GIF |
| pdfjs-dist | 3.11.174 | Apache-2.0 | a PDF comes in |
| pdf-lib | 1.17.1 | MIT | the output is PDF, from an image, an SVG or a PDF |

The declared licence is the one each package declares for itself, read from its own package file on 2026-11-04. The gifsicle-wasm-browser package carries the gifsicle program, which its author offers under the GNU General Public License, version 2 only, or under an alternative licence stated in its README.

Video, audio, GIF to video, video to GIF and HEIC photos use the browser's own codecs and SQUISHY's own code (media.js and heic.js, served by the site). No codec is downloaded or served for them.

## Known limits

- A PDF is rebuilt from page images, so its text is no longer selectable.
- PDF to image takes the first 20 pages.
- Video to GIF takes the first 30 seconds.
- Large files are bounded by the device's memory.
- TIFF is not supported.
- MP3 is not written, since no browser writes MP3: audio comes out as M4A (AAC), or as WEBM (Opus) where the browser's AAC encoder cannot make the file.
- A video in a container SQUISHY does not read (AVI, for one) converts only where the browser plays it, in real time; elsewhere the page says so.
- An MKV plays in other video players, but not in every browser; the page says so where it does not.
- An SVG that carries text, styles or scripts is returned unchanged, and the page says so when the target cannot be reached.
- At a very small target a video or a sound is shortened to fit, and the result names the trim.
- A GIF kept as a GIF, a PDF that comes in, and an image or SVG job with PDF output need a connection to fetch their engine.

## This repository

| file | what it holds |
|---|---|
| `README.md` | what SQUISHY is, its formats, its privacy position, its engines and its limits |
| `RELEASE_NOTES_1.2.0.md` | the notes of release 1.2.0 |
| `RELEASE_NOTES_1.1.0.md` | the notes of release 1.1.0 |
| `RELEASE_NOTES_1.0.2.md` | the notes of release 1.0.2 |
| `RELEASE_NOTES_1.0.1.md` | the notes of release 1.0.1 |
| `PRESS_RELEASE_2026-11-05.md` | the press release of November 5, 2026 |
| `SECURITY.md` | the security contact |

## Contact

SQUISHY is a tool by Puddy Studios, PUDDY Inc. (https://puddystudios.com).

- Press: hello@puddystudios.com
- Security: see `SECURITY.md`

## Credits

Founder/CEO - Colton Dempsey ([@cubedivisiondev](https://github.com/cubedivisiondev)), MASTER✵CUBE, PUDDY✵ARCHITECT, PUDDY✵SQUISHY
