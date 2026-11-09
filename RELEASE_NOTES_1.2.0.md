# PUDDY PRESENTS: SQUISHY 1.2.0

PUDDY PRESENTS: SQUISHY compresses and converts video and audio with your browser's own codecs, and GIF with its own code. A video or audio job downloads nothing and nothing is uploaded, free and with no account, at https://squishy.puddystudios.com.

Release date: 2026-11-09.

## What is new

- Video and audio on the browser's own codecs, GIF by SQUISHY's own reader and writer. SQUISHY reads and writes MP4, MOV, M4A, WebM and MKV itself, and hands every picture and every sound to the browser's own decoders and encoders. No video or audio codec is downloaded or served.
- Any video the browser plays. A video in a container SQUISHY does not read is decoded by the browser's own player, in real time. Where the browser can read neither, the page says so plainly.
- Video to GIF and GIF to video, by SQUISHY's own GIF reader and writer. A GIF from a clip takes one palette chosen for the whole clip and steps down in size until it fits the target.
- HEIC photos open on a target of twice the photo's size. MAX QUALITY converts with no size limit, one click away.
- Video comes out as H.264 in MP4, MOV or MKV, or as VP9 where the browser has no H.264 encoder. Audio comes out as M4A (AAC), or as WEBM (Opus) where the browser's AAC encoder cannot make the file, and the result says which. Where neither encoder can make a video's sound, the video is saved without it, and the result says so.
- Once the page is open, video, audio, GIF-to-video and video-to-GIF jobs run with no connection.
- Nothing of a video's or a sound's own metadata (the location, the camera, the tags) is written to the output.

## Changed in this release

- MP3 output is retired: no browser writes MP3. An MP3, WAV or FLAC kept as SAME is saved as M4A, which plays everywhere.

## Verified

- Under node, SQUISHY's MP4, MOV, M4A, MKV and WebM writers carried the real H.264, VP9 and AAC samples of the test kit's seven video and audio files into 19 outputs, and an independent decoder read every frame of every output with no error, at the source's frame count and duration. Each output carried no metadata box. The GIF writer and reader agreed pixel for pixel, and a MOV's AAC was written in QuickTime's own form. 36 of 36 checks.
- Under node, with a stand-in for the browser's codecs, every job path ran: video to MP4, MOV and MKV to a target and at MAX QUALITY, the floor and the trim, an encoder that overshoots its bitrate, an encoder that will not go below its own floor, no H.264 encoder, no AAC encoder, GIF to video, audio to M4A and WebM, video to GIF, CANCEL mid-job and a decoder error, and the two browsers' own behaviour as the test runs found it: an H.264 setting that takes frames and never emits, an AAC description in another form, AAC frames with their headers on, and an AAC encoder that refuses a low bitrate. Every result at or under its target, and no job waits forever. 33 of 33.
- In two browser engines, on the test kit's 34 files and 71 jobs, every output read back by SQUISHY's own reader and by the browser's own player, and no metadata carried:
  - Chrome 156, headless: 71 of 71 jobs, 64 passed, 0 failed, 7 noted (the seven jobs of one AVI file the browser cannot read, each ending with the page's own message).
  - WebKit 605.1.15 on macOS 27, in MASTER✵CUBE's WKWebView test runner: 71 of 71 jobs, 56 passed, 0 failed, 15 noted (the same seven AVI jobs, and eight MKV outputs that WebKit's player does not play, each read whole by SQUISHY's own reader, the page telling the visitor so).

Chrome is a trademark of Google LLC. macOS is a trademark of Apple Inc., registered in the U.S. and other countries and regions. PUDDY Inc. is not affiliated with Google LLC or Apple Inc.

## Credits

Founder/CEO - Colton Dempsey ([@cubedivisiondev](https://github.com/cubedivisiondev)), MASTER✵CUBE, PUDDY✵ARCHITECT, PUDDY✵SQUISHY
