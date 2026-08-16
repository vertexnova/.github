# Diagrams

Draw.io source for the VertexNova organization profile architecture diagram.

The profile README embeds `architecture.svg`. Edit `architecture.drawio`, then re-export the SVG.

## Export to SVG

### Option 1: draw.io Desktop

If [draw.io Desktop](https://github.com/jgraph/drawio-desktop/releases) is installed:

```bash
drawio -x -f svg -o architecture.svg architecture.drawio
```

### Option 2: draw.io Web

1. Open [app.diagrams.net](https://app.diagrams.net)
2. File → Open from → Device → `architecture.drawio`
3. File → Export as → SVG
4. Save as `architecture.svg` in this folder

## Files

| Source | Output | Used in | Contents |
|--------|--------|---------|----------|
| architecture.drawio | architecture.svg | profile README | Textbook engine stack: OS → Graphics APIs → Core → Visualization → Platform → RHI → Renderer → Domain (future) → Application |

Layers are stacked only. There are no arrows. Orange stroke marks private modules (`vnerhi`, `vnegfx`). Dotted stroke marks future work (`vnerobot`, `vneai`, `vnexr`).
