# Showcase film

`vertexnova-showcase.mp4` is a 44-second silent 1080p reel for interviewers and the org profile.

## Shot list

| # | Still | Source |
|---|-------|--------|
| 00 | Title | Generated |
| 01 | Volume isosurface | iPad Metal sample |
| 02 | Volume DVR (Phong) | iPad Metal sample |
| 03 | Volume slicer (MPR) | iPad Metal sample |
| 04 | Mixed CSG | iPhone Metal sample |
| 05 | A-buffer OIT | iPad Metal sample |
| 06 | Mesh picking | iPhone Metal sample |
| 07–13 | Primitive, materials, points, lines, text, AA, desktop volume | `vnegfx/samples/*/diagrams/` |
| 14 | End card | Generated |

## Rebuild

Requires `ffmpeg` and Python Pillow.

```bash
# After replacing stills, re-run the encode from this folder:
# scale each still to 1920x1080, 2.5–3s, fade, concat → vertexnova-showcase.mp4
```

Keep UI chrome in the iOS shots. It shows Metal, iOS, and the sample controls (isovalue, CSG subtract, OIT, picking).
