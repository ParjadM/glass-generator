# Advanced Glassmorphism CSS Generator

A lightweight, browser-based tool to design and export modern Glassmorphism ("frosted glass") UI components. Tweak blur, transparency, borders, noise, shadows, shapes, gradients, and element types — then copy clean, ready‑to‑use CSS & HTML.

> Open `index.html` directly in any modern browser to use the generator. No build step required.

## ✨ Features
- Live visual preview with draggable glass card
- Element type switching: `div`, `button`, `section`, `form`
- Presets: Frosted Light, Vibrant Dark, Subtle Glow, Minimalist
- Adjustable: background opacity, blur, border radius, border color
- Advanced background modes: abstract shapes, solid color, gradient
- Box shadow fine‑tuning (X, Y, blur, spread, color)
- Optional noise overlay for subtle texture
- One‑click copy of generated CSS and HTML
- Tabbed code panel (CSS / HTML)
- Tailwind CSS (via CDN) + custom inline styles
- Fully self‑contained (no external build tooling)

## 📂 Project Structure
```
/ index.html           # Main app (UI + logic)
/ privacy-policy.html  # Privacy policy page
/ favicon.png          # App icon
/ README.md            # You are here
```

## 🚀 Getting Started
1. Clone or download this repository.
2. Open `index.html` in Chrome, Firefox, Edge, or Safari.
3. Adjust controls in the left panel.
4. Switch tabs to view CSS or HTML.
5. Click "Copy" to copy the generated code to your clipboard.
6. Paste the code into your project and (optionally) refine with your design system.

No server, package manager, or build step is required.

## 🧪 How It Works
The tool dynamically builds a style block using the chosen parameters:
- Background color is converted from HEX + opacity to `rgba()`.
- `backdrop-filter` and `-webkit-backdrop-filter` apply blur.
- A semi‑transparent border + box shadow create depth.
- Optional noise layer is injected as an overlay with an inline SVG texture.
- The glass element is always emitted under the `.glass-effect` class.

Example generated CSS (simplified):
```css
.glass-effect {
  background: rgba(255, 255, 255, 0.25);
  backdrop-filter: blur(12px);
  -webkit-backdrop-filter: blur(12px);
  border: 1px solid rgba(255, 255, 255, 0.18);
  border-radius: 24px;
  box-shadow: 0 8px 32px 0 rgba(0,0,0,0.37);
  padding: 1.5rem;
  color: #fff;
}
```

## 🖼 Background Modes
| Mode      | Description |
|-----------|-------------|
| Shapes    | Colorful blurred circles (abstract aesthetic) |
| Solid     | Single color fill (customizable) |
| Gradient  | Two‑stop linear gradient (top-right direction) |

## 🎛 Presets Overview
| Preset        | Style Notes |
|---------------|-------------|
| Frosted Light | Bright white glass, higher opacity, soft blur |
| Vibrant Dark  | Low-opacity black with noise for realism |
| Subtle Glow   | Neon accent color with strong blur & large radius |
| Minimalist    | Ultra‑light, low blur, small radius |

## 🔍 Browser Support
`backdrop-filter` is supported in all modern browsers, but may:
- Require `-webkit-backdrop-filter` in Safari
- Not appear in older versions of Firefox unless enabled by user flags
- Fallback gracefully (element remains translucent without blur)

## 📦 Tech Stack
- HTML5 + Vanilla JavaScript
- Tailwind CSS (CDN build)
- Inline SVG for procedural noise
- No frameworks, transpilers, or build tooling

## 🛠 Customization Ideas
| Goal | Approach |
|------|----------|
| Add export to PNG | Wrap preview in canvas via `html2canvas` |
| Save presets | Store JSON in `localStorage` |
| Shareable links | Encode settings in URL query params |
| Dark / Light UI toggle | Add a theme switcher + Tailwind utility toggles |
| Multi-element layout | Support multiple glass nodes + duplication |

## 📄 Privacy & Ads
A privacy policy is included in `privacy-policy.html`.

Current integrations:
- Monetag / PropellerAds verification + ad script

If you fork this project and do not intend to serve ads, remove the ad script tag blocks in both HTML files:
```html
<!-- Remove these if not monetizing -->
<meta name="monetag" content="...">
<script data-cfasync="false" src="//madurird.com/tag.min.js" data-zone="9862501"></script>
```

## 🖋 SEO Meta Tags
The `index.html` head includes:
- Title & description
- Author & keywords
- Open Graph preview image
You can replace the OG image URL with a custom hosted image for richer sharing.

## 🧩 Accessibility Notes
- The draggable card is mouse-only (no keyboard fallback yet)
- Radio buttons and sliders are standard form inputs (screen-reader friendly)
- Future improvement: ARIA labels for dynamic sections & keyboard drag mode

## ⚠ Limitations
- No persistent state (refresh resets unless you manually copy settings)
- Noise overlay is purely decorative
- CSS extraction is single-class only (no SCSS variables or tokens)
- Not optimized for very small mobile screens (<340px wide)

## 🤝 Contributing
1. Fork the repo
2. Create a feature branch: `feat/some-improvement`
3. Make changes (keep HTML self‑contained)
4. Submit a PR with a clear description & before/after visuals if UI changes

### Coding Guidelines
- Prefer semantic HTML where possible
- Keep logic inline unless it grows beyond ~300 lines (then extract JS)
- Avoid external dependencies unless they unlock a major feature

## 📌 Roadmap (Suggested)
- [ ] Local storage for last-used settings
- [ ] URL sharable configuration
- [ ] Keyboard-accessible dragging
- [ ] Export as image / snippet gallery
- [ ] Multi-glass layouts + layer manager
- [ ] Color palette suggestions / contrast warnings

## 🧪 Manual Testing Checklist
| Action | Expected |
|--------|----------|
| Change blur slider | Preview updates blur; CSS tab updates value |
| Toggle noise | Layer appears/disappears; code adds `::after` block |
| Switch element type | Content template changes appropriately |
| Copy CSS/HTML | Clipboard contains latest generated snippet |
| Change background mode | Proper controls show (solid/gradient) |
| Drag card | Stays inside preview area bounds |

## 📤 Deploying (Static Hosting)
You can host this on:
- GitHub Pages (just push to `main` / enable Pages)
- Netlify / Vercel (drag & drop folder)
- Any static S3 / Cloudflare Pages bucket

No special headers or server logic required.

## 🛡 License
Choose a license (e.g., MIT, Apache-2.0) and replace this section. If you plan to accept contributions, MIT is a common choice for simplicity.

## 🙋 FAQ
**Why don't I see blur?**  
Ensure you're in a modern browser and not inside an iframe with disabled filters.

**Can I use this in commercial projects?**  
Yes, the generated CSS/HTML is yours to use (subject to final repo license).

**Can I add my own presets?**  
Yes. Edit the `presets` object in `index.html` and append a new key.

## 🧑 Author
Built by Parjad Minooei.

---
If this tool helped you, consider starring the repository or sharing it. Enjoy crafting beautiful glass UI ✨
