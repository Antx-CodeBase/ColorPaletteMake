# Changelog

All notable changes to ColorPaletteMake will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [1.0.0] - 2025-10-24

### Added

#### Core
- Initial release of ColorPaletteMake, an Inkscape extension for building color palettes.
- Interpolates between a start and end color, placing one shape per step along the ramp.
- Live preview panel with two stacked views: full palette (auto-fit, labels omitted) and detail view (first/middle/last card at readable size with labels, stroke, and shadow).
- Generated output grouped as `ColorPaletteMake-NNN` on the current layer, with per-card `<g>` wrappers so fill/stroke pairs move together.

#### Color Palette
- Two color modes: HSV and HSL.
- Three sub-tabs: Ramp Start, Ramp, and Ramp End.
- Step Mode: Increment (set per-card delta, count derived) or Count (set total steps, evenly sampled).
- Reverse Order option to flip the ramp direction.
- Hue interpolates along the shortest arc; saturation and value/lightness interpolate linearly.
- Live color swatch preview for start and end colors.

#### Shape Style
- Layout, size, gap, and per-shape settings.

#### Labels
- **Text on Shape**: HSV / HSL / RGB / Hex display, optional hex second line, size as a percentage of card height, label-every-Nth-card thinning, six font weights, auto-contrast label color, and X/Y offsets.
- **Custom**: multi-line free-form text with style (size, weight, color, auto-contrast), X/Y position nudges, and targeting (Palette placement or per-Shape).
- Middle-Out draw order relabels the X offset slider as "Push X" and fans labels outward from the center card.

#### Effects
- **Stroke**: color, width (px or % of card's short side), opacity, line cap, line join, miter limit, and dash presets (Solid, Dashed, Dotted, Dash-dot, Long dash) plus custom patterns. Applied with `paint-order: stroke fill`.
- **Shadow**: Drop shadow and Inner shadow modes, with Apply-to (per card or whole palette), offset X/Y, blur, color, and opacity. Switching modes flips offset signs for visual consistency.
- Stroke + inner shadow handling: fill and stroke emitted as separate elements, with the shadow applied only to the fill.

#### Transforms
- **Move**: offset X/Y with Palette / Uniform / Cascade modes.
- **Rotate**: angle in degrees with Palette / Uniform / Cascade modes.
- **Radial**: place cards on a circle with per-step angle, radius, center (Palette Center / Document Origin / First Card), and Rotate Cards option.
- **Skew**: horizontal and vertical angles with Palette / Uniform / Cascade modes.
- **Draw Order**: Newest on Top, Middle-Out, and Oldest On Top.

#### Settings
- Enable Dark Mode (applies on next dialog open).
- Saved Settings persisted to `color_palette_make.json` next to the extension, including all widget values, dark mode flag, and open tabs.
- Reset to Defaults button.

### Requirements
- Inkscape 1.4 or later.
- All dependencies ship with Inkscape's Python; no extra setup normally needed.

### Known Limitations
- Preview shadows are drawn as hard-edged solid copies for speed rather than being blurred.
- Full-palette preview omits labels by design to avoid clutter on dense palettes.

### Notes
- First public release. Started as a personal tool; issues and feature requests welcome, though turnaround times and PR acceptance are not guaranteed.

[1.0.0]: https://github.com/USER/ColorPaletteMake/releases/tag/v1.0.0
