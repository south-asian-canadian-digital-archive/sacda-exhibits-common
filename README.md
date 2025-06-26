# SACDA Exhibits Common Components

A Svelte component library containing reusable UI components for SACDA (South Asian Canadian Digital Archive) exhibit applications.

## Installation

```bash
npm install sacda-exhibits-common
# or
pnpm add sacda-exhibits-common
# or
yarn add sacda-exhibits-common
```

## Components

### Header

A responsive navigation header component with search functionality and mobile menu.

**Features:**
- Responsive design (mobile, tablet, desktop)
- Search functionality
- Mobile hamburger menu
- Links to main SACDA sections (Browse, Collections, Exhibits, About, Contact, Newsletter)

**Usage:**

```svelte
<script>
  import { Header } from 'sacda-exhibits-common';
</script>

<Header />
```

### Footer

A footer component with sponsor logos and social media links.

**Features:**
- Sponsor organization logos with links
- Social media icons with links
- Copyright information
- Responsive design

**Usage:**

```svelte
<script>
  import { Footer } from 'sacda-exhibits-common';
</script>

<Footer />
```

## Requirements

- Svelte 5.0+
- SvelteKit 2.0+
- TailwindCSS (for styling)
- Font Awesome (for icons)

## Styling

These components use TailwindCSS classes and expect Font Awesome icons to be available. Make sure to include both in your project:

### TailwindCSS

Install and configure TailwindCSS in your project following the [official guide](https://tailwindcss.com/docs/guides/sveltekit).

### Font Awesome

Include Font Awesome kit in your app.html:

```html
<script src="https://kit.fontawesome.com/30f055fc02.js" crossorigin="anonymous"></script>
```

Or use the CDN version:

```html
<link rel="stylesheet" href="https://cdnjs.cloudflare.com/ajax/libs/font-awesome/6.0.0/css/all.min.css">
```

Or install it as a dependency:

```bash
npm install @fortawesome/fontawesome-free
```

## TypeScript Support

This library includes TypeScript definitions. You can import types if needed:

```typescript
import type { SponsorData, SocialData } from 'sacda-exhibits-common';
```

## Development

To contribute to this library:

1. Clone the repository
2. Install dependencies: `pnpm install`
3. Start development server: `pnpm dev`
4. Build the library: `pnpm build`

## Publishing

To publish this library:

```bash
npm run package
npm publish
```

## License

This project is part of the South Asian Canadian Digital Archive initiative.

Go into the `package.json` and give your package the desired name through the `"name"` option. Also consider adding a `"license"` field and point it to a `LICENSE` file which you can create from a template (one popular option is the [MIT license](https://opensource.org/license/mit/)).

To publish your library to [npm](https://www.npmjs.com):

```bash
npm publish
```
