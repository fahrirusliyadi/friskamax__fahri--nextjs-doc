# Deployment

This guide explains how to deploy your portfolio to various hosting platforms.

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

The template can be deployed to any hosting platform that supports Next.js. Here are the most popular options:

### Node.js Server

Next.js can be deployed to any provider that supports Node.js. This deployment option supports all Next.js features, including API routes, server components, and image optimization.

Ensure your `package.json` has the `"build"` and `"start"` scripts:

```json
{
  "scripts": {
    "dev": "next dev",
    "build": "next build",
    "start": "next start"
  }
}
```

Then, run `pnpm build` to build your application and `pnpm start` to start the Node.js server.

### Adapters

Next.js can be adapted to run on different platforms to support their infrastructure capabilities.

Refer to each provider's documentation for information on supported Next.js features:

- [AWS Amplify Hosting](https://docs.amplify.aws/nextjs/start/quickstart/nextjs-app-router-client-components)
- [Cloudflare](https://developers.cloudflare.com/workers/frameworks/framework-guides/nextjs)
- [Deno Deploy](https://docs.deno.com/examples/next_tutorial)
- [Netlify](https://docs.netlify.com/frameworks/next-js/overview/#next-js-support-on-netlify)
- [Vercel](https://vercel.com/docs/frameworks/nextjs)


## Environment Variables

When deploying to production, make sure to the environment variables descibed in [Setup & Development](setup.md#3-environment-variables) section. These should be configured in your hosting platform's dashboard or deployment settings.

## Domain Configuration

Most hosting platforms allow you to configure custom domains:

1. Purchase a domain from a registrar (or use an existing one)
2. Configure DNS settings to point to your hosting platform
3. Add the domain to your hosting platform's dashboard
4. Configure SSL certificates (usually automatic)

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
