# Component Customization

This guide explains how to customize the components in the template.

## Component Structure

The template uses a component-driven approach with reusable components organized in the `src/components/` directory:

```
src/components/
├── layout/                 # Layout components (header, footer, etc.)
├── mdx/                    # MDX custom components
├── ui/                     # Generic UI components (buttons, inputs, etc.)
└── ...
```

## Layout Components

Layout components form the structure of your site and include the header, footer, and contact section.

### Header

The header component is located at `src/components/layout/header.tsx`.

To customize the header:

- Update the logo in `src/assets/svg/logo.svg` or replace it with your own
- Modify navigation links in `src/components/layout/header.tsx`
- Adjust styling in the component's CSS classes

You can also use text instead of the logo in `src/components/layout/header.tsx`. Example:

```tsx
<TransitionLink href="/">
  {/* <Logo className="h-6 w-6" /> */}
  <span className="text-base font-black leading-none tracking-tighter text-white">Fahri.</span>
</TransitionLink>
```
![Header](img/header.png)

### Footer

The footer component is located at `src/components/layout/footer.tsx`.

To customize the footer:

- Modify the footer menu in `src/components/layout/footer-menu.tsx`.
- Update social links in `src/components/layout/footer-social-links.tsx`.
- Update your name in `src/components/layout/footer-name.tsx`.

### Contact Section

The contact section is located at `src/components/layout/contact.tsx`.

To customize the contact section:

1. Update the contact form in `src/components/layout/contact-form.tsx`
2. Update social links in `src/components/layout/contact-social-links.tsx`

## UI Components

UI components are generic, reusable components used throughout the site. They include buttons, inputs, and other interactive elements.

### Button

The button component is located at `src/components/ui/button.tsx`. It provides a consistent button style throughout the site.


### Input and Textarea

Input and textarea components are located at `src/components/ui/input.tsx` and `src/components/ui/textarea.tsx` respectively.

### Modal

The modal component is located at `src/components/ui/modal.tsx`. It's used for displaying popups and overlays.

## MDX Components

MDX components are custom React components that can be used within MDX files. They're located in `src/components/mdx/`.

### A (Link)

The link component is located at `src/components/mdx/a.tsx`. It provides custom styling for links within MDX content.

### Img

The image component is located at `src/components/mdx/img.tsx`. It's used for displaying images with scroll-triggered animations.

### ImgBox

The image box component is located at `src/components/mdx/img-box.tsx`. It's used for displaying images as boxes with scroll-triggered animations.

### FullWidth

The full-width component is located at `src/components/mdx/full-width.tsx`. It's used for creating full-width content sections.

### Adding Custom MDX Components

To add your own custom MDX components:

1. Create a new component file in `src/components/mdx/` with a `.tsx` extension
2. Implement your component using React and TypeScript
3. Export the component as the default export
4. Register your component in `src/components/mdx/index.tsx`

Example of a custom MDX component:

```tsx
// src/components/mdx/custom-card.tsx
import React from 'react';

interface CustomCardProps {
  title: string;
  description: string;
  children?: React.ReactNode;
}

const CustomCard: React.FC<CustomCardProps> = ({ title, description, children }) => {
  return (
    <div className="border rounded-lg p-6 shadow-sm bg-white">
      <h3 className="text-xl font-bold mb-2">{title}</h3>
      <p className="text-gray-600 mb-4">{description}</p>
      {children && <div className="mt-4">{children}</div>}
    </div>
  );
};

export default CustomCard;
```

Register the component in `src/components/mdx/index.tsx`:

```tsx
import { MDXComponents } from 'mdx/types';
import A from './a';
import FullWidth from './full-width';
import Img from './img';
import ImgBox from './img-box';
import CustomCard from './custom-card'; // Add this import

export const components: MDXComponents = {
  a: A,
  Img,
  ImgBox,
  FullWidth,
  CustomCard, // Add this line to register the component
};
```

Now you can use your custom component in any MDX file:

```mdx
## My Project Details

<CustomCard title="Project Highlights" description="Key features of this project">
  - Feature one
  - Feature two
  - Feature three
</CustomCard>
```

## Animation Components

The template includes several animation components for creating smooth transitions and effects.

### AnimateSlideUp

The animate slide up component is located at `src/components/ui/animate-slide-up.tsx`. It's used for animating multiple text items that slide up from the bottom one by one.

### HoverSlideUp

The hover slide up component is located at `src/components/ui/hover-slide-up.tsx`. It's used for creating hover effects on interactive elements.

## Adding New Components

To add new components to your portfolio:

1. Create a new file in the appropriate directory under `src/components/`
2. Define your component using React and TypeScript
3. Export the component for use in other parts of the application
4. Import and use the component in your pages or other components

Example of a new component:

```tsx
// src/components/ui/my-custom-component.tsx
import React from 'react';

interface MyCustomComponentProps {
  title: string;
  description: string;
}

const MyCustomComponent: React.FC<MyCustomComponentProps> = ({ title, description }) => {
  return (
    <div className="bg-gray-100 p-4 rounded-lg">
      <h3 className="text-xl font-bold">{title}</h3>
      <p className="mt-2">{description}</p>
    </div>
  );
};

export default MyCustomComponent;
```

Then use it in your pages:

```tsx
// In a page or other component
import MyCustomComponent from '@/components/ui/my-custom-component';

<MyCustomComponent title="My Title" description="My description" />
```
