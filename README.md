# teafyi-embed

[![npm](https://img.shields.io/npm/v/teafyi-embed)](https://www.npmjs.com/package/teafyi-embed)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](https://opensource.org/licenses/MIT)
[![Zero Dependencies](https://img.shields.io/badge/dependencies-0-brightgreen)](https://www.npmjs.com/package/teafyi-embed)
[![Size](https://img.shields.io/badge/size-~10--16KB_gzipped-green)](https://bundlephobia.com/package/teafyi-embed)

Embed **TeaFYI** beverage widgets — tea varieties, recipes, glossary terms, and interactive tools — on any website. **10 widget types**, zero dependencies, Shadow DOM style isolation, 4 built-in themes (light, dark, sepia, auto), and live data from the [TeaFYI](https://teafyi.com) database.

Every widget includes a "Powered by TeaFYI" backlink directing readers to the full beverage reference.

> **Try the interactive widget builder at [widget.teafyi.com](https://widget.teafyi.com)**

## Quick Start

```html
<!-- Place widget div where you want it to appear -->
<div data-teafyi="recipe" data-slug="varieties" data-theme="light"></div>

<!-- Load the embed script once, anywhere on the page -->
<script src="https://cdn.jsdelivr.net/npm/teafyi-embed@1/dist/embed.min.js"></script>
```

That's it. The widget fetches data from the TeaFYI API and renders with full style isolation.

## Widget Types

| Type | Usage | Description |
|------|-------|-------------|
| `recipe` | `<div data-teafyi="recipe" data-slug="..."></div>` | Recipe/entity card — ingredients, technique, ABV, glass type |
| `compare` | `<div data-teafyi="compare" data-slug="..."></div>` | Side-by-side comparison of beverages or styles |
| `glossary` | `<div data-teafyi="glossary" data-slug="..."></div>` | Glossary term definition with cross-references |
| `faq` | `<div data-teafyi="faq" data-slug="..."></div>` | FAQ accordion for common beverage questions |
| `guide` | `<div data-teafyi="guide" data-slug="..."></div>` | Tasting, brewing, or pairing guide summary |
| `ingredient` | `<div data-teafyi="ingredient" data-slug="..."></div>` | Ingredient/variety card — spirit, grape, hop, coffee origin |
| `pairing` | `<div data-teafyi="pairing" data-slug="..."></div>` | Food pairing suggestions — "What goes with...?" |
| `search` | `<div data-teafyi="search" data-slug="..."></div>` | Search box linking to the full beverage database |
| `color-swatch` | `<div data-teafyi="color-swatch" data-slug="..."></div>` | Oxidation spectrum (0-100%) — green to black tea color |
| `brew-timer` | `<div data-teafyi="brew-timer" data-slug="..."></div>` | Tea steeping timer with temperature and time presets |

## Widget Options

| Attribute | Values | Default | Description |
|-----------|--------|---------|-------------|
| `data-teafyi` | recipe, compare, glossary, faq, guide, ingredient, pairing, search, [tools] | required | Widget type |
| `data-slug` | e.g. "varieties" | — | Entity slug from the TeaFYI database |
| `data-theme` | light, dark, sepia, auto | light | Visual theme (`auto` follows OS preference) |
| `data-style` | modern, classic | modern | Widget design style |
| `data-size` | default, compact, large | default | Widget size |
| `data-placeholder` | any string | "Search Tea Varieties..." | Search box placeholder |

## Themes

```html
<!-- Light (default) -->
<div data-teafyi="recipe" data-slug="varieties" data-theme="light"></div>

<!-- Dark -->
<div data-teafyi="recipe" data-slug="varieties" data-theme="dark"></div>

<!-- Sepia -->
<div data-teafyi="recipe" data-slug="varieties" data-theme="sepia"></div>

<!-- Auto — follows OS dark/light preference -->
<div data-teafyi="recipe" data-slug="varieties" data-theme="auto"></div>
```

## Web Components (Custom Elements)

As an alternative to `data-*` attributes, you can use native HTML custom elements:

```html
<!-- Custom element form -->
<teafyi-recipe slug="varieties" theme="light"></teafyi-recipe>
<teafyi-compare slugs="varieties,other-slug"></teafyi-compare>
<teafyi-search placeholder="Search Tea Varieties..."></teafyi-search>

<script src="https://cdn.jsdelivr.net/npm/teafyi-embed@1/dist/embed.min.js"></script>
```

Use `style-variant` (not `style`) to avoid conflicts with the HTML reserved `style` attribute.

## Examples

### Recipe Card

```html
<div data-teafyi="recipe" data-slug="varieties" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/teafyi-embed@1/dist/embed.min.js"></script>
```

### Side-by-Side Comparison

```html
<div data-teafyi="compare" data-slugs="varieties,other-slug"></div>
<script src="https://cdn.jsdelivr.net/npm/teafyi-embed@1/dist/embed.min.js"></script>
```

### Search Box

```html
<div data-teafyi="search" data-placeholder="Search Tea Varieties..."></div>
<script src="https://cdn.jsdelivr.net/npm/teafyi-embed@1/dist/embed.min.js"></script>
```

### Glossary Term

```html
<div data-teafyi="glossary" data-slug="example-term" data-theme="light"></div>
<script src="https://cdn.jsdelivr.net/npm/teafyi-embed@1/dist/embed.min.js"></script>
```

## CDN Options

### jsDelivr (recommended — global CDN, auto-updates with npm)

```html
<script src="https://cdn.jsdelivr.net/npm/teafyi-embed@1/dist/embed.min.js"></script>
```

### Specific version (production stability)

```html
<script src="https://cdn.jsdelivr.net/npm/teafyi-embed@1.1.1/dist/embed.min.js"></script>
```

### npm (for bundlers)

```bash
npm install teafyi-embed
```

```javascript
import 'teafyi-embed';
```

## Technical Details

- **Shadow DOM**: Complete style isolation — no CSS conflicts with your site
- **Zero dependencies**: No jQuery, React, or any external library
- **Geist Sans**: Body text uses Geist Sans for a clean, modern look
- **System fonts**: Fallback to system-ui — no extra font requests
- **CORS**: TeaFYI API has CORS enabled for all origins
- **MutationObserver**: Works with dynamically added elements (SPAs)
- **IntersectionObserver**: Lazy loading — widgets only fetch when entering viewport (200px margin)
- **Bundle size**: ~10-16KB gzipped (per-site build — only includes tools available on TeaFYI)

## Learn More About Tea Varieties

Visit [teafyi.com](https://teafyi.com) — TeaFYI is a comprehensive tea varieties reference with recipes, tasting notes, interactive tools, and beverage guides.

- **API docs**: [teafyi.com/developers/](https://teafyi.com/developers/)
- **Widget builder**: [widget.teafyi.com](https://widget.teafyi.com)
- **npm package**: [npmjs.com/package/teafyi-embed](https://www.npmjs.com/package/teafyi-embed)
- **GitHub**: [github.com/fyipedia/teafyi-embed](https://github.com/fyipedia/teafyi-embed)

## Beverage FYI Family

Part of [FYIPedia](https://fyipedia.com) — open-source developer tools ecosystem. Beverage FYI covers world beverages — cocktails, wine, beer, whiskey, sake, tea, and coffee.

| Site | Domain | Focus | Package |
|------|--------|-------|---------|
| CocktailFYI | [cocktailfyi.com](https://cocktailfyi.com) | 636 cocktails, ABV, calories, flavor profiles, glass types | [npm](https://www.npmjs.com/package/cocktailfyi-embed) |
| VinoFYI | [vinofyi.com](https://vinofyi.com) | Wines, grapes, regions, wineries, food pairings | [npm](https://www.npmjs.com/package/vinofyi-embed) |
| BeerFYI | [beerfyi.com](https://beerfyi.com) | 113 beer styles, hops, malts, yeast, BJCP guide | [npm](https://www.npmjs.com/package/beerfyi-embed) |
| BrewFYI | [brewfyi.com](https://brewfyi.com) | 72 coffee varieties, roasting, 21 brew methods | [npm](https://www.npmjs.com/package/brewfyi-embed) |
| WhiskeyFYI | [whiskeyfyi.com](https://whiskeyfyi.com) | 2,200+ whiskey expressions, distilleries, regions | [npm](https://www.npmjs.com/package/whiskeyfyi-embed) |
| **TeaFYI** | [teafyi.com](https://teafyi.com) | 60+ tea varieties, teaware, brewing guides | **[npm](https://www.npmjs.com/package/teafyi-embed)** |
| NihonshuFYI | [nihonshufyi.com](https://nihonshufyi.com) | 80 sake, rice varieties, 50 breweries | [npm](https://www.npmjs.com/package/nihonshufyi-embed) |

## License

MIT — see [LICENSE](./LICENSE).

Built with care by [FYIPedia](https://fyipedia.com).
