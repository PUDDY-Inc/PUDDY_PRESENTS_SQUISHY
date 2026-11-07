# PUDDY PRESENTS: SQUISHY 1.1.0

PUDDY PRESENTS: SQUISHY converts HEIC photos. A HEIC or HEIF photo converts to JPG, PNG or PDF in the browser, free and with no account, at https://squishy.puddystudios.com.

Release date: 2026-11-07.

## What is new

- HEIC and HEIF in; JPG, PNG or PDF out. Both modes apply: TO A SIZE looks for the closest fit under the target, and MAX QUALITY converts with no target.
- Many photos at once. Drop a batch and every photo is converted, each keeps its name with the new extension, and the batch comes back in one ZIP.
- A file that holds several images: JPG and PNG take its main image, and PDF takes all of them, one page each.
- The photo is turned the way it was taken, and a Display P3 photo is converted to sRGB, the web's standard colour space.
- The location and the camera's other Exif data are left out of the new file. The page says so when a photo is loaded.
- Where a browser limits a picture's size, a larger photo is converted at the largest size it allows, and the page says so. In Chrome on a Mac a 48 megapixel photo converts at full size.
- The decoder: for a HEIC photo, SQUISHY serves none. The page reads the HEIF file itself and hands each picture to the browser's HEIC decoder or, through WebCodecs, to the HEVC decoder of the device, and a browser with neither says so.
- The link card: the page declares one preview image, so a shared link shows one whole card.

## Not in this release

- Converting to HEIC is not in this release.

## Verified

- On 67 synthetic HEIC files made on the box, the page's reader under node, with a stand-in for the browser's decoder, gave every file at its size, turned all eight orientations as drawn, converted Display P3 to sRGB within 2 levels, kept alpha, and gave all four images of a file that holds four.
- In two browser engines on the box, one reading HEIC itself and one through WebCodecs, on the same 67 files: every file clean on its size, orientation, colour, alpha and page checks; one photo to JPG, PNG and PDF, 50 photos to one ZIP, and a 48 megapixel photo at full size; no location or camera data in any output.

## Credits

THE MASTER CUBE, PUDDY✵ARCHITECT, PUDDY✵SQUISHY, Colton Dempsey 𓅇 ([@cubedivisiondev](https://github.com/cubedivisiondev))
