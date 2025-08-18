# Setup and Development Environment

This guide will help you set up the development environment for the template and start customizing it for your needs.

## Prerequisites

Before you begin, ensure you have the following installed on your system:

- Node.js (version 18 or higher)
- pnpm (package manager)

### Installing Node.js

You can download Node.js from the official website: [https://nodejs.org/](https://nodejs.org/)


### Installing pnpm

The template uses pnpm as the package manager. You can install it globally using npm:

```bash
npm install -g pnpm
```

## Getting Started

### 1. Enter the Template Directory

First, extract the template from the zip file. You will get a folder named `fahri` (the template folder) and `documentation` (the documentation folder). Enter the template directory:

```bash
cd path/to/fahri
```

### 2. Install Dependencies

Install the project dependencies using pnpm:

```bash
pnpm install
```

### 3. Environment Variables

The template uses environment variables for certain features like the contact form. Create a `.env.local` file in the root directory and add the following variables:

The following variables should be added:

- `SMTP_HOST`: The hostname of your SMTP server (e.g., `smtp.gmail.com`)
- `SMTP_PORT`: The port of your SMTP server (e.g., `587` for TLS, `465` for SSL)
- `SMTP_USER`: The username for authenticating with your SMTP server
- `SMTP_PASSWORD`: The password for authenticating with your SMTP server
- `SMTP_FROM_EMAIL`: The email address from which emails will be sent
- `SMTP_TO_EMAIL`: The recipient email address for contact form submissions

Example:

```env
SMTP_HOST=sandbox.smtp.mailtrap.io
SMTP_PORT=587
SMTP_USER=xxx
SMTP_PASSWORD=xxx
SMTP_FROM_EMAIL=contact@example.com
SMTP_TO_EMAIL=me@example.com
```

For development, you can use a service like [Mailtrap](https://mailtrap.io/) to test email functionality without sending actual emails. This helps in verifying email functionality without sending actual emails to recipients.

### 4. Development Server

Start the development server:

```bash
pnpm dev
```

The site will be available at [http://localhost:3000](http://localhost:3000)

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

### Styling

The template uses Tailwind CSS for styling. You can customize it in `src/app/globals.css`.

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

## Troubleshooting

### Common Issues

1. **Dependency Installation Errors**: If you encounter errors during `pnpm install`, try clearing the cache: `pnpm store prune && pnpm install`

2. **Port Conflicts**: If port 3000 is already in use, you can specify a different port: `pnpm dev --port 3001`

3. **Build Errors**: If you encounter build errors, ensure all dependencies are installed correctly and check the terminal for specific error messages.

### Getting Help

If you encounter issues not covered in this guide, you can:

1. Check the [Next.js documentation](https://nextjs.org/docs)
2. Consult the documentation for specific libraries used in the template
3. Send us a message on [ThemeForest](https://themeforest.net/user/friskamax)
