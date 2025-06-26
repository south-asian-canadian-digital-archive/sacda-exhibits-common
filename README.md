# SACDA Exhibits Common Components

A Sve```svelte
<script>
  import { Header, Footer } from '@south-asian-canadian-digital-archive/sacda-exhibits-common';
</script>

<Header />
```ponent library containing reusable UI components for SACDA (South Asian Canadian Digital Archive) exhibit applications.

## Installation

This package is published to GitHub Packages. See [GITHUB_PACKAGES.md](./GITHUB_PACKAGES.md) for detailed setup instructions.

### Quick Setup
1. Create `.npmrc` in your project:
```
@south-asian-canadian-digital-archive:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=${NODE_AUTH_TOKEN}
```

2. Set your GitHub token:
```bash
export NODE_AUTH_TOKEN=your_github_token_here
```

3. Install the package:
```bash
pnpm add @south-asian-canadian-digital-archive/sacda-exhibits-common
# or
npm install @south-asian-canadian-digital-archive/sacda-exhibits-common
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
  import { Footer } from '@south-asian-canadian-digital-archive/sacda-exhibits-common';
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

**Important**: Include the component library in your TailwindCSS content configuration:

```javascript
/** @type {import('tailwindcss').Config} */
export default {
  content: [
    './src/**/*.{html,js,svelte,ts}',
    './node_modules/@south-asian-canadian-digital-archive/sacda-exhibits-common/**/*.{html,js,svelte,ts}'
  ],
  theme: {
    extend: {},
  },
  plugins: [],
}
```

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

### Component Styles

The components use a combination of TailwindCSS classes and custom CSS for styling. To ensure styles work properly in your consuming project:

#### Method 1: Automatic Import (Recommended)
The component styles are automatically imported when you import the components. This should work for most use cases.

#### Method 2: Manual Import (For styling issues)
If you're experiencing issues with component styles not loading or being overridden by your project's CSS, manually import the component styles:

```javascript
// In your main app file, layout, or app.css
import '@south-asian-canadian-digital-archive/sacda-exhibits-common/dist/components.css';
```

#### Method 3: Custom CSS Integration
For maximum compatibility, you can copy the CSS from `components.css` and integrate it into your project's CSS with your own modifications.

**Note:** The component styles use high-specificity selectors and `!important` declarations to prevent them from being overridden by common CSS patterns in consuming projects.

## TypeScript Support

This library includes TypeScript definitions. You can import types if needed:

```typescript
import type { SponsorData, SocialData } from '@south-asian-canadian-digital-archive/sacda-exhibits-common';
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
