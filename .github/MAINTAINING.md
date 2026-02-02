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

## Best Practices

- Use descriptive commit messages
- Test locally before deploying
- Keep themes as submodules for easy updates
- Use Hugo's built-in features (shortcodes, partials) for reusability
- Optimize images and assets for web

## Resources

- [Hugo Documentation](https://gohugo.io/documentation/)
- [Ananke Theme Docs](https://github.com/theNewDynamic/gohugo-theme-ananke)
- [Hugo Community](https://discourse.gohugo.io/)