# UTAITEREC - Technical Specification

## Technology Stack
- **Frontend**: HTML5 + CSS3 only (No JavaScript frameworks)
- **Templating**: Python Jinja2 for HTML generation
- **Data Processing**: Python pandas for spreadsheet parsing
- **Deployment**: Static website (GitHub Pages / Netlify compatible)

## Architecture
Multi-page static website with 22 generated detail pages:
- `index.html` - Homepage
- `recommendation.html` - Voice category recommendations
- `database.html` - Artist database with search/filter
- `detail/[artist-name].html` - 22 individual artist detail pages

## Component Decomposition

### Layout Components (shared across all pages)

| Component | Type | Description |
|-----------|------|-------------|
| `page-header` | CSS | Gradient header with UTAITEREC title |
| `site-nav` | HTML+CSS | Desktop horizontal nav + mobile hamburger |
| `footer` | HTML+CSS | Simple copyright footer |

### Section Components (page-specific)

| Component | Page | Description |
|-----------|------|-------------|
| `hero-title` | Homepage | Title + subtitle |
| `photo-collage` | Homepage | Polaroid-style image collage |
| `musical-staff` | Homepage | Interactive staff with note dots |
| `voice-category-section` | Recommendation | Grouped artist cards per voice type |
| `popular-underrated` | Database | Two-column popular/underrated lists |
| `search-section` | Database | Search input + alphabet filter |
| `artist-list` | Database | Alphabetically grouped artist list |
| `profile-section` | Detail | Avatar + name + tags |
| `info-card` | Detail | Description + group + socials |
| `similar-artists` | Detail | 3 similar artist cards |

### Reusable Components

| Component | Used In | Description |
|-----------|---------|-------------|
| `artist-card-sm` | Database | Small horizontal card (50px avatar) |
| `artist-card-md` | Recommendation | Medium horizontal card (80px image) |
| `artist-card-lg` | Detail | Large vertical card (square image) |
| `tag-pill` | Detail | Rounded genre/voice/type tag |
| `social-icon` | Detail | Platform social media icon |
| `alphabet-button` | Database | Circular A-Z filter button |

## Animation & Interaction Table

| Animation | Type | Implementation | Complexity |
|-----------|------|---------------|------------|
| Note dot hover scale | CSS :hover | transform: scale(1.2) | Low |
| Card hover lift | CSS :hover | transform: translateY(-4px) + shadow | Low |
| Nav link underline | CSS | scaleX transition on pseudo-element | Low |
| Button hover | CSS :hover | brightness + slight scale | Low |
| Alphabet button hover | CSS :hover | bg color + text color transition | Low |
| Smooth scroll | CSS | scroll-behavior: smooth | Low |
| Photo collage rotation | CSS | Static transform: rotate(Ndeg) | Low |
| Polaroid border effect | CSS | White padding + shadow | Low |
| Staff line drawing | SVG | Static SVG rendering | Low |
| Mobile menu toggle | CSS checkbox hack | :checked + ~ sibling selector | Medium |
| Card stagger fade | CSS animation | @keyframes fadeInUp with animation-delay | Low |

## Data Flow

```
Spreadsheet (.xlsx)
  → Python pandas parsing
    → artists_data.json (structured data)
      → Jinja2 templates
        → Static HTML files (23 pages)
```

## Generated Files Structure

```
/
├── index.html                          # Homepage
├── recommendation.html                 # Voice category recommendations
├── database.html                       # Artist database
├── detail/
│   ├── eve.html
│   ├── ado.html
│   ├── mafumafu.html
│   ├── soraru.html
│   ├── urata.html
│   ├── sakata.html
│   ├── shima.html
│   ├── senra.html
│   ├── tuki.html
│   ├── sou.html
│   ├── gero.html
│   ├── meychan.html
│   ├── nqrse.html
│   ├── luz.html
│   ├── akugetsu.html
│   ├── araki.html
│   ├── dongdang.html
│   ├── otomose-raco.html
│   ├── amatsuki.html
│   ├── 96neko.html
│   ├── chogakusei.html
│   └── reol.html
├── css/
│   └── style.css                       # All styles
└── assets/
    └── artists/                        # 22 generated portraits
```

## CSS Architecture

### File Organization
Single `style.css` with sections:
1. CSS Custom Properties (design tokens)
2. CSS Reset & Base styles
3. Utility classes
4. Layout components
5. Page-specific styles
6. Media queries (responsive)
7. Animations & keyframes

### Key CSS Features
- CSS Grid for page layouts
- Flexbox for component alignment
- CSS custom properties for theming
- Mobile-first responsive approach
- CSS-only interactions (no JS)

## Responsive Breakpoints

| Breakpoint | Target | Key Changes |
|------------|--------|-------------|
| < 576px | Mobile | Single column, hamburger nav, smaller fonts |
| 576-768px | Tablet | Two columns where applicable |
| 768-992px | Desktop | Full layout |
| > 992px | Large desktop | Max-width containers |

## CSS-Only Mobile Menu

Using checkbox hack pattern:
```html
<input type="checkbox" id="menu-toggle" hidden>
<label for="menu-toggle" class="menu-button">☰</label>
<nav class="main-nav">
  <!-- nav items -->
</nav>
```

```css
.main-nav { display: none; }
#menu-toggle:checked ~ .main-nav { display: block; }
```

## Implementation Notes

1. **No JavaScript**: All interactions are CSS-only
2. **No Build Tool**: Pure static files, any web server can host
3. **Detail Pages**: Pre-generated from data, not dynamic
4. **Images**: All artist portraits pre-generated as JPG
5. **Accessibility**: Semantic HTML, alt text, focus states, ARIA labels
