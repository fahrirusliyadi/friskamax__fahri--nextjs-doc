# Deployment

This guide explains how to deploy your Next.js Portfolio Template to various hosting platforms.

## Building for Production

Before deploying, you need to build your application for production. Run the following command:

```bash
pnpm build
```

This will create an optimized production build in the `.next` directory.

To start the production server locally for testing:

```bash
pnpm start
```

## Deployment Options

The Next.js Portfolio Template can be deployed to any hosting platform that supports Next.js. Here are the most popular options:

### Vercel (Recommended)

Vercel is the creators of Next.js and provides the best experience for deploying Next.js applications.

1. Push your code to a Git repository (GitHub, GitLab, or Bitbucket)
2. Sign up for a Vercel account at https://vercel.com
3. Click "New Project" and import your repository
4. Vercel will automatically detect the Next.js framework and configure the build settings
5. Add environment variables if needed
6. Click "Deploy" and your site will be live

Vercel automatically handles:
- Building your application
- Optimizing for performance
- Setting up SSL certificates
- Configuring CDN distribution

### Netlify

Netlify is another popular hosting platform that supports Next.js applications.

1. Push your code to a Git repository
2. Sign up for a Netlify account at https://netlify.com
3. Click "New site from Git" and connect your repository
4. Configure the build settings:
   - Build command: `pnpm build`
   - Publish directory: `.next`
5. Add environment variables in the Netlify dashboard
6. Click "Deploy site"

Note: You may need to configure additional settings for Next.js on Netlify, such as installing the `@netlify/plugin-nextjs` plugin.

### GitHub Pages

You can deploy your Next.js application to GitHub Pages, but it requires some additional configuration.

1. Install the `gh-pages` package:
   ```bash
   pnpm add gh-pages --save-dev
   ```

2. Add deployment scripts to your `package.json`:
   ```json
   {
     "scripts": {
       "predeploy": "pnpm build",
       "deploy": "gh-pages -d .next"
     }
   }
   ```

3. Configure Next.js for GitHub Pages by updating `next.config.ts`:
   ```typescript
   const nextConfig = {
     output: 'export',
     // Add other configuration options as needed
   };
   
   export default nextConfig;
   ```

4. Run the deployment command:
   ```bash
   pnpm deploy
   ```

Note: GitHub Pages deployment has some limitations with Next.js features like API routes.

### Other Hosting Platforms

You can also deploy to other platforms like:

- **Railway**
- **Render**
- **Heroku**
- **DigitalOcean App Platform**

Each platform has its own deployment process, but generally involves:

1. Building the application with `pnpm build`
2. Serving the `.next` directory
3. Configuring environment variables

## Environment Variables

When deploying to production, make sure to set the following environment variables:

```env
SMTP_HOST=your-production-smtp-host
SMTP_PORT=your-production-smtp-port
SMTP_USER=your-production-smtp-username
SMTP_PASSWORD=your-production-smtp-password
SMTP_FROM_EMAIL=your-production-from-email
SMTP_TO_EMAIL=your-production-to-email
```

These should be configured in your hosting platform's dashboard or deployment settings.

## Domain Configuration

Most hosting platforms allow you to configure custom domains:

1. Purchase a domain from a registrar (or use an existing one)
2. Configure DNS settings to point to your hosting platform
3. Add the domain to your hosting platform's dashboard
4. Configure SSL certificates (usually automatic)

For Vercel:
1. Go to your project settings
2. Click "Domains"
3. Add your custom domain
4. Follow the DNS configuration instructions

## Performance Optimization

To ensure optimal performance in production:

1. **Image Optimization**: The template uses Next.js Image component for optimization
2. **Code Splitting**: Next.js automatically splits code for faster loading
3. **Caching**: Configure caching headers in your hosting platform
4. **Compression**: Most hosting platforms automatically compress assets

## Monitoring and Analytics

Consider adding monitoring and analytics to your production site:

### Google Analytics

1. Create a Google Analytics property
2. Add the GA tracking code to your site using `@next/third-parties`:

```bash
pnpm add @next/third-parties
```

3. Update `src/app/layout.tsx`:

```tsx
import { GoogleAnalytics } from '@next/third-parties/google';

export default function RootLayout({
  children,
}: {
  children: React.ReactNode;
}) {
  return (
    <html lang="en">
      <body>
        {children}
        <GoogleAnalytics gaId="G-XXXXXXXXXX" />
      </body>
    </html>
  );
}
```

### Error Tracking

Consider adding error tracking with services like:

- Sentry
- LogRocket
- Rollbar

## Troubleshooting Deployment Issues

### Common Issues

1. **Build Failures**: Check the build logs for specific error messages
2. **Environment Variables**: Ensure all required environment variables are set
3. **Asset Loading**: Check that all images and assets are correctly referenced
4. **API Routes**: Verify that API routes are working correctly

### Debugging Steps

1. Test the production build locally with `pnpm build` and `pnpm start`
2. Check browser console for JavaScript errors
3. Verify all links and images are working
4. Test the contact form functionality

### Getting Help

If you encounter deployment issues:

1. Check the documentation for your hosting platform
2. Review the Next.js deployment documentation: https://nextjs.org/docs/app/building-your-application/deploying
3. Search for solutions in community forums
4. Contact your hosting platform's support team