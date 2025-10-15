![Inter Mono](https://github.com/lujstn/inter-mono/raw/main/gh_cover.jpg)

# Inter Mono

A monospace variation of [Iosevka](https://github.com/be5invis/Iosevka), designed to match [Inter](https://rsms.me/inter/) and Apple's SF font series.

## Download

| Format       | Description                            | Download                                                                        |
| ------------ | -------------------------------------- | ------------------------------------------------------------------------------- |
| **TTF**      | Desktop fonts (install on your system) | [Download Latest Release](https://github.com/lujstn/inter-mono/releases/latest) |
| **WOFF2**    | Web fonts for websites                 | [Download Latest Release](https://github.com/lujstn/inter-mono/releases/latest) |
| **Complete** | All formats included                   | [Download Latest Release](https://github.com/lujstn/inter-mono/releases/latest) |

## Features

- **6 Weights**: Light, Regular, Medium, SemiBold, Bold, ExtraBold
- **2 Styles**: Upright and Oblique (italic)
- **12 Total Fonts**: Complete weight and style combinations
- **Optimized Spacing**: Tightened character spacing for improved readability
- **Enhanced Punctuation**: Weight-dependent colon sizing
- **Monospace**: Fixed-width for perfect code alignment

![Comparison](https://github.com/lujstn/inter-mono/raw/main/gh_comparison.jpg)

## Installation

### macOS

1. Download the TTF package from [releases](https://github.com/lujstn/inter-mono/releases/latest)
2. Unzip the archive
3. Open the `TTF` folder
4. Select all `.ttf` files and double-click to install
5. Or drag them to Font Book

### Windows

1. Download the TTF package from [releases](https://github.com/lujstn/inter-mono/releases/latest)
2. Unzip the archive
3. Open the `TTF` folder
4. Select all `.ttf` files
5. Right-click and select "Install for all users" (recommended)

### Linux

```bash
# Download and extract
unzip InterMono-TTF-*.zip

# Install fonts
mkdir -p ~/.local/share/fonts/InterMono
cp TTF/*.ttf ~/.local/share/fonts/InterMono/

# Refresh font cache
fc-cache -f -v
```

## Usage in Editors

### VS Code

Add to your `settings.json`:

```json
{
	"editor.fontFamily": "'Inter Mono', monospace",
	"editor.fontSize": 14,
	"editor.lineHeight": 1.6
}
```

### Terminal Apps

- **iTerm2**: Preferences → Profiles → Text → Font → Inter Mono
- **Hyper**: Edit `.hyper.js` and set `fontFamily: 'Inter Mono'`
- **Terminal.app**: Preferences → Profiles → Font → Change → Inter Mono
- **Windows Terminal**: Settings → Profiles → Appearance → Font face → Inter Mono

### JetBrains IDEs

1. Preferences → Editor → Font
2. Select "Inter Mono" from the font dropdown
3. Adjust size as needed (recommended: 13-14pt)

## Web Fonts

Include in your CSS:

```css
@import url("path/to/inter-mono.css");

code,
pre {
	font-family: "Inter Mono", monospace;
}
```

Or self-host the WOFF2 files:

```css
@font-face {
	font-family: "Inter Mono";
	src: url("InterMono-Regular.woff2") format("woff2");
	font-weight: 400;
	font-style: normal;
}
```

## Building from Source

Inter Mono is built using Iosevka's build system with custom parameters.

### Prerequisites

- Node.js ≥ 18.0.0
- `ttfautohint` (for hinting)

### Build Steps

```bash
# Clone the repository
git clone https://github.com/lujstn/inter-mono.git
cd inter-mono

# Install dependencies
npm install

# Build all formats (TTF + WOFF2)
npm run build -- contents::InterMono

# Or build specific formats
npm run build -- ttf::InterMono        # TTF only
npm run build -- webfont::InterMono    # WOFF2 + CSS only
```

Fonts will be output to `dist/InterMono/`

### Customization

The build configuration is in `private-build-plans.toml`. Key customization points:

- **Character variants**: Adjust glyph shapes (zero, four, g, etc.)
- **Weight parameters**: Fine-tune stroke weights in `params/private-parameters.toml`
- **Spacing**: Modify character width and sidebearings

See [Iosevka's customization guide](https://github.com/be5invis/Iosevka/blob/main/doc/custom-build.md) for detailed options.

## Technical Details

- **Base**: Iosevka 33.3.1
- **Character Width**: 629 units (1% tighter than default)
- **Spacing Mode**: `fontconfig-mono` (strict monospace)
- **Serifs**: Sans-serif throughout
- **Ligatures**: Disabled (pure monospace)
- **Special Adjustments**:
    - Colon punctuation scaled by weight (1.05-1.25×)
    - ExtraBold stroke enhancement (1.05× multiplier)
    - Reduced colon side bearing (1px)

## Weights

| Weight    | CSS Value | Shape Value | Use Case                     |
| --------- | --------- | ----------- | ---------------------------- |
| Light     | 300       | 300         | Large displays, minimal text |
| Regular   | 400       | 400         | General coding, default      |
| Medium    | 500       | 520         | Emphasis, headings           |
| SemiBold  | 600       | 660         | Strong emphasis              |
| Bold      | 700       | 825         | High contrast, accessibility |
| ExtraBold | 800       | 1000        | Maximum impact, large sizes  |

## Contributing

Inter Mono is a custom Iosevka build. Contributions are welcome!

- Report issues: [GitHub Issues](https://github.com/lujstn/inter-mono/issues)
- Submit PRs for build configuration improvements
- Share your editor configurations

## License

Inter Mono inherits Iosevka's license:

- **Font**: [SIL Open Font License 1.1](https://github.com/be5invis/Iosevka/blob/main/LICENSE.md)
- **Build Scripts**: MIT License

## Credits

- **eeelbrens**: [eeelbrens](https://github.com/eeelbrens) - for writing the original [custom Iosevka script](https://github.com/rsms/inter/issues/128#issuecomment-2816578686) 🙇
- **Iosevka**: [Belleve Invis](https://github.com/be5invis/Iosevka) - Base font system
- **Inter**: [Rasmus Andersson](https://rsms.me/inter/) - Design inspiration
- **SF Mono**: Apple - Additional design reference

---

Made with ❤️ by [lujstn](https://github.com/lujstn)
