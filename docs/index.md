# Next.js Portfolio Template Documentation

Welcome to the documentation for the Next.js Portfolio Template. This template is designed to help developers and designers create a professional portfolio website with minimal setup.

## Features

- **Modern Tech Stack**: Built with Next.js 15, React 19, TypeScript, and Tailwind CSS
- **MDX Support**: Write content in MDX format for rich, interactive project descriptions
- **Responsive Design**: Fully responsive layout that works on all device sizes
- **Performance Optimized**: Optimized for speed and SEO
- **Easy Customization**: Simple to customize colors, content, and layout
- **Project Showcase**: Dedicated sections for displaying your projects with tags and filtering
- **Contact Form**: Built-in contact form with email integration
- **Dark Mode**: Automatic dark mode based on system preferences

## Getting Started

To get started with this template, follow these steps:

1. Clone the repository
2. Install dependencies with `pnpm install`
3. Start the development server with `pnpm dev`
4. Open [http://localhost:3000](http://localhost:3000) in your browser

## Project Structure

The portfolio template follows a standard Next.js App Router structure with additional directories for content and components:

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
├── tailwind.config.ts     # Tailwind CSS configuration
└── tsconfig.json          # TypeScript configuration
```

## Customizing Content

### Personal Information

Update your personal information in `src/config/site.ts`:

```typescript
export const siteConfig = {
  name: 'Your Name',
  url: 'https://your-website.com',
  description: 'Your professional description',
  author: 'Your Name',
  keywords: ['designer', 'developer', 'portfolio'],
};
```

### Adding Projects

Projects are stored as MDX files in the `content/projects/` directory. Each project file contains frontmatter metadata and MDX content. See the "Adding New Projects" section for details.

### Customizing Components

The template uses a component-driven approach with reusable components in the `src/components/` directory. You can customize these components to match your design preferences.

## Deployment

The template can be deployed to any hosting platform that supports Next.js, such as Vercel, Netlify, or GitHub Pages. See the "Deployment" section for detailed instructions.
