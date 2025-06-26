# Usage Examples

> **Note**: This package is published to GitHub Packages. See [GITHUB_PACKAGES.md](./GITHUB_PACKAGES.md) for authentication setup before installing.

## Basic Usage

```svelte
<!-- App.svelte -->
<script>
  import { Header, Footer } from '@south-asian-canadian-digital-archive/sacda-exhibits-common';
  // Optional: Import component styles manually if TailwindCSS isn't processing them
  import '@south-asian-canadian-digital-archive/sacda-exhibits-common/dist/components.css';
</script>

<!-- Include Font Awesome in your app.html -->
<svelte:head>
  <script src="https://kit.fontawesome.com/30f055fc02.js" crossorigin="anonymous"></script>
</svelte:head>

<Header />

<main>
  <!-- Your content here -->
</main>

<Footer />
```

## With TypeScript

```typescript
// types.ts
import type { SponsorData, SocialData } from '@south-asian-canadian-digital-archive/sacda-exhibits-common';

// Use the types if you need to work with sponsor or social data
const customSponsors: SponsorData[] = [
  {
    name: "Custom Sponsor",
    link: "https://example.com",
    image: "https://example.com/logo.svg"
  }
];
```

## SvelteKit Setup

Make sure your `app.html` includes TailwindCSS and Font Awesome:

```html
<!DOCTYPE html>
<html lang="en">
<head>
  <meta charset="utf-8" />
  <link rel="icon" href="%sveltekit.assets%/favicon.png" />
  <meta name="viewport" content="width=device-width, initial-scale=1" />
  
  <!-- TailwindCSS -->
  <script src="https://cdn.tailwindcss.com"></script>
  
  <!-- Font Awesome -->
  <script src="https://kit.fontawesome.com/30f055fc02.js" crossorigin="anonymous"></script>
  
  %sveltekit.head%
</head>
<body data-sveltekit-preload-data="hover">
  <div style="display: contents">%sveltekit.body%</div>
</body>
</html>
```

## Installation in a New Project

```bash
# Create a new SvelteKit project
npm create svelte@latest my-exhibit-app
cd my-exhibit-app
npm install

# Install the SACDA components
npm install @south-asian-canadian-digital-archive/sacda-exhibits-common

# Install TailwindCSS (if not already installed)
npm install -D tailwindcss autoprefixer
npx tailwindcss init -p
```

Configure `tailwind.config.js`:

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

## Custom Styling

If you need to override styles, you can use TailwindCSS utilities or custom CSS:

```svelte
<style>
  :global(.nav-item a) {
    /* Custom styles for navigation links */
    @apply hover:text-blue-600;
  }
</style>
```

## Troubleshooting Style Issues

If the component styles aren't loading properly or are being overridden by your project's CSS, try these solutions:

### Solution 1: Import CSS Manually

```javascript
// In your main app file, layout, or app.css
import '@south-asian-canadian-digital-archive/sacda-exhibits-common/dist/components.css';
```

### Solution 2: Ensure TailwindCSS Processing

Make sure your `tailwind.config.js` includes the component library:

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

### Solution 3: Override with Higher Specificity

If you need to customize styles, use the same class structure:

```css
/* Your custom CSS */
.sacda-header .sacda-nav-list .sacda-nav-item .sacda-nav-link {
  color: your-custom-color !important;
}
```

### Solution 4: Check CSS Load Order

Ensure the component CSS loads before your custom CSS:

```svelte
<script>
  // Component CSS loads first
  import '@south-asian-canadian-digital-archive/sacda-exhibits-common/dist/components.css';
  // Your custom CSS loads after
  import './custom-styles.css';
</script>
```
