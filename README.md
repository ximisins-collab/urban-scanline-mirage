# 城市扫描线幻景

`urban-scanline-mirage` is a Codex skill for transforming city, street, façade, station, parking-area, and architectural photos into a calm rectilinear scanline collage.

## What it does

- Preserves a focal person or action unit as a crisp photographic anchor.
- Rebuilds the surrounding scene from source-derived rectangles, bars, sparse vertical anchors, and horizontal chromatic strata.
- Keeps sky, ground, architecture, foliage, and wet-surface areas at a consistent degree of stylization.
- Uses varied hue shifts, line pitch, streak widths, opacity, merging, fading, and interruptions so the material does not look like a uniform CRT overlay.

## Install

Copy this folder into your Codex skills directory:

```bash
git clone https://github.com/<your-github-username>/urban-scanline-mirage.git ~/.codex/skills/urban-scanline-mirage
```

Or download the repository as a ZIP and place the folder at:

```text
~/.codex/skills/urban-scanline-mirage
```

The skill is automatically discoverable by its name and can also be invoked explicitly as `$urban-scanline-mirage`.

## Usage

Provide a source photo and ask Codex to use `urban-scanline-mirage`. The image-generation sub-skill is required for edits, and the result should be inspected before delivery.

## License

MIT. See [LICENSE](LICENSE).
