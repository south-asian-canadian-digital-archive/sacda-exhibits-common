<script>
  import { Header, Footer } from '$lib/index.js';
</script>

<svelte:head>
  <title>SACDA Exhibits Common Components - Demo</title>
  <script src="https://kit.fontawesome.com/30f055fc02.js" crossorigin="anonymous"></script>
</svelte:head>

<Header />

<main class="min-h-screen bg-gray-50 py-12 px-6">
  <div class="max-w-4xl mx-auto">
    <div class="text-center mb-12">
      <h1 class="text-4xl font-bold text-gray-900 mb-4">SACDA Exhibits Common Components</h1>
      <p class="text-lg text-gray-600 mb-8">Reusable Svelte components for SACDA exhibit applications</p>
    </div>

    <div class="bg-white rounded-lg shadow-lg p-8 mb-8">
      <h2 class="text-2xl font-semibold mb-4">Header Component</h2>
      <p class="text-gray-600 mb-4">
        The header component includes responsive navigation, search functionality, and mobile menu support.
      </p>
      <div class="bg-gray-100 p-4 rounded">
        <code class="text-sm">
          import &#123; Header &#125; from 'sacda-exhibits-common';<br>
          &lt;Header /&gt;
        </code>
      </div>
    </div>

    <div class="bg-white rounded-lg shadow-lg p-8 mb-8">
      <h2 class="text-2xl font-semibold mb-4">Footer Component</h2>
      <p class="text-gray-600 mb-4">
        The footer component displays sponsor logos, social media links, and copyright information.
      </p>
      <div class="bg-gray-100 p-4 rounded">
        <code class="text-sm">
          import &#123; Footer &#125; from 'sacda-exhibits-common';<br>
          &lt;Footer /&gt;
        </code>
      </div>
    </div>

    <div class="bg-white rounded-lg shadow-lg p-8">
      <h2 class="text-2xl font-semibold mb-4">Features</h2>
      <ul class="list-disc list-inside space-y-2 text-gray-600">
        <li>Responsive design for mobile, tablet, and desktop</li>
        <li>TypeScript support with proper type definitions</li>
        <li>TailwindCSS styling</li>
        <li>Font Awesome icon integration</li>
        <li>SvelteKit compatible</li>
        <li>Easy to import and use in any Svelte project</li>
      </ul>
    </div>
  </div>
</main>

<Footer />
