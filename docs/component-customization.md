# Component Customization

This guide explains how to customize the components in the template to match your design preferences and branding.

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

The header component is located at `src/components/layout/header.tsx`. It contains your site's navigation and logo.

To customize the header:

1. Update the logo in `src/assets/svg/logo.svg` or replace it with your own
2. Modify navigation links in `src/components/layout/header.tsx`
3. Adjust styling in the component's CSS classes

### Footer

The footer component is located at `src/components/layout/footer.tsx`. It contains your name, social links, and additional navigation.

To customize the footer:

1. Update your name in `src/components/layout/footer-name.tsx`
2. Update social links in `src/components/layout/footer-social-links.tsx`
3. Modify the footer menu in `src/components/layout/footer-menu.tsx`

### Contact Section

The contact section is located at `src/components/layout/contact.tsx`. It contains the contact form and social links.

To customize the contact section:

1. Update the contact form in `src/components/layout/contact-form.tsx`
2. Update social links in `src/components/layout/contact-social-links.tsx`

## UI Components

UI components are generic, reusable components used throughout the site. They include buttons, inputs, and other interactive elements.

### Button

The button component is located at `src/components/ui/button.tsx`. It provides a consistent button style throughout the site.

To customize the button:

1. Modify the styling in `src/components/ui/button.tsx`
2. Update variants and sizes as needed

### Input and Textarea

Input and textarea components are located at `src/components/ui/input.tsx` and `src/components/ui/textarea.tsx` respectively.

To customize these components:

1. Modify the styling in the respective files
2. Update placeholder text and validation as needed

### Modal

The modal component is located at `src/components/ui/modal.tsx`. It's used for displaying popups and overlays.

To customize the modal:

1. Modify the styling in `src/components/ui/modal.tsx`
2. Update animation and positioning as needed

## MDX Components

MDX components are custom React components that can be used within MDX files. They're located in `src/components/mdx/`.

### A (Link)

The link component is located at `src/components/mdx/a.tsx`. It provides custom styling for links within MDX content.

To customize the link component:

1. Modify the styling in `src/components/mdx/a.tsx`
2. Update hover effects and animations

### ImgBox

The image box component is located at `src/components/mdx/img-box.tsx`. It's used for displaying images with captions.

To customize the ImgBox component:

1. Modify the styling in `src/components/mdx/img-box.tsx`
2. Update caption styling and positioning

### FullWidth

The full-width component is located at `src/components/mdx/full-width.tsx`. It's used for creating full-width content sections.

To customize the FullWidth component:

1. Modify the styling in `src/components/mdx/full-width.tsx`
2. Update background colors and padding

## Animation Components

The template includes several animation components for creating smooth transitions and effects.

### AnimateSlideUp

The animate slide up component is located at `src/components/ui/animate-slide-up.tsx`. It's used for animating elements as they come into view.

To customize the animation:

1. Modify the animation parameters in `src/components/ui/animate-slide-up.tsx`
2. Update easing and duration as needed

### HoverSlideUp

The hover slide up component is located at `src/components/ui/hover-slide-up.tsx`. It's used for creating hover effects on interactive elements.

To customize the hover effect:

1. Modify the styling in `src/components/ui/hover-slide-up.tsx`
2. Update animation parameters and effects

## Customizing Colors

The template uses Tailwind CSS for styling. You can customize the color palette in `tailwind.config.ts`:

```typescript
module.exports = {
  theme: {
    extend: {
      colors: {
        primary: '#your-primary-color',
        secondary: '#your-secondary-color',
        // Add more custom colors as needed
      },
    },
  },
};
```

You can then use these colors throughout your components:

```jsx
<div className="bg-primary text-white">Primary colored element</div>
```

## Customizing Typography

Typography can be customized in `tailwind.config.ts` and `src/app/globals.css`.

In `tailwind.config.ts`:

```typescript
module.exports = {
  theme: {
    extend: {
      fontFamily: {
        sans: ['Your Custom Font', 'sans-serif'],
        // Add more font families as needed
      },
    },
  },
};
```

In `src/app/globals.css`, you can define custom font imports and additional typography styles.

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

## Best Practices

1. **Consistency**: Maintain consistent styling and naming conventions across all components
2. **Reusability**: Design components to be reusable in different contexts
3. **Accessibility**: Ensure all components are accessible and follow WCAG guidelines
4. **Performance**: Optimize components for performance, especially animations
5. **Documentation**: Document complex components with comments and TypeScript interfaces