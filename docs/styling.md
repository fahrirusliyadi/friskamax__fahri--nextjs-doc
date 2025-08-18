# Styling and Theme Customization

This guide explains how to customize the styling and theme of your portfolio.

## Global Styles

Global styles are defined in `src/app/globals.css`. This file contains:

1. Tailwind CSS directives
2. Custom CSS variables
3. Global utility classes

```css
@tailwind base;
@tailwind components;
@tailwind utilities;

:root {
  --foreground-rgb: 0, 0, 0;
  --background-start-rgb: 214, 219, 220;
  --background-end-rgb: 255, 255, 255;
}

@media (prefers-color-scheme: dark) {
  :root {
    --foreground-rgb: 255, 255, 255;
    --background-start-rgb: 0, 0, 0;
    --background-end-rgb: 0, 0, 0;
  }
}

body {
  color: rgb(var(--foreground-rgb));
  background: linear-gradient(
      to bottom,
      transparent,
      rgb(var(--background-end-rgb))
    )
    rgb(var(--background-start-rgb));
}
```

To customize global styles:

1. Add custom CSS variables to the `:root` selector
2. Modify existing variables to change color schemes
3. Add new global utility classes

## Tailwind CSS Configuration

Tailwind CSS configuration is located in `tailwind.config.ts`. This file allows you to:

1. Customize the color palette
2. Extend spacing and sizing scales
3. Add custom fonts
4. Configure plugins

```typescript
import type { Config } from 'tailwindcss';

const config: Config = {
  content: [
    './src/pages/**/*.{js,ts,jsx,tsx,mdx}',
    './src/components/**/*.{js,ts,jsx,tsx,mdx}',
    './src/app/**/*.{js,ts,jsx,tsx,mdx}',
  ],
  theme: {
    extend: {
      backgroundImage: {
        'gradient-radial': 'radial-gradient(var(--tw-gradient-stops))',
        'gradient-conic':
          'conic-gradient(from 180deg at 50% 50%, var(--tw-gradient-stops))',
      },
    },
  },
  plugins: [
    require('@tailwindcss/typography'),
  ],
};

export default config;
```

### Customizing Colors

To add custom colors to your palette:

```typescript
const config: Config = {
  theme: {
    extend: {
      colors: {
        primary: '#3b82f6',
        secondary: '#10b981',
        accent: '#f59e0b',
      },
    },
  },
};
```

Then use them in your components:

```jsx
<div className="bg-primary text-white">Primary colored element</div>
```

### Customizing Typography

To customize typography:

```typescript
const config: Config = {
  theme: {
    extend: {
      fontFamily: {
        sans: ['Inter', 'sans-serif'],
        serif: ['Playfair Display', 'serif'],
      },
      fontSize: {
        'xxs': '0.625rem',
        'xxl': '1.75rem',
      },
    },
  },
};
```

### Adding Plugins

To add Tailwind CSS plugins:

1. Install the plugin:
   ```bash
   pnpm add @tailwindcss/forms
   ```

2. Add it to the plugins array:
   ```typescript
   plugins: [
     require('@tailwindcss/typography'),
     require('@tailwindcss/forms'),
   ],
   ```

## Dark Mode

The template includes built-in dark mode support using Tailwind CSS and CSS variables. The dark mode is controlled by:

1. CSS variables in `src/app/globals.css`
2. Tailwind CSS configuration
3. System preference detection

To customize dark mode:

1. Modify the color variables in the `@media (prefers-color-scheme: dark)` section
2. Add custom dark mode styles using the `dark:` variant in Tailwind CSS

Example of dark mode styling:

```jsx
<div className="bg-white dark:bg-gray-900 text-black dark:text-white">
  Content that changes color in dark mode
</div>
```

## Responsive Design

The template is fully responsive using Tailwind CSS responsive utilities. The breakpoints are:

- `sm`: 640px
- `md`: 768px
- `lg`: 1024px
- `xl`: 1280px
- `2xl`: 1536px

To customize responsive behavior:

1. Use responsive prefixes in Tailwind CSS classes:
   ```jsx
   <div className="text-sm md:text-base lg:text-lg">
     Responsive text size
   </div>
   ```

2. Add custom breakpoints in `tailwind.config.ts`:
   ```typescript
   theme: {
     screens: {
       'tablet': '640px',
       'laptop': '1024px',
       'desktop': '1280px',
     },
   },
   ```

## Custom Animations

The template uses GSAP for animations. Custom animations are defined in:

1. `src/lib/gsap.ts`: GSAP utility functions
2. Component-specific animation files

To add custom animations:

1. Create animation functions in `src/lib/gsap.ts` or in component files
2. Use GSAP methods like `gsap.from()`, `gsap.to()`, etc.
3. Trigger animations with React hooks like `useEffect`

Example of a custom animation:

```typescript
import { useEffect } from 'react';
import gsap from 'gsap';

const MyComponent = () => {
  useEffect(() => {
    gsap.from('.my-element', {
      opacity: 0,
      y: 20,
      duration: 0.5,
      delay: 0.2,
    });
  }, []);

  return <div className="my-element">Animated element</div>;
};
```

## Best Practices

1. **Consistency**: Maintain consistent styling across all components
2. **Performance**: Optimize CSS and avoid unnecessary styles
3. **Accessibility**: Ensure sufficient color contrast and readable font sizes
4. **Mobile-First**: Design for mobile devices first, then enhance for larger screens
5. **CSS Variables**: Use CSS variables for consistent theming
6. **Tailwind Utilities**: Leverage Tailwind's utility classes for rapid development