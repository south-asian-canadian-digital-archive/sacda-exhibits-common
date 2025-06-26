# Usage Examples

## Basic Usage

```svelte
<!-- App.svelte -->
<script>
  import { Header, Footer } from 'sacda-exhibits-common';
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
import type { SponsorData, SocialData } from 'sacda-exhibits-common';

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
npm install sacda-exhibits-common

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
    './node_modules/sacda-exhibits-common/**/*.{html,js,svelte,ts}'
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
