# Project Structure

Understanding the project structure is essential for effectively customizing the portfolio template. This document explains the organization of files and directories in the template.

## Directory Overview

```
├── content/
│   └── projects/          # MDX files for project descriptions
├── public/                # Static assets like images
├── src/
│   ├── app/               # App Router pages and layouts
│   ├── components/        # Reusable UI components
│   ├── config/            # Configuration files
│   ├── hooks/             # Custom React hooks
│   ├── lib/               # Utility functions and libraries
│   └── assets/            # SVG and other assets
├── next.config.ts         # Next.js configuration
└── tsconfig.json          # TypeScript configuration
```

## Content Directory

The `content/` directory contains all the dynamic content for your portfolio, primarily the project descriptions in MDX format.

### Projects

The `content/projects/` directory contains MDX files for each project in your portfolio. Each file includes:

- Frontmatter metadata (title, description, date, tags, etc.)
- MDX content for the project description

Example project file structure:
```
content/projects/
├── my-project.mdx
├── another-project.mdx
└── featured-project.mdx
```

## Public Directory

The `public/` directory contains static assets that are served directly by the web server. This includes media files for projects.

Example structure:
```
public/
├── media/
│   ├── project-1/
│   │   └── featured.png
│   └── project-2/
│       └── featured.png
```

## Src Directory

The `src/` directory contains all the source code for the application.

### App Directory

Following Next.js App Router conventions, the `src/app/` directory contains:

- Page components (`page.tsx`)
- Layout components (`layout.tsx`)
- API routes (`route.ts`)
- Special files like `not-found.tsx`

The structure follows the URL structure of the site:
```
src/app/
├── layout.tsx              # Root layout
├── page.tsx                # Home page
├── not-found.tsx           # 404 page
├── (main)/                 # Main section group
│   ├── layout.tsx          # Main section layout
│   ├── (home)/             # Home page group
│   │   ├── page.tsx        # Home page
│   │   └── components/     # Home page components
│   └── projects/           # Projects section
│       ├── page.tsx        # Projects listing page
│       ├── components/     # Projects page components
│       └── [slug]/         # Dynamic project detail pages
│           └── page.tsx    # Project detail page
└── api/                    # API routes
    ├── contact/
    │   └── route.ts        # Contact form API route
    └── projects/
        └── route.ts        # Projects API route
```

### Components Directory

The `src/components/` directory contains reusable UI components organized by function:

```
src/components/
├── layout/                 # Layout components (header, footer, etc.)
├── mdx/                    # MDX custom components
├── ui/                     # Generic UI components (buttons, inputs, etc.)
└── ...
```

### Config Directory

The `src/config/` directory contains configuration files:

- `site.ts`: Site metadata and configuration
- `email.ts`: Email configuration for the contact form

### Hooks Directory

The `src/hooks/` directory contains custom React hooks:

- `use-focus-trap.ts`: For accessibility focus management
- `use-projects-data.ts`: For fetching and managing project data

### Lib Directory

The `src/lib/` directory contains utility functions and libraries:

- `projects.ts`: Functions for fetching and processing project data
- `email.ts`: Email sending functionality
- `gsap.ts`: GSAP animation utilities
- `utils.ts`: General utility functions

### Assets Directory

The `src/assets/` directory contains static assets that are imported as modules:

- `svg/`: SVG files that can be imported as React components