# Content Customization

This guide explains how to customize the content of your portfolio template, including personal information, site configuration, and project descriptions.

## Site Configuration

The main site configuration is located in `src/config/site.ts`. This file contains metadata about your site that is used throughout the application.

```typescript
export const siteConfig = {
  name: 'Your Name',
  description: 'Your professional description or tagline',
};
```

## Personal Information Components

Personal information is displayed in several components throughout the site:

### Header

- Update navigation links in `src/components/layout/header.tsx`.
- Update the logo in `src/assets/svg/logo.svg`
- Or modify to use text in `src/components/layout/header.tsx`. Example:

```tsx
<TransitionLink href="/">
  {/* <Logo className="h-6 w-6" /> */}
  <span className="text-base font-black leading-none tracking-tighter text-white">Fahri.</span>
</TransitionLink>
```
![Header](img/header.png)

### Footer

- Update footer text in `src/components/layout/footer.tsx`.
- Update navigation links in `src/components/layout/footer-menu.tsx`.
- Update social links in `src/components/layout/footer-social-links.tsx`.
- Update your name in `src/components/layout/footer-name.tsx`.

![Footer](img/footer.png)

### About Section

![About](img/about.png)

- Update the bio text in `src/app/(main)/(home)/components/about.tsx`
- Update experience in `src/app/(main)/(home)/components/about-experience.tsx`
- Update skills in `src/app/(main)/(home)/components/about-skills.tsx`

## Updating the Contact Form

The contact form configuration is in `src/config/email.ts`, which can be configured using environment variables, explained in the [Setup & Development](setup.md#3-environment-variables) section.

The email template can be customized in `src/lib/email.ts`.

You can also customize the contact form fields and validation in `src/components/layout/contact-form.tsx`.