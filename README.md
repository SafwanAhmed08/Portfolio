# Safwan Ahmed — Portfolio

My personal portfolio, built with Astro and TypeScript. It brings together my AI and software projects, research, education, and professional experience, and serves as a practical project for learning CI/CD with GitHub Actions and Netlify.

## Highlights

- Groundwork, winner of the InstaLily AI track at HackTheBurgh 2026, with a dedicated project breakdown.
- Case studies for Study Planner, File Transfer & Remote Access, Remote Desktop Control, and Agentic Auto-Fine-Tuner.
- Education, internship experience, and research with links to the published papers.
- LinkedIn, GitHub, ORCID, and email contact links.
- Responsive layouts, text-based project cards, and section navigation.

This repository contains the portfolio website. The projects it showcases are separate codebases. Groundwork’s source code is coming soon.

## Stack

- **Astro 7** for static page generation
- **TypeScript** for project data
- **CSS** for styling and responsive layouts
- **GitHub Actions** for automated build checks
- **Netlify** for hosting and Git-based continuous deployment

The portfolio itself requires no API keys or backend service.

## Run locally

Use **Node.js 24** to match the CI workflow, and npm.

From the directory containing `package.json`:

```bash
npm ci
npm run dev
```

Open the local URL printed by Astro. To build and inspect the production output:

```bash
npm run build
npm run preview
```

The static site is generated in `dist/`.

## Project structure

```text
.github/workflows/ci.yml    Automated installation and build checks
public/                    Static assets and favicon
src/data/projects.ts       Project summaries and case-study content
src/layouts/Layout.astro   Shared document layout and metadata
src/pages/index.astro      Portfolio homepage
src/pages/projects/        Generated project case-study routes
src/styles/global.css      Shared styling and responsive layouts
```

Edit project details in `src/data/projects.ts`. Update the introduction, background, research, and contact content in `src/pages/index.astro`.

## CI/CD

The `Portfolio CI` workflow runs on pushes and pull requests. It checks out the repository, sets up Node.js 24, installs the locked dependencies with `npm ci`, and runs `npm run build`.

For Netlify’s Git integration, use:

| Setting | Value |
| --- | --- |
| Production branch | `master` |
| Base directory | Repository root |
| Build command | `npm run build` |
| Publish directory | `dist` |
| Node.js version | `24` |

Netlify builds and deploys separately from GitHub Actions. Requiring the CI check before merging pull requests into the production branch keeps the build check ahead of deployment. Direct pushes to the production branch can trigger deployment independently of CI.

Generated files (`dist/`, `.astro/`) and installed dependencies (`node_modules/`) are excluded from version control.

## Contact

- [LinkedIn](https://www.linkedin.com/in/safwan-ahmed-881a77287/)
- [GitHub](https://github.com/SafwanAhmed08)
- [ORCID](https://orcid.org/0009-0003-4805-9810)
