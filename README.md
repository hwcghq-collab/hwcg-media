# hwcg-media

Public image hosting for HWCG (Hot Wheels Car Guy Die-Cast Garage) social posts.

Direct raw URLs are meant for Buffer image assets when posting to X.

## Public URL pattern

`https://raw.githubusercontent.com/hwcghq-collab/hwcg-media/main/x-posts/<filename>.jpg`

Example:

`https://raw.githubusercontent.com/hwcghq-collab/hwcg-media/main/x-posts/2026-11-24-black-friday-carman.jpg`

## How new images get published

The GitHub file tools only accept text, so binaries are staged as base64 and decoded by Actions:

1. Write `staging/<filename>.jpg.b64` (plain base64 text of the image).
2. The **Decode staged images** workflow decodes it to `x-posts/<filename>.jpg`, removes the staging file, and pushes.
3. Use the raw.githubusercontent.com URL on the `main` branch (not a commit SHA).

Supported staging suffixes: `.jpg.b64`, `.jpeg.b64`, `.png.b64`, `.gif.b64`, `.webp.b64`.
