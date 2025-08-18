# Setup and Development Environment

This guide will help you set up the development environment for the Next.js Portfolio Template and start customizing it for your needs.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Node.js (version 18 or higher)
- pnpm (package manager)
- Git

### Installing Node.js

You can download Node.js from the official website: https://nodejs.org/

Alternatively, you can use a version manager like `nvm` (Node Version Manager) to install and manage multiple Node.js versions:

```bash
# Install nvm (if not already installed)
curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.0/install.sh | bash

# Install the latest LTS version of Node.js
nvm install --lts
nvm use --lts
```

### Installing pnpm

The template uses pnpm as the package manager. You can install it globally using npm:

```bash
npm install -g pnpm
```

## Getting Started

### 1. Clone the Repository

First, clone the repository to your local machine:

```bash
git clone <repository-url>
cd <repository-name>
```

### 2. Install Dependencies

Install the project dependencies using pnpm:

```bash
pnpm install
```

### 3. Environment Variables

The template uses environment variables for certain features like the contact form. Create a `.env.local` file in the root directory and add the following variables:

```env
SMTP_HOST=your-smtp-host
SMTP_PORT=your-smtp-port
SMTP_USER=your-smtp-username
SMTP_PASSWORD=your-smtp-password
SMTP_FROM_EMAIL=your-from-email
SMTP_TO_EMAIL=your-to-email
```

For development, you can use a service like [Mailtrap](https://mailtrap.io/) to test email functionality without sending actual emails.

### 4. Development Server

Start the development server:

```bash
pnpm dev
```

The site will be available at http://localhost:3000

### 5. Build for Production

To build the site for production:

```bash
pnpm build
```

### 6. Start Production Server

To start the production server locally:

```bash
pnpm start
```

## Development Workflow

### Code Structure

The template follows a standard Next.js App Router structure with additional directories for content and components. Key directories include:

- `src/app/`: Contains page components and layouts
- `content/projects/`: Contains MDX files for project descriptions
- `src/components/`: Contains reusable UI components
- `public/`: Contains static assets

### Styling

The template uses Tailwind CSS for styling. You can customize the theme in `tailwind.config.ts`. Global styles are defined in `src/app/globals.css`.

### Linting and Formatting

The template includes ESLint and Prettier for code quality and formatting. You can run the linter with:

```bash
pnpm lint
```

To fix linting issues automatically:

```bash
pnpm lint --fix
```

### Git Hooks

The template uses Husky for Git hooks to ensure code quality. Pre-commit hooks will automatically run the linter and formatter on staged files.

## Customizing the Template

### Site Configuration

Update your site information in `src/config/site.ts`:

```typescript
export const siteConfig = {
  name: 'Your Name',
  url: 'https://your-website.com',
  description: 'Your professional description',
  author: 'Your Name',
  keywords: ['designer', 'developer', 'portfolio'],
};
```

### Email Configuration

Update email settings in `src/config/email.ts`:

```typescript
export const emailConfig = {
  from: 'your-email@example.com',
  to: 'recipient@example.com',
};
```

## Troubleshooting

### Common Issues

1. **Dependency Installation Errors**: If you encounter errors during `pnpm install`, try clearing the cache:
   ```bash
   pnpm cache clean
   pnpm install
   ```

2. **Port Conflicts**: If port 3000 is already in use, you can specify a different port:
   ```bash
   pnpm dev --port 3001
   ```

3. **Build Errors**: If you encounter build errors, ensure all dependencies are installed correctly and check the terminal for specific error messages.

### Getting Help

If you encounter issues not covered in this guide, you can:

1. Check the [Next.js documentation](https://nextjs.org/docs)
2. Search for solutions in the project's GitHub issues
3. Consult the documentation for specific libraries used in the template