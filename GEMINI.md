# GEMINI.md

## Project Overview

This project is a personal resume website built with **Jekyll** and designed to be hosted on **GitHub Pages**. It is based on a popular resume template that uses a data-driven approach, where the content of the resume is separated from the layout and styling.

### Key Technologies
- **Jekyll**: Static site generator.
- **Ruby**: Underlying language for Jekyll.
- **Liquid**: Templating engine for layouts.
- **Sass/SCSS**: CSS preprocessor for styling.
- **YAML**: Used for configuration and data storage.

---

## Building and Running

To run this project locally, you need to have Ruby and Bundler installed.

1.  **Install Dependencies:**
    ```bash
    bundle install
    ```

2.  **Run Locally:**
    ```bash
    bundle exec jekyll serve
    ```
    The site will be available at `http://localhost:4000`.

3.  **Build for Production:**
    ```bash
    bundle exec jekyll build
    ```

---

## Development Conventions

### Content Management
Most of the resume content is managed via YAML files in the `_data/` directory. Each file corresponds to a section of the resume:
- `experience.yml`: Work history.
- `education.yml`: Academic background.
- `skills.yml`: Technical and professional skills.
- `projects.yml`: Personal or professional projects.
- `publications.yml`: Research papers and articles.
- `recognitions.yml`: Awards and honors.

### Configuration
Global settings and high-level resume details (name, title, contact info, section visibility) are defined in `_config.yml`.

### Layout and Styles
- **Layouts:** The main resume layout is located at `_layouts/resume.html`. It uses Liquid tags to iterate through the data in `_data/`.
- **Includes:** Reusable components (like icons and head meta) are in `_includes/`.
- **Styling:** SCSS partials are located in `_sass/`. The entry point for styles is `css/main.scss`.
- **Assets:** Custom icons (AI/SVG) are in `_assets/`, and images (avatar, screenshots) are in `images/`.

### Deployment
The project is configured for **GitHub Pages**. Pushing to the `gh-pages` branch (or `main` if configured) will trigger an automatic build and deployment. A `CNAME` file is present for custom domain support.

### CI/CD
- **Travis CI:** The project includes a `.travis.yml` configuration that runs `bundle exec jekyll build` on every push to verify the build integrity.

#### Hosting from a Private Repository
Since this repository is currently private, you have three options to make the site live:
1. **Make Repository Public:** In **Settings > Danger Zone**, change visibility to Public. GitHub Pages is free for all public repositories.
2. **Upgrade to GitHub Pro:** Paid plans allow GitHub Pages hosting from private repositories.
3. **Use External Hosting:** Connect the private repo to **Vercel** or **Netlify**, which offer free static hosting for private GitHub repositories.

#### Enabling GitHub Pages (after making Public or Upgrading)
1. Navigate to **Settings > Pages**.
2. Under **Build and deployment**, set "Source" to "Deploy from a branch".
3. Select the branch (e.g., `main` or `gh-pages`) and folder (root).
4. Click **Save** and wait for the deployment URL to appear.
