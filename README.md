# Pulso Digital

> A dark, modern editorial theme for [Ghost](https://ghost.org/), designed for independent tech journalism and digital publications.

&nbsp;

## 🖼 Screenshots

> _Add screenshots of your live demo here._

&nbsp;

## Features

- **Dark mode** — Deep dark background (#08090d) with carefully tuned contrast ratios for comfortable reading
- **Teal accent** — Eye-catching teal (#0dd9a3) for tags, buttons, links, and interactive elements
- **Plus Jakarta Sans** — Modern sans-serif typography loaded via Google Fonts
- **Curated homepage** — Five-row layout with automatic de-duplication:
  1. Hero (latest featured post)
  2. Three more featured posts
  3. Subscribe CTA (non-members only)
  4. Opinion section (tag-based)
  5. Latest posts (no repeats)
- **Full Ghost feature support** — Members, subscriptions, tiers, search, comments, newsletters, recommendations
- **Multiple header styles** — Landing, Highlight, Magazine, Search, Off
- **Feed styles** — Grid and List modes
- **17 custom settings** — Configurable directly from Ghost Admin
- **13 languages** — Including Spanish
- **Lightbox** — PhotoSwipe integration for image galleries
- **Infinite scroll** — Automatic pagination on archive pages
- **Ghost card support** — Full styling for all Ghost editor cards
- **Accessible** — Keyboard navigation, ARIA labels, focus-visible styles, semantic HTML
- **SEO-friendly** — Structured data, proper heading hierarchy, clean markup

&nbsp;

## Installation

### From a zip file

1. Download the [latest release](../../releases)
2. Go to **Ghost Admin → Settings → Design & branding → Change theme → Upload theme**
3. Upload the zip file and activate

### From GitHub (for development)

```bash
# Navigate to your Ghost themes directory
cd /path/to/ghost/content/themes/

# Clone the repository
git clone https://github.com/OWNER/pulso-digital.git

# Install dependencies
cd pulso-digital
npm install

# Build the theme
npm run build

# Restart Ghost
ghost restart
```

&nbsp;

## Development

Pulso Digital uses [Gulp](https://gulpjs.com/) to compile and build the theme.

### Prerequisites

- [Node.js](https://nodejs.org/) (v18+)
- [npm](https://www.npmjs.com/) or [yarn](https://yarnpkg.com/)
- A running [Ghost](https://ghost.org/docs/install/) instance

### Setup

```bash
# Install dependencies
npm install

# Start development mode with live reload
npm run dev
```

### Available commands

| Command | Description |
|---------|-------------|
| `npm run dev` | Start development mode with live reload |
| `npm run build` | Build CSS and JS for production |
| `npm run zip` | Build and create a zip file in `dist/` |
| `npm run test` | Validate theme with [GScan](https://gscan.ghost.org/) |
| `npm run test:ci` | Run GScan in strict mode (for CI) |

### File structure

```
pulso-digital/
├── assets/
│   ├── built/           # Compiled CSS and JS (committed to repo)
│   ├── css/             # Source CSS
│   ├── fonts/           # Inter, EB Garamond, JetBrains Mono
│   ├── images/          # PhotoSwipe lightbox assets
│   └── js/              # Source JavaScript
│       └── lib/         # Third-party JS libraries
├── locales/             # Translation files (13 languages)
├── partials/
│   ├── components/      # Navigation, header, footer, CTA, featured, post-list
│   ├── icons/           # SVG icon partials
│   └── typography/      # Font loading partials
├── default.hbs          # Main layout template
├── home.hbs             # Custom homepage (5-row curated layout)
├── index.hbs            # Paginated post archive
├── post.hbs             # Single post template
├── page.hbs             # Static page template
├── tag.hbs              # Tag archive template
├── author.hbs           # Author archive template
├── error.hbs            # Error page (404, 500)
├── package.json         # Theme metadata, config, and build scripts
├── gulpfile.js          # Build pipeline
└── README.md
```

&nbsp;

## Configuration

All settings are available in **Ghost Admin → Settings → Design & branding → Customize**.

### Site-wide

| Setting | Options | Default |
|---------|---------|---------|
| Navigation layout | Logo on the left / Logo in the middle / Stacked | Logo on the left |
| Title font | Modern sans-serif / Elegant serif / Consistent mono | Modern sans-serif |
| Body font | Modern sans-serif / Elegant serif | Modern sans-serif |
| Signup heading | Custom text | Site title |
| Signup subheading | Custom text | Site description |

### Homepage

| Setting | Options | Default |
|---------|---------|---------|
| Header style | Landing / Highlight / Magazine / Search / Off | Landing |
| Post feed style | List / Grid | Grid |
| Show images in feed | On/Off | On |
| Show author | On/Off | On |
| Show publish date | On/Off | On |
| Show sidebar | On/Off | Off |
| Show featured posts | On/Off | Off |
| Background image | On/Off | On |

### Post

| Setting | Options | Default |
|---------|---------|---------|
| Show post metadata | On/Off | On |
| Drop caps on posts | On/Off | Off |
| Show related articles | On/Off | On |

### Homepage customization

The homepage opinion section filters posts by the `opinion` tag slug. If your tag slug is different, edit line 103 in `home.hbs`:

```handlebars
{{!-- Change "opinion" to your tag slug --}}
{{#get "posts" filter="tag:opinion" include="authors,tags" limit="4"}}
```

&nbsp;

## Contributing

Contributions are welcome! Please follow these steps:

1. Fork this repository
2. Create a feature branch: `git checkout -b feature/my-feature`
3. Make your changes and test with `npm run test`
4. Commit with a clear message: `git commit -m "Add: my new feature"`
5. Push and open a Pull Request

### Code style

- Use 4-space indentation
- Add code comments for complex logic
- Follow the existing naming conventions (`pd-` prefix for custom homepage components, `gh-` for Ghost-standard elements)
- Test your changes with [GScan](https://gscan.ghost.org/) before submitting

&nbsp;

## Credits

- Based on [Source](https://github.com/TryGhost/Source) by Ghost Foundation
- Typography: [Plus Jakarta Sans](https://fonts.google.com/specimen/Plus+Jakarta+Sans) by Tokotype
- Lightbox: [PhotoSwipe](https://photoswipe.com/)

## License

[MIT](LICENSE)
