# Maintaining Your Hugo Portfolio Website

This guide provides instructions for maintaining and updating your Hugo-based portfolio website.

## Prerequisites

- [Hugo](https://gohugo.io/getting-started/installing/) installed on your system
- Git for version control
- Basic knowledge of Markdown for content creation

## Project Structure

- `hugo.yaml`: Site configuration
- `content/`: Markdown files for pages and posts
- `static/`: Static assets (images, PDFs, etc.)
- `themes/`: Hugo themes (likely as git submodules)
- `public/`: Generated site (don't edit manually)

## Regular Maintenance Tasks

### 1. Update Hugo

Keep Hugo updated to the latest version:

```bash
hugo version  # Check current version
# Download and install latest from https://github.com/gohugoio/hugo/releases
```

### 2. Update Themes

If using git submodules for themes:

```bash
git submodule update --remote
```

Or manually update the theme repository.

### 3. Add New Content

- Create new Markdown files in `content/`
- Use archetypes for consistent front matter: `hugo new <path>`
- For static files (PDFs, images), place in `static/`

### 4. Customize Theme

To override theme templates:
- Copy files from `themes/<theme>/layouts/` to `layouts/` in root
- Modify as needed
- Same for `assets/`, `static/`

### 5. Build and Test Locally

```bash
hugo server  # Start local server at http://localhost:1313
hugo  # Build to public/
```

### 6. Deploy

For GitHub Pages:
- Commit changes
- Push to main branch
- GitHub Actions will build and deploy automatically (if set up)

### 7. Check for Broken Links

Use tools like:
- `hugo --minify --gc` to build
- Check `public/` for generated files
- Use online link checkers or `lychee` CLI tool

## Troubleshooting

### Broken Links
- Ensure static files are in `static/` directory
- Use relative paths in content: `/files/resume.pdf`
- Check `baseURL` in `hugo.yaml`

### Theme Issues
- Verify theme is properly installed (git submodule status)
- Check theme documentation for customization options

### Build Errors
- Run `hugo --debug` for detailed error messages
- Check front matter in content files
- Ensure all required parameters are set in `hugo.yaml`

## Troubleshooting

### Why Changes Don't Show Up
If your changes aren't appearing on the site, check these common issues:

1. **Browser Cache**: Browsers cache CSS and JS. Do a hard refresh (Ctrl+F5 or Cmd+Shift+R) or clear cache.

2. **Hugo Server Not Rebuilding**: If using `hugo server`, it should auto-rebuild, but sometimes restart it. Run `hugo server --disableFastRender` for full rebuilds.

3. **Build Errors**: Run `hugo` to build and check for errors. Fix any YAML or syntax issues.

4. **File Locations**: Ensure edits are in the correct files:
   - Theme overrides: `layouts/`, `assets/`
   - Content: `content/`
   - Config: `hugo.yaml`

5. **Asset Compilation**: SASS changes need `hugo` rebuild. Check `public/css/styles.css` for your changes.

6. **Git Status**: If using git, check if files are committed and pushed (for GitHub Pages).

7. **Theme Submodules**: If modifying theme files, changes may be overwritten on update. Use overrides in root instead.

8. **Console Errors**: Check browser console for JS errors, and Hugo output for build errors.

If issues persist, run `hugo --debug` for detailed output.

## Custom Features

### Sidebar
- **Location**: `layouts/partials/sidebar.html`
- **Styling**: `assets/_custom.scss` (search for `.sidebar.layout__second-sidebar`)
- **JavaScript**: `layouts/partials/scripts.html` (dark mode toggle script)
- **Modifications**:
  - To make dark mode toggle classier: Edit the button styling in `assets/_custom.scss` under `#theme-toggle`
  - To add table of contents: In `layouts/partials/sidebar.html`, add `{{ .TableOfContents }}` inside a conditional for single pages (e.g., `{{ if .IsPage }}{{ .TableOfContents }}{{ end }}`)
  - Sidebar is hidden on screens narrower than 1200px; adjust in `assets/_custom.scss`