# Secure Smart Buildings Project Website


This repository hosts the static website for the Secure Smart Buildings (SSB) project — a TETRA project led by KU Leuven's DistriNet research group in partnership with UCLL.

🌐 **Live Site:** [https://ssb.projects.cybersecurity-research.be](https://ssb.projects.cybersecurity-research.be)

## About the Project

Secure Smart Buildings focuses on enhancing cybersecurity for intelligent building systems. The project delivers:
- Security insights about attacks, vulnerabilities, and technologies for smart buildings
- Best practices and tools to increase resilience
- Methodologies for secure installation and management of building systems
- User group meetings and knowledge dissemination with industry stakeholders


## Website Structure & Features

The website is built with Jekyll and GitHub Pages, using custom SCSS and layouts for a modern, professional look. Key sections include:

- **Home** (`index.md`): Project overview and objectives
- **Knowledge Dissemination** (`knowledge-dissemination.md`): Events, workshops, and knowledge sharing
- **Blog** (`blog.md`): In-depth articles and insights
- **Presentations** (`presentations.md`): Meeting presentations and materials (PDFs in `assets/presentations/`)
- **Consortium** (`consortium.md`): Research partners, contact info, and funding

Other features:
- Modern favicon and browser icon support (SVG, PNG, ICO, Apple touch)
- Email addresses are obfuscated for privacy
- Responsive, visually improved footer and hero sections

## Updating the Website

### Prerequisites

To test the site locally:

```bash
# Install Ruby and Bundler
gem install bundler

# Install dependencies
bundle install

# Run local server
bundle exec jekyll serve

# Visit http://localhost:4000
```


### Adding a Presentation

1. **Upload PDF file:**
   ```bash
   cp your-presentation.pdf assets/presentations/
   ```

2. **Create or update a markdown entry in `presentations.md`** to link to your PDF:
   ```markdown
   - [Your Presentation Title](/assets/presentations/your-presentation.pdf) — Speaker Name, 2025-03-15
   ```

3. **Commit and push:**
   ```bash
   git add assets/presentations/your-presentation.pdf presentations.md
   git commit -m "Add presentation from Q1 meeting"
   git push
   ```

The presentation will appear on the Presentations page.


### Events & Knowledge Dissemination

Events, workshops, and knowledge sharing are managed in `knowledge-dissemination.md` and the `_dissemination/` collection. Add or update event entries as markdown files or directly in the main page.


### Updating Consortium Information

Edit `consortium.md` to:
- Add or update research partners and contact info
- Add or update funding and logos (place in `assets/images/`)
- Update collaboration opportunities


### Modifying Site Configuration

Edit `_config.yml` to change:
- Site title and description
- Navigation menu items (under `header_pages`)
- Project metadata

## GitHub Pages Deployment

The site automatically deploys when changes are pushed to the main branch:

1. Push changes to repository
2. GitHub Actions builds the site
3. Site is published to `gh-pages` branch
4. Changes appear at https://ku-leuven-msec.github.io/bugatti

### Enable GitHub Pages

In repository settings:
1. Go to **Settings** > **Pages**
2. Source: Deploy from a branch
3. Branch: Select `gh-pages` or `main` (depending on configuration)
4. Folder: `/ (root)` or `/docs`
5. Save

## File Structure

```
bugatti/
├── _config.yml              # Jekyll configuration
├── _blog/                  # Blog articles (markdown)
├── _dissemination/         # Event and knowledge dissemination entries
├── assets/
│   └── presentations/       # PDF files for presentations
├── index.md                 # Home page
├── presentations.md         # Presentations listing page
├── consortium.md            # Consortium information
├── Gemfile                  # Ruby dependencies
└── README.md               # This file
```


## Customization

### Styling

The site uses a custom SCSS file (`assets/css/style.scss`) and custom layouts in `_layouts/` for a modern, professional look. You can further customize by editing these files or adding new ones.

### Adding New Pages

Create a new markdown file with front matter:

```yaml
---
layout: page
title: "Page Title"
permalink: /page-url/
---

# Content here
```

Add to navigation in `_config.yml`:

```yaml
header_pages:
  - index.md
  - presentations.md
  - new-page.md
```


## Support

For questions or issues:
- **Project Contact:** bugatti [at] cs [dot] kuleuven [dot] be (email obfuscated for privacy)
- **Technical Issues:** Open an issue in this repository

## License

Content © KU Leuven - DistriNet. All rights reserved.