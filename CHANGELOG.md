# Changelog

All notable changes to this project will be documented in this file.

The format is based on [Keep a Changelog](https://keepachangelog.com/en/1.0.0/),
and this project adheres to [Semantic Versioning](https://semver.org/spec/v2.0.0.html).

## [0.0.1] - 2025-06-25

### Added
- Initial release of SACDA Exhibits Common Components
- Header component with responsive navigation and search functionality
- Footer component with sponsor logos and social media links
- TypeScript support with proper type definitions
- Demo page showcasing components
- Complete documentation and usage examples
- GitHub Packages configuration for organization-wide distribution
- Comprehensive setup guide for GitHub Packages authentication and usage

### Fixed
- Fixed navigation link hover effects by replacing undefined `nav-link` class with proper Tailwind utility classes
- Navigation links now properly show orange bottom border on hover with smooth transition
- Fixed pnpm lockfile configuration mismatch to resolve CI/CD build issues

### Changed
- Updated Header component: Changed "CONTRIBUTE" button to "NEWSLETTER" with updated link
- Updated Font Awesome integration to use FontAwesome Kit script for better icon support
- Changed newsletter button styling to match other navigation links (removed special background styling)
- **BREAKING**: Package name changed from `sacda-exhibits-common` to `@south-asian-canadian-digital-archive/sacda-exhibits-common` for GitHub Packages
- Switched from npm registry to GitHub Packages for distribution

### Features
- Responsive design for mobile, tablet, and desktop
- TailwindCSS styling
- Font Awesome icon integration with kit support
- SvelteKit compatibility
- Easy import and usage in Svelte projects
