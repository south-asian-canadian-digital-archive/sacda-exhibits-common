# GitHub Packages Setup Guide

This guide explains how to publish and consume this package using GitHub Packages.

## 📦 **Publishing the Package**

### Prerequisites
- Repository must be owned by `sacda` organization
- You need `write` permissions to the repository
- GitHub Actions are enabled

### Automatic Publishing
The package is automatically published to GitHub Packages when:
1. A new release is created on GitHub
2. The workflow can also be triggered manually from the Actions tab

### Manual Publishing
To publish manually:
```bash
# 1. Authenticate with GitHub Packages
echo "//npm.pkg.github.com/:_authToken=${GITHUB_TOKEN}" >> ~/.npmrc

# 2. Build and publish
pnpm build
pnpm publish
```

## 📥 **Installing the Package in Other Projects**

### Step 1: Configure npm/pnpm to use GitHub Packages
Create or update `.npmrc` in your project root:
```
@south-asian-canadian-digital-archive:registry=https://npm.pkg.github.com
//npm.pkg.github.com/:_authToken=${NODE_AUTH_TOKEN}
```

### Step 2: Set up authentication
#### Option A: Using Personal Access Token (recommended for development)
1. Go to GitHub Settings → Developer settings → Personal access tokens → Tokens (classic)
2. Generate a token with `read:packages` scope
3. Add to your environment:
```bash
export NODE_AUTH_TOKEN=your_github_token_here
```

#### Option B: Using GITHUB_TOKEN in CI/CD
In your GitHub Actions workflow:
```yaml
- name: Setup Node.js
  uses: actions/setup-node@v4        with:
          node-version: '20'
          registry-url: 'https://npm.pkg.github.com'
          scope: '@south-asian-canadian-digital-archive'

- name: Install dependencies
  run: pnpm install
  env:
    NODE_AUTH_TOKEN: ${{ secrets.GITHUB_TOKEN }}
```

### Step 3: Install the package
```bash
# Using pnpm
pnpm add @south-asian-canadian-digital-archive/sacda-exhibits-common

# Using npm
npm install @south-asian-canadian-digital-archive/sacda-exhibits-common

# Using yarn
yarn add @south-asian-canadian-digital-archive/sacda-exhibits-common
```

## 🛠 **Usage in Other Projects**

### Basic Usage
```svelte
<script>
  import { Header, Footer } from '@south-asian-canadian-digital-archive/sacda-exhibits-common';
</script>

<Header />
<main>
  <!-- Your content -->
</main>
<Footer />
```

### TypeScript Support
```typescript
import type { SponsorData, SocialData } from '@south-asian-canadian-digital-archive/sacda-exhibits-common';
```

## 🔄 **Version Management**

### Semantic Versioning
This package follows [Semantic Versioning](https://semver.org/):
- `MAJOR`: Breaking changes
- `MINOR`: New features (backward compatible)
- `PATCH`: Bug fixes (backward compatible)

### Releasing New Versions
1. Update version in `package.json`:
   ```bash
   pnpm version patch  # for bug fixes
   pnpm version minor  # for new features
   pnpm version major  # for breaking changes
   ```
2. Push changes and tags:
   ```bash
   git push && git push --tags
   ```
3. Create a release on GitHub (this triggers automatic publishing)

## 🏢 **Organization Benefits**

### Private Package Access
- Only members of the `south-asian-canadian-digital-archive` organization can install this package
- Perfect for internal component libraries
- No additional costs compared to npm private packages

### Access Control
- Repository collaborators automatically have access
- Fine-grained permissions through GitHub teams
- Audit trail through GitHub's activity logs

## 🚨 **Troubleshooting**

### Common Issues
1. **Authentication Errors**: Ensure your `NODE_AUTH_TOKEN` is set and valid
2. **Permission Denied**: Check you have `read:packages` permission
3. **Package Not Found**: Verify the package name includes the `@south-asian-canadian-digital-archive` scope

### Debug Commands
```bash
# Check npm configuration
npm config list

# Verify authentication
npm whoami --registry=https://npm.pkg.github.com

# Check package visibility
curl -H "Authorization: token YOUR_TOKEN" \
  https://api.github.com/orgs/south-asian-canadian-digital-archive/packages/npm/@south-asian-canadian-digital-archive/sacda-exhibits-common
```
