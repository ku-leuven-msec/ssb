# BUGATTI Project Website

This repository hosts the static website for the BUGATTI (Building security Guidance, Applying pracTical Threat modellIng) project - a Vlaio/COOCK tech transfer project led by KU Leuven's DistriNet research group.

🌐 **Live Site:** [https://ku-leuven-msec.github.io/bugatti](https://ku-leuven-msec.github.io/bugatti)

## About the Project

BUGATTI bridges the gap between academic security research and practical industry applications, focusing on:
- Practical threat modeling methodologies
- Actionable security guidance
- Industry collaboration and knowledge transfer
- Dissemination of research findings

## Website Structure

The website is built using Jekyll and GitHub Pages. Key sections include:

- **Home** (`index.md`) - General project information and objectives
- **Presentations** (`presentations.md`) - Meeting presentations and materials
- **Calendar** (`calendar.md`) - Upcoming events with iCal subscription
- **Consortium** (`consortium.md`) - Research partners and advisory board

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

# Visit http://localhost:4000/bugatti
```

### Adding a Presentation

1. **Upload PDF file:**
   ```bash
   cp your-presentation.pdf assets/presentations/
   ```

2. **Create presentation entry:**
   Create a new file in `_presentations/` (e.g., `_presentations/2024-03-meeting.md`):
   ```yaml
   ---
   layout: default
   title: "Your Presentation Title"
   speaker: "Speaker Name"
   date: 2024-03-15
   event: "Quarterly Meeting Q1"
   description: "Brief description of the presentation content"
   slides: "/bugatti/assets/presentations/your-presentation.pdf"
   ---
   ```

3. **Commit and push:**
   ```bash
   git add _presentations/2024-03-meeting.md assets/presentations/your-presentation.pdf
   git commit -m "Add presentation from Q1 meeting"
   git push
   ```

The presentation will automatically appear on the presentations page.

### Updating the Calendar

#### Edit Calendar Page

Modify `calendar.md` to add event information in the "Upcoming Events" or "Past Events" sections.

#### Update iCalendar Feed

Edit `calendar.ics` to add/update events:

```ics
BEGIN:VEVENT
UID:unique-event-id@ku-leuven-msec.github.io
DTSTAMP:20240101T120000Z
DTSTART:20240315T100000Z
DTEND:20240315T170000Z
SUMMARY:Event Title
DESCRIPTION:Event description
LOCATION:Event location
STATUS:CONFIRMED
END:VEVENT
```

Users subscribed to the calendar feed will receive automatic updates.

### Updating Consortium Information

Edit `consortium.md` to:
- Add new research partners
- Update advisory board members
- Add company logos (place in `assets/images/`)
- Update collaboration opportunities

### Modifying Site Configuration

Edit `_config.yml` to change:
- Site title and description
- Navigation menu items
- Project metadata
- Theme settings

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
├── _presentations/          # Presentation collection
│   └── example-intro.md     # Example presentation entry
├── assets/
│   └── presentations/       # PDF files for presentations
├── index.md                 # Home page
├── presentations.md         # Presentations listing page
├── calendar.md              # Calendar and events page
├── calendar.ics             # iCalendar feed file
├── consortium.md            # Consortium information
├── Gemfile                  # Ruby dependencies
└── README.md               # This file
```

## Customization

### Styling

The site uses the Minima theme. To customize:
1. Override theme files in your repository
2. Add custom CSS in `assets/css/style.scss`
3. Modify layouts in `_layouts/`

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
- **Project Contact:** bugatti@cs.kuleuven.be
- **Technical Issues:** Open an issue in this repository

## License

Content © KU Leuven - DistriNet. All rights reserved.