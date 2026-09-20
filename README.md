# misc

Shared media for BUAA-CI-LAB project documentation: logos, images, and demo
videos that the READMEs and documentation sites reference.

This repository exists so that the project repositories stay free of binary
assets. Nothing here is source code.

## Layout

```
<project>/<asset>              brand assets, which do not change per release
<project>/<version>/<asset>    demo media recorded for one release
```

The top level is the project, because this repository is shared across projects
and a bare `logo.png` would eventually collide. The version directory applies
only to media that belongs to a release; logos and marks sit directly under the
project.

```
embodirun/logo.png
embodirun/mark.png
embodirun/favicon.png
embodirun/wordmark-source.png
embodirun/v0.1/multi_robot_serving.mp4
embodirun/v0.1/engine_e2e_contrast.mp4
```

| Project | Used by |
|---|---|
| `embodirun/` | EmbodiRun README and documentation site |
| `embodiinfer/` | EmbodiInfer README and documentation site |

## Referencing an asset

Use the raw URL for the default branch:

```
https://raw.githubusercontent.com/BUAA-CI-LAB/misc/main/embodirun/logo.png
```

Raw URLs serve byte ranges, so the same URL works as the source of a `<video>`
element:

```html
<video controls muted playsinline preload="metadata" width="720">
  <source src="https://raw.githubusercontent.com/BUAA-CI-LAB/misc/main/embodirun/v0.1/multi_robot_serving.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video>
```

`preload="metadata"` fetches only the file header, `playsinline` stops iOS from
forcing fullscreen, and `muted` is required if you ever add `autoplay`. Set an
explicit `width` so the layout does not shift while the video loads.

## Adding an asset

- Prefer SVG for logos and diagrams. This is still a Git repository, and text
  keeps diffs and history small.
- Compress video before committing it. H.264 at roughly 1.5 Mbit/s is enough for
  a screen recording. Do not commit GIFs: same content, many times the size.
- Name assets by content rather than by a number, so that re-cutting a video
  does not force a URL change.
- Keep the editable source next to the file derived from it, for example
  `wordmark-source.png` beside `logo.png`.

## Licensing

The licence in [LICENSE](LICENSE) covers the files in this repository. Project
names and logos remain marks of their respective projects and are not granted as
trademarks by that licence.
