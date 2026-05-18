# Logs
logs
*.log
npm-debug.log*
yarn-debug.log*
yarn-error.log*
pnpm-debug.log*
lerna-debug.log*

node_modules
dist
dist-ssr
*.local

# Editor directories and files
.vscode/*
!.vscode/extensions.json
.idea
.DS_Store
*.suo
*.ntvs*
*.njsproj
*.sln
*.sw?



================================================================================
FILE: app/README.md
================================================================================

# React + TypeScript + Vite

This template provides a minimal setup to get React working in Vite with HMR and some ESLint rules.

Currently, two official plugins are available:

- [@vitejs/plugin-react](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react) uses [Babel](https://babeljs.io/) (or [oxc](https://oxc.rs) when used in [rolldown-vite](https://vite.dev/guide/rolldown)) for Fast Refresh
- [@vitejs/plugin-react-swc](https://github.com/vitejs/vite-plugin-react/blob/main/packages/plugin-react-swc) uses [SWC](https://swc.rs/) for Fast Refresh

## React Compiler

The React Compiler is not enabled on this template because of its impact on dev & build performances. To add it, see [this documentation](https://react.dev/learn/react-compiler/installation).

## Expanding the ESLint configuration

If you are developing a production application, we recommend updating the configuration to enable type-aware lint rules:

```js
export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...

      // Remove tseslint.configs.recommended and replace with this
      tseslint.configs.recommendedTypeChecked,
      // Alternatively, use this for stricter rules
      tseslint.configs.strictTypeChecked,
      // Optionally, add this for stylistic rules
      tseslint.configs.stylisticTypeChecked,

      // Other configs...
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```

You can also install [eslint-plugin-react-x](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-x) and [eslint-plugin-react-dom](https://github.com/Rel1cx/eslint-react/tree/main/packages/plugins/eslint-plugin-react-dom) for React-specific lint rules:

```js
// eslint.config.js
import reactX from 'eslint-plugin-react-x'
import reactDom from 'eslint-plugin-react-dom'

export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      // Other configs...
      // Enable lint rules for React
      reactX.configs['recommended-typescript'],
      // Enable lint rules for React DOM
      reactDom.configs.recommended,
    ],
    languageOptions: {
      parserOptions: {
        project: ['./tsconfig.node.json', './tsconfig.app.json'],
        tsconfigRootDir: import.meta.dirname,
      },
      // other options...
    },
  },
])
```



================================================================================
FILE: app/components.json
================================================================================

{
  "$schema": "https://ui.shadcn.com/schema.json",
  "style": "new-york",
  "rsc": false,
  "tsx": true,
  "tailwind": {
    "config": "postcss.config.js",
    "css": "src/index.css",
    "baseColor": "slate",
    "cssVariables": true,
    "prefix": ""
  },
  "iconLibrary": "lucide",
  "aliases": {
    "components": "@/components",
    "utils": "@/lib/utils",
    "ui": "@/components/ui",
    "lib": "@/lib",
    "hooks": "@/hooks"
  },
  "registries": {}
}



================================================================================
FILE: app/eslint.config.js
================================================================================

import js from '@eslint/js'
import globals from 'globals'
import reactHooks from 'eslint-plugin-react-hooks'
import reactRefresh from 'eslint-plugin-react-refresh'
import tseslint from 'typescript-eslint'
import { defineConfig, globalIgnores } from 'eslint/config'

export default defineConfig([
  globalIgnores(['dist']),
  {
    files: ['**/*.{ts,tsx}'],
    extends: [
      js.configs.recommended,
      tseslint.configs.recommended,
      reactHooks.configs.flat.recommended,
      reactRefresh.configs.vite,
    ],
    languageOptions: {
      ecmaVersion: 2020,
      globals: globals.browser,
    },
  },
])



================================================================================
FILE: app/index.html
================================================================================

<!doctype html>
<html lang="en">
  <head>
    <meta charset="UTF-8" />
    <meta name="viewport" content="width=device-width, initial-scale=1.0" />
    <title>Flight Platform</title>
  </head>
  <body>
    <div id="root"></div>
    <script type="module" src="/src/main.tsx"></script>
  </body>
</html>



================================================================================
FILE: app/info.md
================================================================================

Using Node.js 20, Tailwind CSS v3.4.19, and Vite v7.2.4

Tailwind CSS has been set up with the shadcn theme

Setup complete: /mnt/agents/output/app

Components (40+):
  accordion, alert-dialog, alert, aspect-ratio, avatar, badge, breadcrumb,
  button-group, button, calendar, card, carousel, chart, checkbox, collapsible,
  command, context-menu, dialog, drawer, dropdown-menu, empty, field, form,
  hover-card, input-group, input-otp, input, item, kbd, label, menubar,
  navigation-menu, pagination, popover, progress, radio-group, resizable,
  scroll-area, select, separator, sheet, sidebar, skeleton, slider, sonner,
  spinner, switch, table, tabs, textarea, toggle-group, toggle, tooltip

Usage:
  import { Button } from '@/components/ui/button'
  import { Card, CardHeader, CardTitle } from '@/components/ui/card'

Structure:
  src/sections/        Page sections
  src/hooks/           Custom hooks
  src/types/           Type definitions
  src/App.css          Styles specific to the Webapp
  src/App.tsx          Root React component
  src/index.css        Global styles
  src/main.tsx         Entry point for rendering the Webapp
  index.html           Entry point for the Webapp
  tailwind.config.js   Configures Tailwind's theme, plugins, etc.
  vite.config.ts       Main build and dev server settings for Vite
  postcss.config.js    Config file for CSS post-processing tools


================================================================================
FILE: app/package-lock.json
================================================================================

{
  "name": "my-app",
  "version": "0.0.0",
  "lockfileVersion": 3,
  "requires": true,
  "packages": {
    "": {
      "name": "my-app",
      "version": "0.0.0",
      "dependencies": {
        "@hookform/resolvers": "^5.2.2",
        "@radix-ui/react-accordion": "^1.2.12",
        "@radix-ui/react-alert-dialog": "^1.1.15",
        "@radix-ui/react-aspect-ratio": "^1.1.8",
        "@radix-ui/react-avatar": "^1.1.11",
        "@radix-ui/react-checkbox": "^1.3.3",
        "@radix-ui/react-collapsible": "^1.1.12",
        "@radix-ui/react-context-menu": "^2.2.16",
        "@radix-ui/react-dialog": "^1.1.15",
        "@radix-ui/react-dropdown-menu": "^2.1.16",
        "@radix-ui/react-hover-card": "^1.1.15",
        "@radix-ui/react-label": "^2.1.8",
        "@radix-ui/react-menubar": "^1.1.16",
        "@radix-ui/react-navigation-menu": "^1.2.14",
        "@radix-ui/react-popover": "^1.1.15",
        "@radix-ui/react-progress": "^1.1.8",
        "@radix-ui/react-radio-group": "^1.3.8",
        "@radix-ui/react-scroll-area": "^1.2.10",
        "@radix-ui/react-select": "^2.2.6",
        "@radix-ui/react-separator": "^1.1.8",
        "@radix-ui/react-slider": "^1.3.6",
        "@radix-ui/react-slot": "^1.2.4",
        "@radix-ui/react-switch": "^1.2.6",
        "@radix-ui/react-tabs": "^1.1.13",
        "@radix-ui/react-toggle": "^1.1.10",
        "@radix-ui/react-toggle-group": "^1.1.11",
        "@radix-ui/react-tooltip": "^1.2.8",
        "@types/three": "^0.184.1",
        "class-variance-authority": "^0.7.1",
        "clsx": "^2.1.1",
        "cmdk": "^1.1.1",
        "date-fns": "^4.1.0",
        "embla-carousel-react": "^8.6.0",
        "gsap": "^3.15.0",
        "input-otp": "^1.4.2",
        "lucide-react": "^0.562.0",
        "next-themes": "^0.4.6",
        "react": "^19.2.0",
        "react-day-picker": "^9.13.0",
        "react-dom": "^19.2.0",
        "react-hook-form": "^7.70.0",
        "react-resizable-panels": "^4.2.2",
        "react-router": "^7.6.1",
        "react-router-dom": "^7.15.1",
        "recharts": "^2.15.4",
        "sonner": "^2.0.7",
        "tailwind-merge": "^3.4.0",
        "three": "^0.184.0",
        "vaul": "^1.1.2",
        "zod": "^4.3.5"
      },
      "devDependencies": {
        "@eslint/js": "^9.39.1",
        "@types/node": "^24.10.1",
        "@types/react": "^19.2.5",
        "@types/react-dom": "^19.2.3",
        "@vitejs/plugin-react": "^5.1.1",
        "autoprefixer": "^10.4.23",
        "eslint": "^9.39.1",
        "eslint-plugin-react-hooks": "^7.0.1",
        "eslint-plugin-react-refresh": "^0.4.24",
        "globals": "^16.5.0",
        "kimi-plugin-inspect-react": "^1.0.3",
        "postcss": "^8.5.6",
        "tailwindcss": "^3.4.19",
        "tailwindcss-animate": "^1.0.7",
        "tw-animate-css": "^1.4.0",
        "typescript": "~5.9.3",
        "typescript-eslint": "^8.46.4",
        "vite": "^7.2.4"
      }
    },
    "node_modules/@alloc/quick-lru": {
      "version": "5.2.0",
      "resolved": "https://registry.npmjs.org/@alloc/quick-lru/-/quick-lru-5.2.0.tgz",
      "integrity": "sha512-UrcABB+4bUrFABwbluTIBErXwvbsU/V7TZWfmbgJfbkwiBuziS9gxdODUyuiecfdGQ85jglMW6juS3+z5TsKLw==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=10"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/@babel/code-frame": {
      "version": "7.29.0",
      "resolved": "https://registry.npmmirror.com/@babel/code-frame/-/code-frame-7.29.0.tgz",
      "integrity": "sha512-9NhCeYjq9+3uxgdtp20LSiJXJvN0FeCtNGpJxuMFZ1Kv3cWUNb6DOhJwUvcVCzKGR66cw4njwM6hrJLqgOwbcw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-validator-identifier": "^7.28.5",
        "js-tokens": "^4.0.0",
        "picocolors": "^1.1.1"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/compat-data": {
      "version": "7.29.3",
      "resolved": "https://registry.npmmirror.com/@babel/compat-data/-/compat-data-7.29.3.tgz",
      "integrity": "sha512-LIVqM46zQWZhj17qA8wb4nW/ixr2y1Nw+r1etiAWgRM6U1IqP+LNhL1yg440jYZR72jCWcWbLWzIosH+uP1fqg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/core": {
      "version": "7.28.5",
      "resolved": "https://registry.npmjs.org/@babel/core/-/core-7.28.5.tgz",
      "integrity": "sha512-e7jT4DxYvIDLk1ZHmU/m/mB19rex9sv0c2ftBtjSBv+kVM/902eh0fINUzD7UwLLNR+jU585GxUJ8/EBfAM5fw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/code-frame": "^7.27.1",
        "@babel/generator": "^7.28.5",
        "@babel/helper-compilation-targets": "^7.27.2",
        "@babel/helper-module-transforms": "^7.28.3",
        "@babel/helpers": "^7.28.4",
        "@babel/parser": "^7.28.5",
        "@babel/template": "^7.27.2",
        "@babel/traverse": "^7.28.5",
        "@babel/types": "^7.28.5",
        "@jridgewell/remapping": "^2.3.5",
        "convert-source-map": "^2.0.0",
        "debug": "^4.1.0",
        "gensync": "^1.0.0-beta.2",
        "json5": "^2.2.3",
        "semver": "^6.3.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/babel"
      }
    },
    "node_modules/@babel/generator": {
      "version": "7.29.1",
      "resolved": "https://registry.npmmirror.com/@babel/generator/-/generator-7.29.1.tgz",
      "integrity": "sha512-qsaF+9Qcm2Qv8SRIMMscAvG4O3lJ0F1GuMo5HR/Bp02LopNgnZBC/EkbevHFeGs4ls/oPz9v+Bsmzbkbe+0dUw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/parser": "^7.29.0",
        "@babel/types": "^7.29.0",
        "@jridgewell/gen-mapping": "^0.3.12",
        "@jridgewell/trace-mapping": "^0.3.28",
        "jsesc": "^3.0.2"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-annotate-as-pure": {
      "version": "7.27.3",
      "resolved": "https://registry.npmmirror.com/@babel/helper-annotate-as-pure/-/helper-annotate-as-pure-7.27.3.tgz",
      "integrity": "sha512-fXSwMQqitTGeHLBC08Eq5yXz2m37E4pJX1qAU1+2cNedz/ifv/bVXft90VeSav5nFO61EcNgwr0aJxbyPaWBPg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/types": "^7.27.3"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-compilation-targets": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/helper-compilation-targets/-/helper-compilation-targets-7.28.6.tgz",
      "integrity": "sha512-JYtls3hqi15fcx5GaSNL7SCTJ2MNmjrkHXg4FSpOA/grxK8KwyZ5bubHsCq8FXCkua6xhuaaBit+3b7+VZRfcA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/compat-data": "^7.28.6",
        "@babel/helper-validator-option": "^7.27.1",
        "browserslist": "^4.24.0",
        "lru-cache": "^5.1.1",
        "semver": "^6.3.1"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-create-class-features-plugin": {
      "version": "7.29.3",
      "resolved": "https://registry.npmmirror.com/@babel/helper-create-class-features-plugin/-/helper-create-class-features-plugin-7.29.3.tgz",
      "integrity": "sha512-RpLYy2sb51oNLjuu1iD3bwBqCBWUzjO0ocp+iaCP/lJtb2CPLcnC2Fftw+4sAzaMELGeWTgExSKADbdo0GFVzA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-annotate-as-pure": "^7.27.3",
        "@babel/helper-member-expression-to-functions": "^7.28.5",
        "@babel/helper-optimise-call-expression": "^7.27.1",
        "@babel/helper-replace-supers": "^7.28.6",
        "@babel/helper-skip-transparent-expression-wrappers": "^7.27.1",
        "@babel/traverse": "^7.29.0",
        "semver": "^6.3.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/helper-create-regexp-features-plugin": {
      "version": "7.28.5",
      "resolved": "https://registry.npmmirror.com/@babel/helper-create-regexp-features-plugin/-/helper-create-regexp-features-plugin-7.28.5.tgz",
      "integrity": "sha512-N1EhvLtHzOvj7QQOUCCS3NrPJP8c5W6ZXCHDn7Yialuy1iu4r5EmIYkXlKNqT99Ciw+W0mDqWoR6HWMZlFP3hw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-annotate-as-pure": "^7.27.3",
        "regexpu-core": "^6.3.1",
        "semver": "^6.3.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/helper-define-polyfill-provider": {
      "version": "0.6.8",
      "resolved": "https://registry.npmmirror.com/@babel/helper-define-polyfill-provider/-/helper-define-polyfill-provider-0.6.8.tgz",
      "integrity": "sha512-47UwBLPpQi1NoWzLuHNjRoHlYXMwIJoBf7MFou6viC/sIHWYygpvr0B6IAyh5sBdA2nr2LPIRww8lfaUVQINBA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-compilation-targets": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6",
        "debug": "^4.4.3",
        "lodash.debounce": "^4.0.8",
        "resolve": "^1.22.11"
      },
      "peerDependencies": {
        "@babel/core": "^7.4.0 || ^8.0.0-0 <8.0.0"
      }
    },
    "node_modules/@babel/helper-globals": {
      "version": "7.28.0",
      "resolved": "https://registry.npmjs.org/@babel/helper-globals/-/helper-globals-7.28.0.tgz",
      "integrity": "sha512-+W6cISkXFa1jXsDEdYA8HeevQT/FULhxzR99pxphltZcVaugps53THCeiWA8SguxxpSp3gKPiuYfSWopkLQ4hw==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-member-expression-to-functions": {
      "version": "7.28.5",
      "resolved": "https://registry.npmmirror.com/@babel/helper-member-expression-to-functions/-/helper-member-expression-to-functions-7.28.5.tgz",
      "integrity": "sha512-cwM7SBRZcPCLgl8a7cY0soT1SptSzAlMH39vwiRpOQkJlh53r5hdHwLSCZpQdVLT39sZt+CRpNwYG4Y2v77atg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/traverse": "^7.28.5",
        "@babel/types": "^7.28.5"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-module-imports": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/helper-module-imports/-/helper-module-imports-7.28.6.tgz",
      "integrity": "sha512-l5XkZK7r7wa9LucGw9LwZyyCUscb4x37JWTPz7swwFE/0FMQAGpiWUZn8u9DzkSBWEcK25jmvubfpw2dnAMdbw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/traverse": "^7.28.6",
        "@babel/types": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-module-transforms": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/helper-module-transforms/-/helper-module-transforms-7.28.6.tgz",
      "integrity": "sha512-67oXFAYr2cDLDVGLXTEABjdBJZ6drElUSI7WKp70NrpyISso3plG9SAGEF6y7zbha/wOzUByWWTJvEDVNIUGcA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-module-imports": "^7.28.6",
        "@babel/helper-validator-identifier": "^7.28.5",
        "@babel/traverse": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/helper-optimise-call-expression": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/helper-optimise-call-expression/-/helper-optimise-call-expression-7.27.1.tgz",
      "integrity": "sha512-URMGH08NzYFhubNSGJrpUEphGKQwMQYBySzat5cAByY1/YgIRkULnIy3tAMeszlL/so2HbeilYloUmSpd7GdVw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/types": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-plugin-utils": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/helper-plugin-utils/-/helper-plugin-utils-7.28.6.tgz",
      "integrity": "sha512-S9gzZ/bz83GRysI7gAD4wPT/AI3uCnY+9xn+Mx/KPs2JwHJIz1W8PZkg2cqyt3RNOBM8ejcXhV6y8Og7ly/Dug==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-remap-async-to-generator": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/helper-remap-async-to-generator/-/helper-remap-async-to-generator-7.27.1.tgz",
      "integrity": "sha512-7fiA521aVw8lSPeI4ZOD3vRFkoqkJcS+z4hFo82bFSH/2tNd6eJ5qCVMS5OzDmZh/kaHQeBaeyxK6wljcPtveA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-annotate-as-pure": "^7.27.1",
        "@babel/helper-wrap-function": "^7.27.1",
        "@babel/traverse": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/helper-replace-supers": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/helper-replace-supers/-/helper-replace-supers-7.28.6.tgz",
      "integrity": "sha512-mq8e+laIk94/yFec3DxSjCRD2Z0TAjhVbEJY3UQrlwVo15Lmt7C2wAUbK4bjnTs4APkwsYLTahXRraQXhb1WCg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-member-expression-to-functions": "^7.28.5",
        "@babel/helper-optimise-call-expression": "^7.27.1",
        "@babel/traverse": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/helper-skip-transparent-expression-wrappers": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/helper-skip-transparent-expression-wrappers/-/helper-skip-transparent-expression-wrappers-7.27.1.tgz",
      "integrity": "sha512-Tub4ZKEXqbPjXgWLl2+3JpQAYBJ8+ikpQ2Ocj/q/r0LwE3UhENh7EUabyHjz2kCEsrRY83ew2DQdHluuiDQFzg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/traverse": "^7.27.1",
        "@babel/types": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-string-parser": {
      "version": "7.27.1",
      "resolved": "https://registry.npmjs.org/@babel/helper-string-parser/-/helper-string-parser-7.27.1.tgz",
      "integrity": "sha512-qMlSxKbpRlAridDExk92nSobyDdpPijUq2DW6oDnUqd0iOGxmQjyqhMIihI9+zv4LPyZdRje2cavWPbCbWm3eA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-validator-identifier": {
      "version": "7.28.5",
      "resolved": "https://registry.npmjs.org/@babel/helper-validator-identifier/-/helper-validator-identifier-7.28.5.tgz",
      "integrity": "sha512-qSs4ifwzKJSV39ucNjsvc6WVHs6b7S03sOh2OcHF9UHfVPqWWALUsNUVzhSBiItjRZoLHx7nIarVjqKVusUZ1Q==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-validator-option": {
      "version": "7.27.1",
      "resolved": "https://registry.npmjs.org/@babel/helper-validator-option/-/helper-validator-option-7.27.1.tgz",
      "integrity": "sha512-YvjJow9FxbhFFKDSuFnVCe2WxXk1zWc22fFePVNEaWJEu8IrZVlda6N0uHwzZrUM1il7NC9Mlp4MaJYbYd9JSg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helper-wrap-function": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/helper-wrap-function/-/helper-wrap-function-7.28.6.tgz",
      "integrity": "sha512-z+PwLziMNBeSQJonizz2AGnndLsP2DeGHIxDAn+wdHOGuo4Fo1x1HBPPXeE9TAOPHNNWQKCSlA2VZyYyyibDnQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/template": "^7.28.6",
        "@babel/traverse": "^7.28.6",
        "@babel/types": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/helpers": {
      "version": "7.28.4",
      "resolved": "https://registry.npmjs.org/@babel/helpers/-/helpers-7.28.4.tgz",
      "integrity": "sha512-HFN59MmQXGHVyYadKLVumYsA9dBFun/ldYxipEjzA4196jpLZd8UjEEBLkbEkvfYreDqJhZxYAWFPtrfhNpj4w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/template": "^7.27.2",
        "@babel/types": "^7.28.4"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/parser": {
      "version": "7.29.3",
      "resolved": "https://registry.npmmirror.com/@babel/parser/-/parser-7.29.3.tgz",
      "integrity": "sha512-b3ctpQwp+PROvU/cttc4OYl4MzfJUWy6FZg+PMXfzmt/+39iHVF0sDfqay8TQM3JA2EUOyKcFZt75jWriQijsA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/types": "^7.29.0"
      },
      "bin": {
        "parser": "bin/babel-parser.js"
      },
      "engines": {
        "node": ">=6.0.0"
      }
    },
    "node_modules/@babel/plugin-bugfix-firefox-class-in-computed-class-key": {
      "version": "7.28.5",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-bugfix-firefox-class-in-computed-class-key/-/plugin-bugfix-firefox-class-in-computed-class-key-7.28.5.tgz",
      "integrity": "sha512-87GDMS3tsmMSi/3bWOte1UblL+YUTFMV8SZPZ2eSEL17s74Cw/l63rR6NmGVKMYW2GYi85nE+/d6Hw5N0bEk2Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1",
        "@babel/traverse": "^7.28.5"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-bugfix-safari-class-field-initializer-scope": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-bugfix-safari-class-field-initializer-scope/-/plugin-bugfix-safari-class-field-initializer-scope-7.27.1.tgz",
      "integrity": "sha512-qNeq3bCKnGgLkEXUuFry6dPlGfCdQNZbn7yUAPCInwAJHMU7THJfrBSozkcWq5sNM6RcF3S8XyQL2A52KNR9IA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-bugfix-safari-id-destructuring-collision-in-function-expression": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-bugfix-safari-id-destructuring-collision-in-function-expression/-/plugin-bugfix-safari-id-destructuring-collision-in-function-expression-7.27.1.tgz",
      "integrity": "sha512-g4L7OYun04N1WyqMNjldFwlfPCLVkgB54A/YCXICZYBsvJJE3kByKv9c9+R/nAfmIfjl2rKYLNyMHboYbZaWaA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-bugfix-safari-rest-destructuring-rhs-array": {
      "version": "7.29.3",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-bugfix-safari-rest-destructuring-rhs-array/-/plugin-bugfix-safari-rest-destructuring-rhs-array-7.29.3.tgz",
      "integrity": "sha512-SRS46DFR4HqzUzCVgi90/xMoL+zeBDBvWdKYXSEzh79kXswNFEglUpMKxR04//dPqwYXWUBJ3mpUd933ru9Kmg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-skip-transparent-expression-wrappers": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-bugfix-v8-spread-parameters-in-optional-chaining": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-bugfix-v8-spread-parameters-in-optional-chaining/-/plugin-bugfix-v8-spread-parameters-in-optional-chaining-7.27.1.tgz",
      "integrity": "sha512-oO02gcONcD5O1iTLi/6frMJBIwWEHceWGSGqrpCmEL8nogiS6J9PBlE48CaK20/Jx1LuRml9aDftLgdjXT8+Cw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1",
        "@babel/helper-skip-transparent-expression-wrappers": "^7.27.1",
        "@babel/plugin-transform-optional-chaining": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.13.0"
      }
    },
    "node_modules/@babel/plugin-bugfix-v8-static-class-fields-redefine-readonly": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-bugfix-v8-static-class-fields-redefine-readonly/-/plugin-bugfix-v8-static-class-fields-redefine-readonly-7.28.6.tgz",
      "integrity": "sha512-a0aBScVTlNaiUe35UtfxAN7A/tehvvG4/ByO6+46VPKTRSlfnAFsgKy0FUh+qAkQrDTmhDkT+IBOKlOoMUxQ0g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/traverse": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-proposal-decorators": {
      "version": "7.29.0",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-proposal-decorators/-/plugin-proposal-decorators-7.29.0.tgz",
      "integrity": "sha512-CVBVv3VY/XRMxRYq5dwr2DS7/MvqPm23cOCjbwNnVrfOqcWlnefua1uUs0sjdKOGjvPUG633o07uWzJq4oI6dA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-class-features-plugin": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/plugin-syntax-decorators": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-proposal-private-property-in-object": {
      "version": "7.21.0-placeholder-for-preset-env.2",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-proposal-private-property-in-object/-/plugin-proposal-private-property-in-object-7.21.0-placeholder-for-preset-env.2.tgz",
      "integrity": "sha512-SOSkfJDddaM7mak6cPEpswyTRnuRltl429hMraQEglW+OkovnCzsiszTmsrlY//qLFjCpQDFRvjdm2wA5pPm9w==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-syntax-decorators": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-syntax-decorators/-/plugin-syntax-decorators-7.28.6.tgz",
      "integrity": "sha512-71EYI0ONURHJBL4rSFXnITXqXrrY8q4P0q006DPfN+Rk+ASM+++IBXem/ruokgBZR8YNEWZ8R6B+rCb8VcUTqA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-syntax-import-assertions": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-syntax-import-assertions/-/plugin-syntax-import-assertions-7.28.6.tgz",
      "integrity": "sha512-pSJUpFHdx9z5nqTSirOCMtYVP2wFgoWhP0p3g8ONK/4IHhLIBd0B9NYqAvIUAhq+OkhO4VM1tENCt0cjlsNShw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-syntax-import-attributes": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-syntax-import-attributes/-/plugin-syntax-import-attributes-7.28.6.tgz",
      "integrity": "sha512-jiLC0ma9XkQT3TKJ9uYvlakm66Pamywo+qwL+oL8HJOvc6TWdZXVfhqJr8CCzbSGUAbDOzlGHJC1U+vRfLQDvw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-syntax-jsx": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-syntax-jsx/-/plugin-syntax-jsx-7.28.6.tgz",
      "integrity": "sha512-wgEmr06G6sIpqr8YDwA2dSRTE3bJ+V0IfpzfSY3Lfgd7YWOaAdlykvJi13ZKBt8cZHfgH1IXN+CL656W3uUa4w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-syntax-typescript": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-syntax-typescript/-/plugin-syntax-typescript-7.28.6.tgz",
      "integrity": "sha512-+nDNmQye7nlnuuHDboPbGm00Vqg3oO8niRRL27/4LYHUsHYh0zJ1xWOz0uRwNFmM1Avzk8wZbc6rdiYhomzv/A==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-syntax-unicode-sets-regex": {
      "version": "7.18.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-syntax-unicode-sets-regex/-/plugin-syntax-unicode-sets-regex-7.18.6.tgz",
      "integrity": "sha512-727YkEAPwSIQTv5im8QHz3upqp92JTWhidIC81Tdx4VJYIte/VndKf1qKrfnnhPLiPghStWfvC/iFaMCQu7Nqg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-regexp-features-plugin": "^7.18.6",
        "@babel/helper-plugin-utils": "^7.18.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-transform-arrow-functions": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-arrow-functions/-/plugin-transform-arrow-functions-7.27.1.tgz",
      "integrity": "sha512-8Z4TGic6xW70FKThA5HYEKKyBpOOsucTOD1DjU3fZxDg+K3zBJcXMFnt/4yQiZnf5+MiOMSXQ9PaEK/Ilh1DeA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-async-generator-functions": {
      "version": "7.29.0",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-async-generator-functions/-/plugin-transform-async-generator-functions-7.29.0.tgz",
      "integrity": "sha512-va0VdWro4zlBr2JsXC+ofCPB2iG12wPtVGTWFx2WLDOM3nYQZZIGP82qku2eW/JR83sD+k2k+CsNtyEbUqhU6w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-remap-async-to-generator": "^7.27.1",
        "@babel/traverse": "^7.29.0"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-async-to-generator": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-async-to-generator/-/plugin-transform-async-to-generator-7.28.6.tgz",
      "integrity": "sha512-ilTRcmbuXjsMmcZ3HASTe4caH5Tpo93PkTxF9oG2VZsSWsahydmcEHhix9Ik122RcTnZnUzPbmux4wh1swfv7g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-module-imports": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-remap-async-to-generator": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-block-scoped-functions": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-block-scoped-functions/-/plugin-transform-block-scoped-functions-7.27.1.tgz",
      "integrity": "sha512-cnqkuOtZLapWYZUYM5rVIdv1nXYuFVIltZ6ZJ7nIj585QsjKM5dhL2Fu/lICXZ1OyIAFc7Qy+bvDAtTXqGrlhg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-block-scoping": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-block-scoping/-/plugin-transform-block-scoping-7.28.6.tgz",
      "integrity": "sha512-tt/7wOtBmwHPNMPu7ax4pdPz6shjFrmHDghvNC+FG9Qvj7D6mJcoRQIF5dy4njmxR941l6rgtvfSB2zX3VlUIw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-class-properties": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-class-properties/-/plugin-transform-class-properties-7.28.6.tgz",
      "integrity": "sha512-dY2wS3I2G7D697VHndN91TJr8/AAfXQNt5ynCTI/MpxMsSzHp+52uNivYT5wCPax3whc47DR8Ba7cmlQMg24bw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-class-features-plugin": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-class-static-block": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-class-static-block/-/plugin-transform-class-static-block-7.28.6.tgz",
      "integrity": "sha512-rfQ++ghVwTWTqQ7w8qyDxL1XGihjBss4CmTgGRCTAC9RIbhVpyp4fOeZtta0Lbf+dTNIVJer6ych2ibHwkZqsQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-class-features-plugin": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.12.0"
      }
    },
    "node_modules/@babel/plugin-transform-classes": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-classes/-/plugin-transform-classes-7.28.6.tgz",
      "integrity": "sha512-EF5KONAqC5zAqT783iMGuM2ZtmEBy+mJMOKl2BCvPZ2lVrwvXnB6o+OBWCS+CoeCCpVRF2sA2RBKUxvT8tQT5Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-annotate-as-pure": "^7.27.3",
        "@babel/helper-compilation-targets": "^7.28.6",
        "@babel/helper-globals": "^7.28.0",
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-replace-supers": "^7.28.6",
        "@babel/traverse": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-computed-properties": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-computed-properties/-/plugin-transform-computed-properties-7.28.6.tgz",
      "integrity": "sha512-bcc3k0ijhHbc2lEfpFHgx7eYw9KNXqOerKWfzbxEHUGKnS3sz9C4CNL9OiFN1297bDNfUiSO7DaLzbvHQQQ1BQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/template": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-destructuring": {
      "version": "7.28.5",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-destructuring/-/plugin-transform-destructuring-7.28.5.tgz",
      "integrity": "sha512-Kl9Bc6D0zTUcFUvkNuQh4eGXPKKNDOJQXVyyM4ZAQPMveniJdxi8XMJwLo+xSoW3MIq81bD33lcUe9kZpl0MCw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1",
        "@babel/traverse": "^7.28.5"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-dotall-regex": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-dotall-regex/-/plugin-transform-dotall-regex-7.28.6.tgz",
      "integrity": "sha512-SljjowuNKB7q5Oayv4FoPzeB74g3QgLt8IVJw9ADvWy3QnUb/01aw8I4AVv8wYnPvQz2GDDZ/g3GhcNyDBI4Bg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-regexp-features-plugin": "^7.28.5",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-duplicate-keys": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-duplicate-keys/-/plugin-transform-duplicate-keys-7.27.1.tgz",
      "integrity": "sha512-MTyJk98sHvSs+cvZ4nOauwTTG1JeonDjSGvGGUNHreGQns+Mpt6WX/dVzWBHgg+dYZhkC4X+zTDfkTU+Vy9y7Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-duplicate-named-capturing-groups-regex": {
      "version": "7.29.0",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-duplicate-named-capturing-groups-regex/-/plugin-transform-duplicate-named-capturing-groups-regex-7.29.0.tgz",
      "integrity": "sha512-zBPcW2lFGxdiD8PUnPwJjag2J9otbcLQzvbiOzDxpYXyCuYX9agOwMPGn1prVH0a4qzhCKu24rlH4c1f7yA8rw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-regexp-features-plugin": "^7.28.5",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-transform-dynamic-import": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-dynamic-import/-/plugin-transform-dynamic-import-7.27.1.tgz",
      "integrity": "sha512-MHzkWQcEmjzzVW9j2q8LGjwGWpG2mjwaaB0BNQwst3FIjqsg8Ct/mIZlvSPJvfi9y2AC8mi/ktxbFVL9pZ1I4A==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-explicit-resource-management": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-explicit-resource-management/-/plugin-transform-explicit-resource-management-7.28.6.tgz",
      "integrity": "sha512-Iao5Konzx2b6g7EPqTy40UZbcdXE126tTxVFr/nAIj+WItNxjKSYTEw3RC+A2/ZetmdJsgueL1KhaMCQHkLPIg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/plugin-transform-destructuring": "^7.28.5"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-exponentiation-operator": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-exponentiation-operator/-/plugin-transform-exponentiation-operator-7.28.6.tgz",
      "integrity": "sha512-WitabqiGjV/vJ0aPOLSFfNY1u9U3R7W36B03r5I2KoNix+a3sOhJ3pKFB3R5It9/UiK78NiO0KE9P21cMhlPkw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-export-namespace-from": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-export-namespace-from/-/plugin-transform-export-namespace-from-7.27.1.tgz",
      "integrity": "sha512-tQvHWSZ3/jH2xuq/vZDy0jNn+ZdXJeM8gHvX4lnJmsc3+50yPlWdZXIc5ay+umX+2/tJIqHqiEqcJvxlmIvRvQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-for-of": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-for-of/-/plugin-transform-for-of-7.27.1.tgz",
      "integrity": "sha512-BfbWFFEJFQzLCQ5N8VocnCtA8J1CLkNTe2Ms2wocj75dd6VpiqS5Z5quTYcUoo4Yq+DN0rtikODccuv7RU81sw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1",
        "@babel/helper-skip-transparent-expression-wrappers": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-function-name": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-function-name/-/plugin-transform-function-name-7.27.1.tgz",
      "integrity": "sha512-1bQeydJF9Nr1eBCMMbC+hdwmRlsv5XYOMu03YSWFwNs0HsAmtSxxF1fyuYPqemVldVyFmlCU7w8UE14LupUSZQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-compilation-targets": "^7.27.1",
        "@babel/helper-plugin-utils": "^7.27.1",
        "@babel/traverse": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-json-strings": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-json-strings/-/plugin-transform-json-strings-7.28.6.tgz",
      "integrity": "sha512-Nr+hEN+0geQkzhbdgQVPoqr47lZbm+5fCUmO70722xJZd0Mvb59+33QLImGj6F+DkK3xgDi1YVysP8whD6FQAw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-literals": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-literals/-/plugin-transform-literals-7.27.1.tgz",
      "integrity": "sha512-0HCFSepIpLTkLcsi86GG3mTUzxV5jpmbv97hTETW3yzrAij8aqlD36toB1D0daVFJM8NK6GvKO0gslVQmm+zZA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-logical-assignment-operators": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-logical-assignment-operators/-/plugin-transform-logical-assignment-operators-7.28.6.tgz",
      "integrity": "sha512-+anKKair6gpi8VsM/95kmomGNMD0eLz1NQ8+Pfw5sAwWH9fGYXT50E55ZpV0pHUHWf6IUTWPM+f/7AAff+wr9A==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-member-expression-literals": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-member-expression-literals/-/plugin-transform-member-expression-literals-7.27.1.tgz",
      "integrity": "sha512-hqoBX4dcZ1I33jCSWcXrP+1Ku7kdqXf1oeah7ooKOIiAdKQ+uqftgCFNOSzA5AMS2XIHEYeGFg4cKRCdpxzVOQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-modules-amd": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-modules-amd/-/plugin-transform-modules-amd-7.27.1.tgz",
      "integrity": "sha512-iCsytMg/N9/oFq6n+gFTvUYDZQOMK5kEdeYxmxt91fcJGycfxVP9CnrxoliM0oumFERba2i8ZtwRUCMhvP1LnA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-module-transforms": "^7.27.1",
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-modules-commonjs": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-modules-commonjs/-/plugin-transform-modules-commonjs-7.28.6.tgz",
      "integrity": "sha512-jppVbf8IV9iWWwWTQIxJMAJCWBuuKx71475wHwYytrRGQ2CWiDvYlADQno3tcYpS/T2UUWFQp3nVtYfK/YBQrA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-module-transforms": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-modules-systemjs": {
      "version": "7.29.4",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-modules-systemjs/-/plugin-transform-modules-systemjs-7.29.4.tgz",
      "integrity": "sha512-N7QmZ0xRZfjHOfZeQLJjwgX2zS9pdGHSVl/cjSGlo4dXMqvurfxXDMKY4RqEKzPozV78VMcd0lxyG13mlbKc4w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-module-transforms": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-validator-identifier": "^7.28.5",
        "@babel/traverse": "^7.29.0"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-modules-umd": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-modules-umd/-/plugin-transform-modules-umd-7.27.1.tgz",
      "integrity": "sha512-iQBE/xC5BV1OxJbp6WG7jq9IWiD+xxlZhLrdwpPkTX3ydmXdvoCpyfJN7acaIBZaOqTfr76pgzqBJflNbeRK+w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-module-transforms": "^7.27.1",
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-named-capturing-groups-regex": {
      "version": "7.29.0",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-named-capturing-groups-regex/-/plugin-transform-named-capturing-groups-regex-7.29.0.tgz",
      "integrity": "sha512-1CZQA5KNAD6ZYQLPw7oi5ewtDNxH/2vuCh+6SmvgDfhumForvs8a1o9n0UrEoBD8HU4djO2yWngTQlXl1NDVEQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-regexp-features-plugin": "^7.28.5",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-transform-new-target": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-new-target/-/plugin-transform-new-target-7.27.1.tgz",
      "integrity": "sha512-f6PiYeqXQ05lYq3TIfIDu/MtliKUbNwkGApPUvyo6+tc7uaR4cPjPe7DFPr15Uyycg2lZU6btZ575CuQoYh7MQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-nullish-coalescing-operator": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-nullish-coalescing-operator/-/plugin-transform-nullish-coalescing-operator-7.28.6.tgz",
      "integrity": "sha512-3wKbRgmzYbw24mDJXT7N+ADXw8BC/imU9yo9c9X9NKaLF1fW+e5H1U5QjMUBe4Qo4Ox/o++IyUkl1sVCLgevKg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-numeric-separator": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-numeric-separator/-/plugin-transform-numeric-separator-7.28.6.tgz",
      "integrity": "sha512-SJR8hPynj8outz+SlStQSwvziMN4+Bq99it4tMIf5/Caq+3iOc0JtKyse8puvyXkk3eFRIA5ID/XfunGgO5i6w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-object-rest-spread": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-object-rest-spread/-/plugin-transform-object-rest-spread-7.28.6.tgz",
      "integrity": "sha512-5rh+JR4JBC4pGkXLAcYdLHZjXudVxWMXbB6u6+E9lRL5TrGVbHt1TjxGbZ8CkmYw9zjkB7jutzOROArsqtncEA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-compilation-targets": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/plugin-transform-destructuring": "^7.28.5",
        "@babel/plugin-transform-parameters": "^7.27.7",
        "@babel/traverse": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-object-super": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-object-super/-/plugin-transform-object-super-7.27.1.tgz",
      "integrity": "sha512-SFy8S9plRPbIcxlJ8A6mT/CxFdJx/c04JEctz4jf8YZaVS2px34j7NXRrlGlHkN/M2gnpL37ZpGRGVFLd3l8Ng==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1",
        "@babel/helper-replace-supers": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-optional-catch-binding": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-optional-catch-binding/-/plugin-transform-optional-catch-binding-7.28.6.tgz",
      "integrity": "sha512-R8ja/Pyrv0OGAvAXQhSTmWyPJPml+0TMqXlO5w+AsMEiwb2fg3WkOvob7UxFSL3OIttFSGSRFKQsOhJ/X6HQdQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-optional-chaining": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-optional-chaining/-/plugin-transform-optional-chaining-7.28.6.tgz",
      "integrity": "sha512-A4zobikRGJTsX9uqVFdafzGkqD30t26ck2LmOzAuLL8b2x6k3TIqRiT2xVvA9fNmFeTX484VpsdgmKNA0bS23w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-skip-transparent-expression-wrappers": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-parameters": {
      "version": "7.27.7",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-parameters/-/plugin-transform-parameters-7.27.7.tgz",
      "integrity": "sha512-qBkYTYCb76RRxUM6CcZA5KRu8K4SM8ajzVeUgVdMVO9NN9uI/GaVmBg/WKJJGnNokV9SY8FxNOVWGXzqzUidBg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-private-methods": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-private-methods/-/plugin-transform-private-methods-7.28.6.tgz",
      "integrity": "sha512-piiuapX9CRv7+0st8lmuUlRSmX6mBcVeNQ1b4AYzJxfCMuBfB0vBXDiGSmm03pKJw1v6cZ8KSeM+oUnM6yAExg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-class-features-plugin": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-private-property-in-object": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-private-property-in-object/-/plugin-transform-private-property-in-object-7.28.6.tgz",
      "integrity": "sha512-b97jvNSOb5+ehyQmBpmhOCiUC5oVK4PMnpRvO7+ymFBoqYjeDHIU9jnrNUuwHOiL9RpGDoKBpSViarV+BU+eVA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-annotate-as-pure": "^7.27.3",
        "@babel/helper-create-class-features-plugin": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-property-literals": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-property-literals/-/plugin-transform-property-literals-7.27.1.tgz",
      "integrity": "sha512-oThy3BCuCha8kDZ8ZkgOg2exvPYUlprMukKQXI1r1pJ47NCvxfkEy8vK+r/hT9nF0Aa4H1WUPZZjHTFtAhGfmQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-react-display-name": {
      "version": "7.28.0",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-react-display-name/-/plugin-transform-react-display-name-7.28.0.tgz",
      "integrity": "sha512-D6Eujc2zMxKjfa4Zxl4GHMsmhKKZ9VpcqIchJLvwTxad9zWIYulwYItBovpDOoNLISpcZSXoDJ5gaGbQUDqViA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-react-jsx": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-react-jsx/-/plugin-transform-react-jsx-7.28.6.tgz",
      "integrity": "sha512-61bxqhiRfAACulXSLd/GxqmAedUSrRZIu/cbaT18T1CetkTmtDN15it7i80ru4DVqRK1WMxQhXs+Lf9kajm5Ow==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-annotate-as-pure": "^7.27.3",
        "@babel/helper-module-imports": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/plugin-syntax-jsx": "^7.28.6",
        "@babel/types": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-react-jsx-development": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-react-jsx-development/-/plugin-transform-react-jsx-development-7.27.1.tgz",
      "integrity": "sha512-ykDdF5yI4f1WrAolLqeF3hmYU12j9ntLQl/AOG1HAS21jxyg1Q0/J/tpREuYLfatGdGmXp/3yS0ZA76kOlVq9Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/plugin-transform-react-jsx": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-react-jsx-self": {
      "version": "7.27.1",
      "resolved": "https://registry.npmjs.org/@babel/plugin-transform-react-jsx-self/-/plugin-transform-react-jsx-self-7.27.1.tgz",
      "integrity": "sha512-6UzkCs+ejGdZ5mFFC/OCUrv028ab2fp1znZmCZjAOBKiBK2jXD1O+BPSfX8X2qjJ75fZBMSnQn3Rq2mrBJK2mw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-react-jsx-source": {
      "version": "7.27.1",
      "resolved": "https://registry.npmjs.org/@babel/plugin-transform-react-jsx-source/-/plugin-transform-react-jsx-source-7.27.1.tgz",
      "integrity": "sha512-zbwoTsBruTeKB9hSq73ha66iFeJHuaFkUbwvqElnygoNbj/jHRsSeokowZFN3CZ64IvEqcmmkVe89OPXc7ldAw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-react-pure-annotations": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-react-pure-annotations/-/plugin-transform-react-pure-annotations-7.27.1.tgz",
      "integrity": "sha512-JfuinvDOsD9FVMTHpzA/pBLisxpv1aSf+OIV8lgH3MuWrks19R27e6a6DipIg4aX1Zm9Wpb04p8wljfKrVSnPA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-annotate-as-pure": "^7.27.1",
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-regenerator": {
      "version": "7.29.0",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-regenerator/-/plugin-transform-regenerator-7.29.0.tgz",
      "integrity": "sha512-FijqlqMA7DmRdg/aINBSs04y8XNTYw/lr1gJ2WsmBnnaNw1iS43EPkJW+zK7z65auG3AWRFXWj+NcTQwYptUog==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-regexp-modifiers": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-regexp-modifiers/-/plugin-transform-regexp-modifiers-7.28.6.tgz",
      "integrity": "sha512-QGWAepm9qxpaIs7UM9FvUSnCGlb8Ua1RhyM4/veAxLwt3gMat/LSGrZixyuj4I6+Kn9iwvqCyPTtbdxanYoWYg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-regexp-features-plugin": "^7.28.5",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/plugin-transform-reserved-words": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-reserved-words/-/plugin-transform-reserved-words-7.27.1.tgz",
      "integrity": "sha512-V2ABPHIJX4kC7HegLkYoDpfg9PVmuWy/i6vUM5eGK22bx4YVFD3M5F0QQnWQoDs6AGsUWTVOopBiMFQgHaSkVw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-shorthand-properties": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-shorthand-properties/-/plugin-transform-shorthand-properties-7.27.1.tgz",
      "integrity": "sha512-N/wH1vcn4oYawbJ13Y/FxcQrWk63jhfNa7jef0ih7PHSIHX2LB7GWE1rkPrOnka9kwMxb6hMl19p7lidA+EHmQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-spread": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-spread/-/plugin-transform-spread-7.28.6.tgz",
      "integrity": "sha512-9U4QObUC0FtJl05AsUcodau/RWDytrU6uKgkxu09mLR9HLDAtUMoPuuskm5huQsoktmsYpI+bGmq+iapDcriKA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-skip-transparent-expression-wrappers": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-sticky-regex": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-sticky-regex/-/plugin-transform-sticky-regex-7.27.1.tgz",
      "integrity": "sha512-lhInBO5bi/Kowe2/aLdBAawijx+q1pQzicSgnkB6dUPc1+RC8QmJHKf2OjvU+NZWitguJHEaEmbV6VWEouT58g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-template-literals": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-template-literals/-/plugin-transform-template-literals-7.27.1.tgz",
      "integrity": "sha512-fBJKiV7F2DxZUkg5EtHKXQdbsbURW3DZKQUWphDum0uRP6eHGGa/He9mc0mypL680pb+e/lDIthRohlv8NCHkg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-typeof-symbol": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-typeof-symbol/-/plugin-transform-typeof-symbol-7.27.1.tgz",
      "integrity": "sha512-RiSILC+nRJM7FY5srIyc4/fGIwUhyDuuBSdWn4y6yT6gm652DpCHZjIipgn6B7MQ1ITOUnAKWixEUjQRIBIcLw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-typescript": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-typescript/-/plugin-transform-typescript-7.28.6.tgz",
      "integrity": "sha512-0YWL2RFxOqEm9Efk5PvreamxPME8OyY0wM5wh5lHjF+VtVhdneCWGzZeSqzOfiobVqQaNCd2z0tQvnI9DaPWPw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-annotate-as-pure": "^7.27.3",
        "@babel/helper-create-class-features-plugin": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-skip-transparent-expression-wrappers": "^7.27.1",
        "@babel/plugin-syntax-typescript": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-unicode-escapes": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-unicode-escapes/-/plugin-transform-unicode-escapes-7.27.1.tgz",
      "integrity": "sha512-Ysg4v6AmF26k9vpfFuTZg8HRfVWzsh1kVfowA23y9j/Gu6dOuahdUVhkLqpObp3JIv27MLSii6noRnuKN8H0Mg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-unicode-property-regex": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-unicode-property-regex/-/plugin-transform-unicode-property-regex-7.28.6.tgz",
      "integrity": "sha512-4Wlbdl/sIZjzi/8St0evF0gEZrgOswVO6aOzqxh1kDZOl9WmLrHq2HtGhnOJZmHZYKP8WZ1MDLCt5DAWwRo57A==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-regexp-features-plugin": "^7.28.5",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-unicode-regex": {
      "version": "7.27.1",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-unicode-regex/-/plugin-transform-unicode-regex-7.27.1.tgz",
      "integrity": "sha512-xvINq24TRojDuyt6JGtHmkVkrfVV3FPT16uytxImLeBZqW3/H52yN+kM1MGuyPkIQxrzKwPHs5U/MP3qKyzkGw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-regexp-features-plugin": "^7.27.1",
        "@babel/helper-plugin-utils": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/plugin-transform-unicode-sets-regex": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/plugin-transform-unicode-sets-regex/-/plugin-transform-unicode-sets-regex-7.28.6.tgz",
      "integrity": "sha512-/wHc/paTUmsDYN7SZkpWxogTOBNnlx7nBQYfy6JJlCT7G3mVhltk3e++N7zV0XfgGsrqBxd4rJQt9H16I21Y1Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-create-regexp-features-plugin": "^7.28.5",
        "@babel/helper-plugin-utils": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0"
      }
    },
    "node_modules/@babel/preset-env": {
      "version": "7.29.5",
      "resolved": "https://registry.npmmirror.com/@babel/preset-env/-/preset-env-7.29.5.tgz",
      "integrity": "sha512-/69t2aEzGKHD76DyLbHysF/QH2LJOB8iFnYO37unDTKBTubzcMRv0f3H5EiN1Q6ajOd/eB7dAInF0qdFVS06kA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/compat-data": "^7.29.3",
        "@babel/helper-compilation-targets": "^7.28.6",
        "@babel/helper-plugin-utils": "^7.28.6",
        "@babel/helper-validator-option": "^7.27.1",
        "@babel/plugin-bugfix-firefox-class-in-computed-class-key": "^7.28.5",
        "@babel/plugin-bugfix-safari-class-field-initializer-scope": "^7.27.1",
        "@babel/plugin-bugfix-safari-id-destructuring-collision-in-function-expression": "^7.27.1",
        "@babel/plugin-bugfix-safari-rest-destructuring-rhs-array": "^7.29.3",
        "@babel/plugin-bugfix-v8-spread-parameters-in-optional-chaining": "^7.27.1",
        "@babel/plugin-bugfix-v8-static-class-fields-redefine-readonly": "^7.28.6",
        "@babel/plugin-proposal-private-property-in-object": "7.21.0-placeholder-for-preset-env.2",
        "@babel/plugin-syntax-import-assertions": "^7.28.6",
        "@babel/plugin-syntax-import-attributes": "^7.28.6",
        "@babel/plugin-syntax-unicode-sets-regex": "^7.18.6",
        "@babel/plugin-transform-arrow-functions": "^7.27.1",
        "@babel/plugin-transform-async-generator-functions": "^7.29.0",
        "@babel/plugin-transform-async-to-generator": "^7.28.6",
        "@babel/plugin-transform-block-scoped-functions": "^7.27.1",
        "@babel/plugin-transform-block-scoping": "^7.28.6",
        "@babel/plugin-transform-class-properties": "^7.28.6",
        "@babel/plugin-transform-class-static-block": "^7.28.6",
        "@babel/plugin-transform-classes": "^7.28.6",
        "@babel/plugin-transform-computed-properties": "^7.28.6",
        "@babel/plugin-transform-destructuring": "^7.28.5",
        "@babel/plugin-transform-dotall-regex": "^7.28.6",
        "@babel/plugin-transform-duplicate-keys": "^7.27.1",
        "@babel/plugin-transform-duplicate-named-capturing-groups-regex": "^7.29.0",
        "@babel/plugin-transform-dynamic-import": "^7.27.1",
        "@babel/plugin-transform-explicit-resource-management": "^7.28.6",
        "@babel/plugin-transform-exponentiation-operator": "^7.28.6",
        "@babel/plugin-transform-export-namespace-from": "^7.27.1",
        "@babel/plugin-transform-for-of": "^7.27.1",
        "@babel/plugin-transform-function-name": "^7.27.1",
        "@babel/plugin-transform-json-strings": "^7.28.6",
        "@babel/plugin-transform-literals": "^7.27.1",
        "@babel/plugin-transform-logical-assignment-operators": "^7.28.6",
        "@babel/plugin-transform-member-expression-literals": "^7.27.1",
        "@babel/plugin-transform-modules-amd": "^7.27.1",
        "@babel/plugin-transform-modules-commonjs": "^7.28.6",
        "@babel/plugin-transform-modules-systemjs": "^7.29.4",
        "@babel/plugin-transform-modules-umd": "^7.27.1",
        "@babel/plugin-transform-named-capturing-groups-regex": "^7.29.0",
        "@babel/plugin-transform-new-target": "^7.27.1",
        "@babel/plugin-transform-nullish-coalescing-operator": "^7.28.6",
        "@babel/plugin-transform-numeric-separator": "^7.28.6",
        "@babel/plugin-transform-object-rest-spread": "^7.28.6",
        "@babel/plugin-transform-object-super": "^7.27.1",
        "@babel/plugin-transform-optional-catch-binding": "^7.28.6",
        "@babel/plugin-transform-optional-chaining": "^7.28.6",
        "@babel/plugin-transform-parameters": "^7.27.7",
        "@babel/plugin-transform-private-methods": "^7.28.6",
        "@babel/plugin-transform-private-property-in-object": "^7.28.6",
        "@babel/plugin-transform-property-literals": "^7.27.1",
        "@babel/plugin-transform-regenerator": "^7.29.0",
        "@babel/plugin-transform-regexp-modifiers": "^7.28.6",
        "@babel/plugin-transform-reserved-words": "^7.27.1",
        "@babel/plugin-transform-shorthand-properties": "^7.27.1",
        "@babel/plugin-transform-spread": "^7.28.6",
        "@babel/plugin-transform-sticky-regex": "^7.27.1",
        "@babel/plugin-transform-template-literals": "^7.27.1",
        "@babel/plugin-transform-typeof-symbol": "^7.27.1",
        "@babel/plugin-transform-unicode-escapes": "^7.27.1",
        "@babel/plugin-transform-unicode-property-regex": "^7.28.6",
        "@babel/plugin-transform-unicode-regex": "^7.27.1",
        "@babel/plugin-transform-unicode-sets-regex": "^7.28.6",
        "@babel/preset-modules": "0.1.6-no-external-plugins",
        "babel-plugin-polyfill-corejs2": "^0.4.15",
        "babel-plugin-polyfill-corejs3": "^0.14.0",
        "babel-plugin-polyfill-regenerator": "^0.6.6",
        "core-js-compat": "^3.48.0",
        "semver": "^6.3.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/preset-modules": {
      "version": "0.1.6-no-external-plugins",
      "resolved": "https://registry.npmmirror.com/@babel/preset-modules/-/preset-modules-0.1.6-no-external-plugins.tgz",
      "integrity": "sha512-HrcgcIESLm9aIR842yhJ5RWan/gebQUJ6E/E5+rf0y9o6oj7w0Br+sWuL6kEQ/o/AdfvR1Je9jG18/gnpwjEyA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.0.0",
        "@babel/types": "^7.4.4",
        "esutils": "^2.0.2"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0 || ^8.0.0-0 <8.0.0"
      }
    },
    "node_modules/@babel/preset-react": {
      "version": "7.28.5",
      "resolved": "https://registry.npmmirror.com/@babel/preset-react/-/preset-react-7.28.5.tgz",
      "integrity": "sha512-Z3J8vhRq7CeLjdC58jLv4lnZ5RKFUJWqH5emvxmv9Hv3BD1T9R/Im713R4MTKwvFaV74ejZ3sM01LyEKk4ugNQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1",
        "@babel/helper-validator-option": "^7.27.1",
        "@babel/plugin-transform-react-display-name": "^7.28.0",
        "@babel/plugin-transform-react-jsx": "^7.27.1",
        "@babel/plugin-transform-react-jsx-development": "^7.27.1",
        "@babel/plugin-transform-react-pure-annotations": "^7.27.1"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/preset-typescript": {
      "version": "7.28.5",
      "resolved": "https://registry.npmmirror.com/@babel/preset-typescript/-/preset-typescript-7.28.5.tgz",
      "integrity": "sha512-+bQy5WOI2V6LJZpPVxY+yp66XdZ2yifu0Mc1aP5CQKgjn4QM5IN2i5fAZ4xKop47pr8rpVhiAeu+nDQa12C8+g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-plugin-utils": "^7.27.1",
        "@babel/helper-validator-option": "^7.27.1",
        "@babel/plugin-syntax-jsx": "^7.27.1",
        "@babel/plugin-transform-modules-commonjs": "^7.27.1",
        "@babel/plugin-transform-typescript": "^7.28.5"
      },
      "engines": {
        "node": ">=6.9.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.0.0-0"
      }
    },
    "node_modules/@babel/runtime": {
      "version": "7.28.4",
      "resolved": "https://registry.npmjs.org/@babel/runtime/-/runtime-7.28.4.tgz",
      "integrity": "sha512-Q/N6JNWvIvPnLDvjlE1OUBLPQHH6l3CltCEsHIujp45zQUSSh8K+gHnaEX45yAT1nyngnINhvWtzN+Nb9D8RAQ==",
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/template": {
      "version": "7.28.6",
      "resolved": "https://registry.npmmirror.com/@babel/template/-/template-7.28.6.tgz",
      "integrity": "sha512-YA6Ma2KsCdGb+WC6UpBVFJGXL58MDA6oyONbjyF/+5sBgxY/dwkhLogbMT2GXXyU84/IhRw/2D1Os1B/giz+BQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/code-frame": "^7.28.6",
        "@babel/parser": "^7.28.6",
        "@babel/types": "^7.28.6"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/traverse": {
      "version": "7.29.0",
      "resolved": "https://registry.npmmirror.com/@babel/traverse/-/traverse-7.29.0.tgz",
      "integrity": "sha512-4HPiQr0X7+waHfyXPZpWPfWL/J7dcN1mx9gL6WdQVMbPnF3+ZhSMs8tCxN7oHddJE9fhNE7+lxdnlyemKfJRuA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/code-frame": "^7.29.0",
        "@babel/generator": "^7.29.0",
        "@babel/helper-globals": "^7.28.0",
        "@babel/parser": "^7.29.0",
        "@babel/template": "^7.28.6",
        "@babel/types": "^7.29.0",
        "debug": "^4.3.1"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@babel/types": {
      "version": "7.29.0",
      "resolved": "https://registry.npmmirror.com/@babel/types/-/types-7.29.0.tgz",
      "integrity": "sha512-LwdZHpScM4Qz8Xw2iKSzS+cfglZzJGvofQICy7W7v4caru4EaAmyUuO6BGrbyQ2mYV11W0U8j5mBhd14dd3B0A==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-string-parser": "^7.27.1",
        "@babel/helper-validator-identifier": "^7.28.5"
      },
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/@date-fns/tz": {
      "version": "1.4.1",
      "resolved": "https://registry.npmjs.org/@date-fns/tz/-/tz-1.4.1.tgz",
      "integrity": "sha512-P5LUNhtbj6YfI3iJjw5EL9eUAG6OitD0W3fWQcpQjDRc/QIsL0tRNuO1PcDvPccWL1fSTXXdE1ds+l95DV/OFA==",
      "license": "MIT"
    },
    "node_modules/@dimforge/rapier3d-compat": {
      "version": "0.12.0",
      "resolved": "https://registry.npmmirror.com/@dimforge/rapier3d-compat/-/rapier3d-compat-0.12.0.tgz",
      "integrity": "sha512-uekIGetywIgopfD97oDL5PfeezkFpNhwlzlaEYNOA0N6ghdsOvh/HYjSMek5Q2O1PYvRSDFcqFVJl4r4ZBwOow==",
      "license": "Apache-2.0"
    },
    "node_modules/@esbuild/aix-ppc64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/aix-ppc64/-/aix-ppc64-0.27.2.tgz",
      "integrity": "sha512-GZMB+a0mOMZs4MpDbj8RJp4cw+w1WV5NYD6xzgvzUJ5Ek2jerwfO2eADyI6ExDSUED+1X8aMbegahsJi+8mgpw==",
      "cpu": [
        "ppc64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "aix"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/android-arm": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/android-arm/-/android-arm-0.27.2.tgz",
      "integrity": "sha512-DVNI8jlPa7Ujbr1yjU2PfUSRtAUZPG9I1RwW4F4xFB1Imiu2on0ADiI/c3td+KmDtVKNbi+nffGDQMfcIMkwIA==",
      "cpu": [
        "arm"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "android"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/android-arm64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/android-arm64/-/android-arm64-0.27.2.tgz",
      "integrity": "sha512-pvz8ZZ7ot/RBphf8fv60ljmaoydPU12VuXHImtAs0XhLLw+EXBi2BLe3OYSBslR4rryHvweW5gmkKFwTiFy6KA==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "android"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/android-x64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/android-x64/-/android-x64-0.27.2.tgz",
      "integrity": "sha512-z8Ank4Byh4TJJOh4wpz8g2vDy75zFL0TlZlkUkEwYXuPSgX8yzep596n6mT7905kA9uHZsf/o2OJZubl2l3M7A==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "android"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/darwin-arm64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/darwin-arm64/-/darwin-arm64-0.27.2.tgz",
      "integrity": "sha512-davCD2Zc80nzDVRwXTcQP/28fiJbcOwvdolL0sOiOsbwBa72kegmVU0Wrh1MYrbuCL98Omp5dVhQFWRKR2ZAlg==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "darwin"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/darwin-x64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/darwin-x64/-/darwin-x64-0.27.2.tgz",
      "integrity": "sha512-ZxtijOmlQCBWGwbVmwOF/UCzuGIbUkqB1faQRf5akQmxRJ1ujusWsb3CVfk/9iZKr2L5SMU5wPBi1UWbvL+VQA==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "darwin"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/freebsd-arm64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/freebsd-arm64/-/freebsd-arm64-0.27.2.tgz",
      "integrity": "sha512-lS/9CN+rgqQ9czogxlMcBMGd+l8Q3Nj1MFQwBZJyoEKI50XGxwuzznYdwcav6lpOGv5BqaZXqvBSiB/kJ5op+g==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "freebsd"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/freebsd-x64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/freebsd-x64/-/freebsd-x64-0.27.2.tgz",
      "integrity": "sha512-tAfqtNYb4YgPnJlEFu4c212HYjQWSO/w/h/lQaBK7RbwGIkBOuNKQI9tqWzx7Wtp7bTPaGC6MJvWI608P3wXYA==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "freebsd"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-arm": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-arm/-/linux-arm-0.27.2.tgz",
      "integrity": "sha512-vWfq4GaIMP9AIe4yj1ZUW18RDhx6EPQKjwe7n8BbIecFtCQG4CfHGaHuh7fdfq+y3LIA2vGS/o9ZBGVxIDi9hw==",
      "cpu": [
        "arm"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-arm64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-arm64/-/linux-arm64-0.27.2.tgz",
      "integrity": "sha512-hYxN8pr66NsCCiRFkHUAsxylNOcAQaxSSkHMMjcpx0si13t1LHFphxJZUiGwojB1a/Hd5OiPIqDdXONia6bhTw==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-ia32": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-ia32/-/linux-ia32-0.27.2.tgz",
      "integrity": "sha512-MJt5BRRSScPDwG2hLelYhAAKh9imjHK5+NE/tvnRLbIqUWa+0E9N4WNMjmp/kXXPHZGqPLxggwVhz7QP8CTR8w==",
      "cpu": [
        "ia32"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-loong64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-loong64/-/linux-loong64-0.27.2.tgz",
      "integrity": "sha512-lugyF1atnAT463aO6KPshVCJK5NgRnU4yb3FUumyVz+cGvZbontBgzeGFO1nF+dPueHD367a2ZXe1NtUkAjOtg==",
      "cpu": [
        "loong64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-mips64el": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-mips64el/-/linux-mips64el-0.27.2.tgz",
      "integrity": "sha512-nlP2I6ArEBewvJ2gjrrkESEZkB5mIoaTswuqNFRv/WYd+ATtUpe9Y09RnJvgvdag7he0OWgEZWhviS1OTOKixw==",
      "cpu": [
        "mips64el"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-ppc64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-ppc64/-/linux-ppc64-0.27.2.tgz",
      "integrity": "sha512-C92gnpey7tUQONqg1n6dKVbx3vphKtTHJaNG2Ok9lGwbZil6DrfyecMsp9CrmXGQJmZ7iiVXvvZH6Ml5hL6XdQ==",
      "cpu": [
        "ppc64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-riscv64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-riscv64/-/linux-riscv64-0.27.2.tgz",
      "integrity": "sha512-B5BOmojNtUyN8AXlK0QJyvjEZkWwy/FKvakkTDCziX95AowLZKR6aCDhG7LeF7uMCXEJqwa8Bejz5LTPYm8AvA==",
      "cpu": [
        "riscv64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-s390x": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-s390x/-/linux-s390x-0.27.2.tgz",
      "integrity": "sha512-p4bm9+wsPwup5Z8f4EpfN63qNagQ47Ua2znaqGH6bqLlmJ4bx97Y9JdqxgGZ6Y8xVTixUnEkoKSHcpRlDnNr5w==",
      "cpu": [
        "s390x"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/linux-x64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/linux-x64/-/linux-x64-0.27.2.tgz",
      "integrity": "sha512-uwp2Tip5aPmH+NRUwTcfLb+W32WXjpFejTIOWZFw/v7/KnpCDKG66u4DLcurQpiYTiYwQ9B7KOeMJvLCu/OvbA==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/netbsd-arm64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/netbsd-arm64/-/netbsd-arm64-0.27.2.tgz",
      "integrity": "sha512-Kj6DiBlwXrPsCRDeRvGAUb/LNrBASrfqAIok+xB0LxK8CHqxZ037viF13ugfsIpePH93mX7xfJp97cyDuTZ3cw==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "netbsd"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/netbsd-x64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/netbsd-x64/-/netbsd-x64-0.27.2.tgz",
      "integrity": "sha512-HwGDZ0VLVBY3Y+Nw0JexZy9o/nUAWq9MlV7cahpaXKW6TOzfVno3y3/M8Ga8u8Yr7GldLOov27xiCnqRZf0tCA==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "netbsd"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/openbsd-arm64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/openbsd-arm64/-/openbsd-arm64-0.27.2.tgz",
      "integrity": "sha512-DNIHH2BPQ5551A7oSHD0CKbwIA/Ox7+78/AWkbS5QoRzaqlev2uFayfSxq68EkonB+IKjiuxBFoV8ESJy8bOHA==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "openbsd"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/openbsd-x64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/openbsd-x64/-/openbsd-x64-0.27.2.tgz",
      "integrity": "sha512-/it7w9Nb7+0KFIzjalNJVR5bOzA9Vay+yIPLVHfIQYG/j+j9VTH84aNB8ExGKPU4AzfaEvN9/V4HV+F+vo8OEg==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "openbsd"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/openharmony-arm64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/openharmony-arm64/-/openharmony-arm64-0.27.2.tgz",
      "integrity": "sha512-LRBbCmiU51IXfeXk59csuX/aSaToeG7w48nMwA6049Y4J4+VbWALAuXcs+qcD04rHDuSCSRKdmY63sruDS5qag==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "openharmony"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/sunos-x64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/sunos-x64/-/sunos-x64-0.27.2.tgz",
      "integrity": "sha512-kMtx1yqJHTmqaqHPAzKCAkDaKsffmXkPHThSfRwZGyuqyIeBvf08KSsYXl+abf5HDAPMJIPnbBfXvP2ZC2TfHg==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "sunos"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/win32-arm64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/win32-arm64/-/win32-arm64-0.27.2.tgz",
      "integrity": "sha512-Yaf78O/B3Kkh+nKABUF++bvJv5Ijoy9AN1ww904rOXZFLWVc5OLOfL56W+C8F9xn5JQZa3UX6m+IktJnIb1Jjg==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "win32"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/win32-ia32": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/win32-ia32/-/win32-ia32-0.27.2.tgz",
      "integrity": "sha512-Iuws0kxo4yusk7sw70Xa2E2imZU5HoixzxfGCdxwBdhiDgt9vX9VUCBhqcwY7/uh//78A1hMkkROMJq9l27oLQ==",
      "cpu": [
        "ia32"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "win32"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@esbuild/win32-x64": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/@esbuild/win32-x64/-/win32-x64-0.27.2.tgz",
      "integrity": "sha512-sRdU18mcKf7F+YgheI/zGf5alZatMUTKj/jNS6l744f9u3WFu4v7twcUI9vu4mknF4Y9aDlblIie0IM+5xxaqQ==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "win32"
      ],
      "engines": {
        "node": ">=18"
      }
    },
    "node_modules/@eslint-community/eslint-utils": {
      "version": "4.9.1",
      "resolved": "https://registry.npmjs.org/@eslint-community/eslint-utils/-/eslint-utils-4.9.1.tgz",
      "integrity": "sha512-phrYmNiYppR7znFEdqgfWHXR6NCkZEK7hwWDHZUjit/2/U0r6XvkDl0SYnoM51Hq7FhCGdLDT6zxCCOY1hexsQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "eslint-visitor-keys": "^3.4.3"
      },
      "engines": {
        "node": "^12.22.0 || ^14.17.0 || >=16.0.0"
      },
      "funding": {
        "url": "https://opencollective.com/eslint"
      },
      "peerDependencies": {
        "eslint": "^6.0.0 || ^7.0.0 || >=8.0.0"
      }
    },
    "node_modules/@eslint-community/eslint-utils/node_modules/eslint-visitor-keys": {
      "version": "3.4.3",
      "resolved": "https://registry.npmjs.org/eslint-visitor-keys/-/eslint-visitor-keys-3.4.3.tgz",
      "integrity": "sha512-wpc+LXeiyiisxPlEkUzU6svyS1frIO3Mgxj1fdy7Pm8Ygzguax2N3Fa/D/ag1WqbOprdI+uY6wMUl8/a2G+iag==",
      "dev": true,
      "license": "Apache-2.0",
      "engines": {
        "node": "^12.22.0 || ^14.17.0 || >=16.0.0"
      },
      "funding": {
        "url": "https://opencollective.com/eslint"
      }
    },
    "node_modules/@eslint-community/regexpp": {
      "version": "4.12.2",
      "resolved": "https://registry.npmjs.org/@eslint-community/regexpp/-/regexpp-4.12.2.tgz",
      "integrity": "sha512-EriSTlt5OC9/7SXkRSCAhfSxxoSUgBm33OH+IkwbdpgoqsSsUg7y3uh+IICI/Qg4BBWr3U2i39RpmycbxMq4ew==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": "^12.0.0 || ^14.0.0 || >=16.0.0"
      }
    },
    "node_modules/@eslint/config-array": {
      "version": "0.21.1",
      "resolved": "https://registry.npmjs.org/@eslint/config-array/-/config-array-0.21.1.tgz",
      "integrity": "sha512-aw1gNayWpdI/jSYVgzN5pL0cfzU02GT3NBpeT/DXbx1/1x7ZKxFPd9bwrzygx/qiwIQiJ1sw/zD8qY/kRvlGHA==",
      "dev": true,
      "license": "Apache-2.0",
      "dependencies": {
        "@eslint/object-schema": "^2.1.7",
        "debug": "^4.3.1",
        "minimatch": "^3.1.2"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      }
    },
    "node_modules/@eslint/config-helpers": {
      "version": "0.4.2",
      "resolved": "https://registry.npmjs.org/@eslint/config-helpers/-/config-helpers-0.4.2.tgz",
      "integrity": "sha512-gBrxN88gOIf3R7ja5K9slwNayVcZgK6SOUORm2uBzTeIEfeVaIhOpCtTox3P6R7o2jLFwLFTLnC7kU/RGcYEgw==",
      "dev": true,
      "license": "Apache-2.0",
      "dependencies": {
        "@eslint/core": "^0.17.0"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      }
    },
    "node_modules/@eslint/core": {
      "version": "0.17.0",
      "resolved": "https://registry.npmjs.org/@eslint/core/-/core-0.17.0.tgz",
      "integrity": "sha512-yL/sLrpmtDaFEiUj1osRP4TI2MDz1AddJL+jZ7KSqvBuliN4xqYY54IfdN8qD8Toa6g1iloph1fxQNkjOxrrpQ==",
      "dev": true,
      "license": "Apache-2.0",
      "dependencies": {
        "@types/json-schema": "^7.0.15"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      }
    },
    "node_modules/@eslint/eslintrc": {
      "version": "3.3.3",
      "resolved": "https://registry.npmjs.org/@eslint/eslintrc/-/eslintrc-3.3.3.tgz",
      "integrity": "sha512-Kr+LPIUVKz2qkx1HAMH8q1q6azbqBAsXJUxBl/ODDuVPX45Z9DfwB8tPjTi6nNZ8BuM3nbJxC5zCAg5elnBUTQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "ajv": "^6.12.4",
        "debug": "^4.3.2",
        "espree": "^10.0.1",
        "globals": "^14.0.0",
        "ignore": "^5.2.0",
        "import-fresh": "^3.2.1",
        "js-yaml": "^4.1.1",
        "minimatch": "^3.1.2",
        "strip-json-comments": "^3.1.1"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "url": "https://opencollective.com/eslint"
      }
    },
    "node_modules/@eslint/eslintrc/node_modules/globals": {
      "version": "14.0.0",
      "resolved": "https://registry.npmjs.org/globals/-/globals-14.0.0.tgz",
      "integrity": "sha512-oahGvuMGQlPw/ivIYBjVSrWAfWLBeku5tpPE2fOPLi+WHffIWbuh2tCjhyQhTBPMf5E9jDEH4FOmTYgYwbKwtQ==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=18"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/@eslint/js": {
      "version": "9.39.2",
      "resolved": "https://registry.npmjs.org/@eslint/js/-/js-9.39.2.tgz",
      "integrity": "sha512-q1mjIoW1VX4IvSocvM/vbTiveKC4k9eLrajNEuSsmjymSDEbpGddtpfOoN7YGAqBK3NG+uqo8ia4PDTt8buCYA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "url": "https://eslint.org/donate"
      }
    },
    "node_modules/@eslint/object-schema": {
      "version": "2.1.7",
      "resolved": "https://registry.npmjs.org/@eslint/object-schema/-/object-schema-2.1.7.tgz",
      "integrity": "sha512-VtAOaymWVfZcmZbp6E2mympDIHvyjXs/12LqWYjVw6qjrfF+VK+fyG33kChz3nnK+SU5/NeHOqrTEHS8sXO3OA==",
      "dev": true,
      "license": "Apache-2.0",
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      }
    },
    "node_modules/@eslint/plugin-kit": {
      "version": "0.4.1",
      "resolved": "https://registry.npmjs.org/@eslint/plugin-kit/-/plugin-kit-0.4.1.tgz",
      "integrity": "sha512-43/qtrDUokr7LJqoF2c3+RInu/t4zfrpYdoSDfYyhg52rwLV6TnOvdG4fXm7IkSB3wErkcmJS9iEhjVtOSEjjA==",
      "dev": true,
      "license": "Apache-2.0",
      "dependencies": {
        "@eslint/core": "^0.17.0",
        "levn": "^0.4.1"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      }
    },
    "node_modules/@floating-ui/core": {
      "version": "1.7.3",
      "resolved": "https://registry.npmjs.org/@floating-ui/core/-/core-1.7.3.tgz",
      "integrity": "sha512-sGnvb5dmrJaKEZ+LDIpguvdX3bDlEllmv4/ClQ9awcmCZrlx5jQyyMWFM5kBI+EyNOCDDiKk8il0zeuX3Zlg/w==",
      "license": "MIT",
      "dependencies": {
        "@floating-ui/utils": "^0.2.10"
      }
    },
    "node_modules/@floating-ui/dom": {
      "version": "1.7.4",
      "resolved": "https://registry.npmjs.org/@floating-ui/dom/-/dom-1.7.4.tgz",
      "integrity": "sha512-OOchDgh4F2CchOX94cRVqhvy7b3AFb+/rQXyswmzmGakRfkMgoWVjfnLWkRirfLEfuD4ysVW16eXzwt3jHIzKA==",
      "license": "MIT",
      "dependencies": {
        "@floating-ui/core": "^1.7.3",
        "@floating-ui/utils": "^0.2.10"
      }
    },
    "node_modules/@floating-ui/react-dom": {
      "version": "2.1.6",
      "resolved": "https://registry.npmjs.org/@floating-ui/react-dom/-/react-dom-2.1.6.tgz",
      "integrity": "sha512-4JX6rEatQEvlmgU80wZyq9RT96HZJa88q8hp0pBd+LrczeDI4o6uA2M+uvxngVHo4Ihr8uibXxH6+70zhAFrVw==",
      "license": "MIT",
      "dependencies": {
        "@floating-ui/dom": "^1.7.4"
      },
      "peerDependencies": {
        "react": ">=16.8.0",
        "react-dom": ">=16.8.0"
      }
    },
    "node_modules/@floating-ui/utils": {
      "version": "0.2.10",
      "resolved": "https://registry.npmjs.org/@floating-ui/utils/-/utils-0.2.10.tgz",
      "integrity": "sha512-aGTxbpbg8/b5JfU1HXSrbH3wXZuLPJcNEcZQFMxLs3oSzgtVu6nFPkbbGGUvBcUjKV2YyB9Wxxabo+HEH9tcRQ==",
      "license": "MIT"
    },
    "node_modules/@hookform/resolvers": {
      "version": "5.2.2",
      "resolved": "https://registry.npmjs.org/@hookform/resolvers/-/resolvers-5.2.2.tgz",
      "integrity": "sha512-A/IxlMLShx3KjV/HeTcTfaMxdwy690+L/ZADoeaTltLx+CVuzkeVIPuybK3jrRfw7YZnmdKsVVHAlEPIAEUNlA==",
      "license": "MIT",
      "dependencies": {
        "@standard-schema/utils": "^0.3.0"
      },
      "peerDependencies": {
        "react-hook-form": "^7.55.0"
      }
    },
    "node_modules/@humanfs/core": {
      "version": "0.19.1",
      "resolved": "https://registry.npmjs.org/@humanfs/core/-/core-0.19.1.tgz",
      "integrity": "sha512-5DyQ4+1JEUzejeK1JGICcideyfUbGixgS9jNgex5nqkW+cY7WZhxBigmieN5Qnw9ZosSNVC9KQKyb+GUaGyKUA==",
      "dev": true,
      "license": "Apache-2.0",
      "engines": {
        "node": ">=18.18.0"
      }
    },
    "node_modules/@humanfs/node": {
      "version": "0.16.7",
      "resolved": "https://registry.npmjs.org/@humanfs/node/-/node-0.16.7.tgz",
      "integrity": "sha512-/zUx+yOsIrG4Y43Eh2peDeKCxlRt/gET6aHfaKpuq267qXdYDFViVHfMaLyygZOnl0kGWxFIgsBy8QFuTLUXEQ==",
      "dev": true,
      "license": "Apache-2.0",
      "dependencies": {
        "@humanfs/core": "^0.19.1",
        "@humanwhocodes/retry": "^0.4.0"
      },
      "engines": {
        "node": ">=18.18.0"
      }
    },
    "node_modules/@humanwhocodes/module-importer": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/@humanwhocodes/module-importer/-/module-importer-1.0.1.tgz",
      "integrity": "sha512-bxveV4V8v5Yb4ncFTT3rPSgZBOpCkjfK0y4oVVVJwIuDVBRMDXrPyXRL988i5ap9m9bnyEEjWfm5WkBmtffLfA==",
      "dev": true,
      "license": "Apache-2.0",
      "engines": {
        "node": ">=12.22"
      },
      "funding": {
        "type": "github",
        "url": "https://github.com/sponsors/nzakas"
      }
    },
    "node_modules/@humanwhocodes/retry": {
      "version": "0.4.3",
      "resolved": "https://registry.npmjs.org/@humanwhocodes/retry/-/retry-0.4.3.tgz",
      "integrity": "sha512-bV0Tgo9K4hfPCek+aMAn81RppFKv2ySDQeMoSZuvTASywNTnVJCArCZE2FWqpvIatKu7VMRLWlR1EazvVhDyhQ==",
      "dev": true,
      "license": "Apache-2.0",
      "engines": {
        "node": ">=18.18"
      },
      "funding": {
        "type": "github",
        "url": "https://github.com/sponsors/nzakas"
      }
    },
    "node_modules/@jridgewell/gen-mapping": {
      "version": "0.3.13",
      "resolved": "https://registry.npmjs.org/@jridgewell/gen-mapping/-/gen-mapping-0.3.13.tgz",
      "integrity": "sha512-2kkt/7niJ6MgEPxF0bYdQ6etZaA+fQvDcLKckhy1yIQOzaoKjBBjSj63/aLVjYE3qhRt5dvM+uUyfCg6UKCBbA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@jridgewell/sourcemap-codec": "^1.5.0",
        "@jridgewell/trace-mapping": "^0.3.24"
      }
    },
    "node_modules/@jridgewell/remapping": {
      "version": "2.3.5",
      "resolved": "https://registry.npmjs.org/@jridgewell/remapping/-/remapping-2.3.5.tgz",
      "integrity": "sha512-LI9u/+laYG4Ds1TDKSJW2YPrIlcVYOwi2fUC6xB43lueCjgxV4lffOCZCtYFiH6TNOX+tQKXx97T4IKHbhyHEQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@jridgewell/gen-mapping": "^0.3.5",
        "@jridgewell/trace-mapping": "^0.3.24"
      }
    },
    "node_modules/@jridgewell/resolve-uri": {
      "version": "3.1.2",
      "resolved": "https://registry.npmjs.org/@jridgewell/resolve-uri/-/resolve-uri-3.1.2.tgz",
      "integrity": "sha512-bRISgCIjP20/tbWSPWMEi54QVPRZExkuD9lJL+UIxUKtwVJA8wW1Trb1jMs1RFXo1CBTNZ/5hpC9QvmKWdopKw==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.0.0"
      }
    },
    "node_modules/@jridgewell/sourcemap-codec": {
      "version": "1.5.5",
      "resolved": "https://registry.npmjs.org/@jridgewell/sourcemap-codec/-/sourcemap-codec-1.5.5.tgz",
      "integrity": "sha512-cYQ9310grqxueWbl+WuIUIaiUaDcj7WOq5fVhEljNVgRfOUhY9fy2zTvfoqWsnebh8Sl70VScFbICvJnLKB0Og==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/@jridgewell/trace-mapping": {
      "version": "0.3.31",
      "resolved": "https://registry.npmjs.org/@jridgewell/trace-mapping/-/trace-mapping-0.3.31.tgz",
      "integrity": "sha512-zzNR+SdQSDJzc8joaeP8QQoCQr8NuYx2dIIytl1QeBEZHJ9uW6hebsrYgbz8hJwUQao3TWCMtmfV8Nu1twOLAw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@jridgewell/resolve-uri": "^3.1.0",
        "@jridgewell/sourcemap-codec": "^1.4.14"
      }
    },
    "node_modules/@nodelib/fs.scandir": {
      "version": "2.1.5",
      "resolved": "https://registry.npmjs.org/@nodelib/fs.scandir/-/fs.scandir-2.1.5.tgz",
      "integrity": "sha512-vq24Bq3ym5HEQm2NKCr3yXDwjc7vTsEThRDnkp2DK9p1uqLR+DHurm/NOTo0KG7HYHU7eppKZj3MyqYuMBf62g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@nodelib/fs.stat": "2.0.5",
        "run-parallel": "^1.1.9"
      },
      "engines": {
        "node": ">= 8"
      }
    },
    "node_modules/@nodelib/fs.stat": {
      "version": "2.0.5",
      "resolved": "https://registry.npmjs.org/@nodelib/fs.stat/-/fs.stat-2.0.5.tgz",
      "integrity": "sha512-RkhPPp2zrqDAQA/2jNhnztcPAlv64XdhIp7a7454A5ovI7Bukxgt7MX7udwAu3zg1DcpPU0rz3VV1SeaqvY4+A==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 8"
      }
    },
    "node_modules/@nodelib/fs.walk": {
      "version": "1.2.8",
      "resolved": "https://registry.npmjs.org/@nodelib/fs.walk/-/fs.walk-1.2.8.tgz",
      "integrity": "sha512-oGB+UxlgWcgQkgwo8GcEGwemoTFt3FIO9ababBmaGwXIoBKZ+GTy0pP185beGg7Llih/NSHSV2XAs1lnznocSg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@nodelib/fs.scandir": "2.1.5",
        "fastq": "^1.6.0"
      },
      "engines": {
        "node": ">= 8"
      }
    },
    "node_modules/@radix-ui/number": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/number/-/number-1.1.1.tgz",
      "integrity": "sha512-MkKCwxlXTgz6CFoJx3pCwn07GKp36+aZyu/u2Ln2VrA5DcdyCZkASEDBTd8x5whTQQL5CiYf4prXKLcgQdv29g==",
      "license": "MIT"
    },
    "node_modules/@radix-ui/primitive": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/primitive/-/primitive-1.1.3.tgz",
      "integrity": "sha512-JTF99U/6XIjCBo0wqkU5sK10glYe27MRRsfwoiq5zzOEZLHU3A3KCMa5X/azekYRCJ0HlwI0crAXS/5dEHTzDg==",
      "license": "MIT"
    },
    "node_modules/@radix-ui/react-accordion": {
      "version": "1.2.12",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-accordion/-/react-accordion-1.2.12.tgz",
      "integrity": "sha512-T4nygeh9YE9dLRPhAHSeOZi7HBXo+0kYIPJXayZfvWOWA0+n3dESrZbjfDPUABkUNym6Hd+f2IR113To8D2GPA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-collapsible": "1.1.12",
        "@radix-ui/react-collection": "1.1.7",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-alert-dialog": {
      "version": "1.1.15",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-alert-dialog/-/react-alert-dialog-1.1.15.tgz",
      "integrity": "sha512-oTVLkEw5GpdRe29BqJ0LSDFWI3qu0vR1M0mUkOQWDIUnY/QIkLpgDMWuKxP94c2NAC2LGcgVhG1ImF3jkZ5wXw==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-dialog": "1.1.15",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-slot": "1.2.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-alert-dialog/node_modules/@radix-ui/react-slot": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.3.tgz",
      "integrity": "sha512-aeNmHnBxbi2St0au6VBVC7JXFlhLlOnvIIlePNniyUNAClzmtAUEY8/pBiK3iHjufOlwA+c20/8jngo7xcrg8A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-arrow": {
      "version": "1.1.7",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-arrow/-/react-arrow-1.1.7.tgz",
      "integrity": "sha512-F+M1tLhO+mlQaOWspE8Wstg+z6PwxwRd8oQ8IXceWz92kfAmalTRf0EjrouQeo7QssEPfCn05B4Ihs1K9WQ/7w==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-primitive": "2.1.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-aspect-ratio": {
      "version": "1.1.8",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-aspect-ratio/-/react-aspect-ratio-1.1.8.tgz",
      "integrity": "sha512-5nZrJTF7gH+e0nZS7/QxFz6tJV4VimhQb1avEgtsJxvvIp5JilL+c58HICsKzPxghdwaDt48hEfPM1au4zGy+w==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-primitive": "2.1.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-aspect-ratio/node_modules/@radix-ui/react-primitive": {
      "version": "2.1.4",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-primitive/-/react-primitive-2.1.4.tgz",
      "integrity": "sha512-9hQc4+GNVtJAIEPEqlYqW5RiYdrr8ea5XQ0ZOnD6fgru+83kqT15mq2OCcbe8KnjRZl5vF3ks69AKz3kh1jrhg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-slot": "1.2.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-avatar": {
      "version": "1.1.11",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-avatar/-/react-avatar-1.1.11.tgz",
      "integrity": "sha512-0Qk603AHGV28BOBO34p7IgD5m+V5Sg/YovfayABkoDDBM5d3NCx0Mp4gGrjzLGes1jV5eNOE1r3itqOR33VC6Q==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-context": "1.1.3",
        "@radix-ui/react-primitive": "2.1.4",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "@radix-ui/react-use-is-hydrated": "0.1.0",
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-avatar/node_modules/@radix-ui/react-context": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-context/-/react-context-1.1.3.tgz",
      "integrity": "sha512-ieIFACdMpYfMEjF0rEf5KLvfVyIkOz6PDGyNnP+u+4xQ6jny3VCgA4OgXOwNx2aUkxn8zx9fiVcM8CfFYv9Lxw==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-avatar/node_modules/@radix-ui/react-primitive": {
      "version": "2.1.4",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-primitive/-/react-primitive-2.1.4.tgz",
      "integrity": "sha512-9hQc4+GNVtJAIEPEqlYqW5RiYdrr8ea5XQ0ZOnD6fgru+83kqT15mq2OCcbe8KnjRZl5vF3ks69AKz3kh1jrhg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-slot": "1.2.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-checkbox": {
      "version": "1.3.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-checkbox/-/react-checkbox-1.3.3.tgz",
      "integrity": "sha512-wBbpv+NQftHDdG86Qc0pIyXk5IR3tM8Vd0nWLKDcX8nNn4nXFOFwsKuqw2okA/1D/mpaAkmuyndrPJTYDNZtFw==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "@radix-ui/react-use-previous": "1.1.1",
        "@radix-ui/react-use-size": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-collapsible": {
      "version": "1.1.12",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-collapsible/-/react-collapsible-1.1.12.tgz",
      "integrity": "sha512-Uu+mSh4agx2ib1uIGPP4/CKNULyajb3p92LsVXmH2EHVMTfZWpll88XJ0j4W0z3f8NK1eYl1+Mf/szHPmcHzyA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-collection": {
      "version": "1.1.7",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-collection/-/react-collection-1.1.7.tgz",
      "integrity": "sha512-Fh9rGN0MoI4ZFUNyfFVNU4y9LUz93u9/0K+yLgA2bwRojxM8JU1DyvvMBabnZPBgMWREAJvU2jjVzq+LrFUglw==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-slot": "1.2.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-collection/node_modules/@radix-ui/react-slot": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.3.tgz",
      "integrity": "sha512-aeNmHnBxbi2St0au6VBVC7JXFlhLlOnvIIlePNniyUNAClzmtAUEY8/pBiK3iHjufOlwA+c20/8jngo7xcrg8A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-compose-refs": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-compose-refs/-/react-compose-refs-1.1.2.tgz",
      "integrity": "sha512-z4eqJvfiNnFMHIIvXP3CY57y2WJs5g2v3X0zm9mEJkrkNv4rDxu+sg9Jh8EkXyeqBkB7SOcboo9dMVqhyrACIg==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-context": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-context/-/react-context-1.1.2.tgz",
      "integrity": "sha512-jCi/QKUM2r1Ju5a3J64TH2A5SpKAgh0LpknyqdQ4m6DCV0xJ2HG1xARRwNGPQfi1SLdLWZ1OJz6F4OMBBNiGJA==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-context-menu": {
      "version": "2.2.16",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-context-menu/-/react-context-menu-2.2.16.tgz",
      "integrity": "sha512-O8morBEW+HsVG28gYDZPTrT9UUovQUlJue5YO836tiTJhuIWBm/zQHc7j388sHWtdH/xUZurK9olD2+pcqx5ww==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-menu": "2.1.16",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-dialog": {
      "version": "1.1.15",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-dialog/-/react-dialog-1.1.15.tgz",
      "integrity": "sha512-TCglVRtzlffRNxRMEyR36DGBLJpeusFcgMVD9PZEzAKnUs1lKCgX5u9BmC2Yg+LL9MgZDugFFs1Vl+Jp4t/PGw==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-dismissable-layer": "1.1.11",
        "@radix-ui/react-focus-guards": "1.1.3",
        "@radix-ui/react-focus-scope": "1.1.7",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-portal": "1.1.9",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-slot": "1.2.3",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "aria-hidden": "^1.2.4",
        "react-remove-scroll": "^2.6.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-dialog/node_modules/@radix-ui/react-slot": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.3.tgz",
      "integrity": "sha512-aeNmHnBxbi2St0au6VBVC7JXFlhLlOnvIIlePNniyUNAClzmtAUEY8/pBiK3iHjufOlwA+c20/8jngo7xcrg8A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-direction": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-direction/-/react-direction-1.1.1.tgz",
      "integrity": "sha512-1UEWRX6jnOA2y4H5WczZ44gOOjTEmlqv1uNW4GAJEO5+bauCBhv8snY65Iw5/VOS/ghKN9gr2KjnLKxrsvoMVw==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-dismissable-layer": {
      "version": "1.1.11",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-dismissable-layer/-/react-dismissable-layer-1.1.11.tgz",
      "integrity": "sha512-Nqcp+t5cTB8BinFkZgXiMJniQH0PsUt2k51FUhbdfeKvc4ACcG2uQniY/8+h1Yv6Kza4Q7lD7PQV0z0oicE0Mg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "@radix-ui/react-use-escape-keydown": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-dropdown-menu": {
      "version": "2.1.16",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-dropdown-menu/-/react-dropdown-menu-2.1.16.tgz",
      "integrity": "sha512-1PLGQEynI/3OX/ftV54COn+3Sud/Mn8vALg2rWnBLnRaGtJDduNW/22XjlGgPdpcIbiQxjKtb7BkcjP00nqfJw==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-menu": "2.1.16",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-focus-guards": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-focus-guards/-/react-focus-guards-1.1.3.tgz",
      "integrity": "sha512-0rFg/Rj2Q62NCm62jZw0QX7a3sz6QCQU0LpZdNrJX8byRGaGVTqbrW9jAoIAHyMQqsNpeZ81YgSizOt5WXq0Pw==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-focus-scope": {
      "version": "1.1.7",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-focus-scope/-/react-focus-scope-1.1.7.tgz",
      "integrity": "sha512-t2ODlkXBQyn7jkl6TNaw/MtVEVvIGelJDCG41Okq/KwUsJBwQ4XVZsHAVUkK4mBv3ewiAS3PGuUWuY2BoK4ZUw==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-callback-ref": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-hover-card": {
      "version": "1.1.15",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-hover-card/-/react-hover-card-1.1.15.tgz",
      "integrity": "sha512-qgTkjNT1CfKMoP0rcasmlH2r1DAiYicWsDsufxl940sT2wHNEWWv6FMWIQXWhVdmC1d/HYfbhQx60KYyAtKxjg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-dismissable-layer": "1.1.11",
        "@radix-ui/react-popper": "1.2.8",
        "@radix-ui/react-portal": "1.1.9",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-id": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-id/-/react-id-1.1.1.tgz",
      "integrity": "sha512-kGkGegYIdQsOb4XjsfM97rXsiHaBwco+hFI66oO4s9LU+PLAC5oJ7khdOVFxkhsmlbpUqDAvXw11CluXP+jkHg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-label": {
      "version": "2.1.8",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-label/-/react-label-2.1.8.tgz",
      "integrity": "sha512-FmXs37I6hSBVDlO4y764TNz1rLgKwjJMQ0EGte6F3Cb3f4bIuHB/iLa/8I9VKkmOy+gNHq8rql3j686ACVV21A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-primitive": "2.1.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-label/node_modules/@radix-ui/react-primitive": {
      "version": "2.1.4",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-primitive/-/react-primitive-2.1.4.tgz",
      "integrity": "sha512-9hQc4+GNVtJAIEPEqlYqW5RiYdrr8ea5XQ0ZOnD6fgru+83kqT15mq2OCcbe8KnjRZl5vF3ks69AKz3kh1jrhg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-slot": "1.2.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-menu": {
      "version": "2.1.16",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-menu/-/react-menu-2.1.16.tgz",
      "integrity": "sha512-72F2T+PLlphrqLcAotYPp0uJMr5SjP5SL01wfEspJbru5Zs5vQaSHb4VB3ZMJPimgHHCHG7gMOeOB9H3Hdmtxg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-collection": "1.1.7",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-dismissable-layer": "1.1.11",
        "@radix-ui/react-focus-guards": "1.1.3",
        "@radix-ui/react-focus-scope": "1.1.7",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-popper": "1.2.8",
        "@radix-ui/react-portal": "1.1.9",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-roving-focus": "1.1.11",
        "@radix-ui/react-slot": "1.2.3",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "aria-hidden": "^1.2.4",
        "react-remove-scroll": "^2.6.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-menu/node_modules/@radix-ui/react-slot": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.3.tgz",
      "integrity": "sha512-aeNmHnBxbi2St0au6VBVC7JXFlhLlOnvIIlePNniyUNAClzmtAUEY8/pBiK3iHjufOlwA+c20/8jngo7xcrg8A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-menubar": {
      "version": "1.1.16",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-menubar/-/react-menubar-1.1.16.tgz",
      "integrity": "sha512-EB1FktTz5xRRi2Er974AUQZWg2yVBb1yjip38/lgwtCVRd3a+maUoGHN/xs9Yv8SY8QwbSEb+YrxGadVWbEutA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-collection": "1.1.7",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-menu": "2.1.16",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-roving-focus": "1.1.11",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-navigation-menu": {
      "version": "1.2.14",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-navigation-menu/-/react-navigation-menu-1.2.14.tgz",
      "integrity": "sha512-YB9mTFQvCOAQMHU+C/jVl96WmuWeltyUEpRJJky51huhds5W2FQr1J8D/16sQlf0ozxkPK8uF3niQMdUwZPv5w==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-collection": "1.1.7",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-dismissable-layer": "1.1.11",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "@radix-ui/react-use-layout-effect": "1.1.1",
        "@radix-ui/react-use-previous": "1.1.1",
        "@radix-ui/react-visually-hidden": "1.2.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-popover": {
      "version": "1.1.15",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-popover/-/react-popover-1.1.15.tgz",
      "integrity": "sha512-kr0X2+6Yy/vJzLYJUPCZEc8SfQcf+1COFoAqauJm74umQhta9M7lNJHP7QQS3vkvcGLQUbWpMzwrXYwrYztHKA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-dismissable-layer": "1.1.11",
        "@radix-ui/react-focus-guards": "1.1.3",
        "@radix-ui/react-focus-scope": "1.1.7",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-popper": "1.2.8",
        "@radix-ui/react-portal": "1.1.9",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-slot": "1.2.3",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "aria-hidden": "^1.2.4",
        "react-remove-scroll": "^2.6.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-popover/node_modules/@radix-ui/react-slot": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.3.tgz",
      "integrity": "sha512-aeNmHnBxbi2St0au6VBVC7JXFlhLlOnvIIlePNniyUNAClzmtAUEY8/pBiK3iHjufOlwA+c20/8jngo7xcrg8A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-popper": {
      "version": "1.2.8",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-popper/-/react-popper-1.2.8.tgz",
      "integrity": "sha512-0NJQ4LFFUuWkE7Oxf0htBKS6zLkkjBH+hM1uk7Ng705ReR8m/uelduy1DBo0PyBXPKVnBA6YBlU94MBGXrSBCw==",
      "license": "MIT",
      "dependencies": {
        "@floating-ui/react-dom": "^2.0.0",
        "@radix-ui/react-arrow": "1.1.7",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "@radix-ui/react-use-layout-effect": "1.1.1",
        "@radix-ui/react-use-rect": "1.1.1",
        "@radix-ui/react-use-size": "1.1.1",
        "@radix-ui/rect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-portal": {
      "version": "1.1.9",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-portal/-/react-portal-1.1.9.tgz",
      "integrity": "sha512-bpIxvq03if6UNwXZ+HTK71JLh4APvnXntDc6XOX8UVq4XQOVl7lwok0AvIl+b8zgCw3fSaVTZMpAPPagXbKmHQ==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-presence": {
      "version": "1.1.5",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-presence/-/react-presence-1.1.5.tgz",
      "integrity": "sha512-/jfEwNDdQVBCNvjkGit4h6pMOzq8bHkopq458dPt2lMjx+eBQUohZNG9A7DtO/O5ukSbxuaNGXMjHicgwy6rQQ==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-primitive": {
      "version": "2.1.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-primitive/-/react-primitive-2.1.3.tgz",
      "integrity": "sha512-m9gTwRkhy2lvCPe6QJp4d3G1TYEUHn/FzJUtq9MjH46an1wJU+GdoGC5VLof8RX8Ft/DlpshApkhswDLZzHIcQ==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-slot": "1.2.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-primitive/node_modules/@radix-ui/react-slot": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.3.tgz",
      "integrity": "sha512-aeNmHnBxbi2St0au6VBVC7JXFlhLlOnvIIlePNniyUNAClzmtAUEY8/pBiK3iHjufOlwA+c20/8jngo7xcrg8A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-progress": {
      "version": "1.1.8",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-progress/-/react-progress-1.1.8.tgz",
      "integrity": "sha512-+gISHcSPUJ7ktBy9RnTqbdKW78bcGke3t6taawyZ71pio1JewwGSJizycs7rLhGTvMJYCQB1DBK4KQsxs7U8dA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-context": "1.1.3",
        "@radix-ui/react-primitive": "2.1.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-progress/node_modules/@radix-ui/react-context": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-context/-/react-context-1.1.3.tgz",
      "integrity": "sha512-ieIFACdMpYfMEjF0rEf5KLvfVyIkOz6PDGyNnP+u+4xQ6jny3VCgA4OgXOwNx2aUkxn8zx9fiVcM8CfFYv9Lxw==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-progress/node_modules/@radix-ui/react-primitive": {
      "version": "2.1.4",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-primitive/-/react-primitive-2.1.4.tgz",
      "integrity": "sha512-9hQc4+GNVtJAIEPEqlYqW5RiYdrr8ea5XQ0ZOnD6fgru+83kqT15mq2OCcbe8KnjRZl5vF3ks69AKz3kh1jrhg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-slot": "1.2.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-radio-group": {
      "version": "1.3.8",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-radio-group/-/react-radio-group-1.3.8.tgz",
      "integrity": "sha512-VBKYIYImA5zsxACdisNQ3BjCBfmbGH3kQlnFVqlWU4tXwjy7cGX8ta80BcrO+WJXIn5iBylEH3K6ZTlee//lgQ==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-roving-focus": "1.1.11",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "@radix-ui/react-use-previous": "1.1.1",
        "@radix-ui/react-use-size": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-roving-focus": {
      "version": "1.1.11",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-roving-focus/-/react-roving-focus-1.1.11.tgz",
      "integrity": "sha512-7A6S9jSgm/S+7MdtNDSb+IU859vQqJ/QAtcYQcfFC6W8RS4IxIZDldLR0xqCFZ6DCyrQLjLPsxtTNch5jVA4lA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-collection": "1.1.7",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-scroll-area": {
      "version": "1.2.10",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-scroll-area/-/react-scroll-area-1.2.10.tgz",
      "integrity": "sha512-tAXIa1g3sM5CGpVT0uIbUx/U3Gs5N8T52IICuCtObaos1S8fzsrPXG5WObkQN3S6NVl6wKgPhAIiBGbWnvc97A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/number": "1.1.1",
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-select": {
      "version": "2.2.6",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-select/-/react-select-2.2.6.tgz",
      "integrity": "sha512-I30RydO+bnn2PQztvo25tswPH+wFBjehVGtmagkU78yMdwTwVf12wnAOF+AeP8S2N8xD+5UPbGhkUfPyvT+mwQ==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/number": "1.1.1",
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-collection": "1.1.7",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-dismissable-layer": "1.1.11",
        "@radix-ui/react-focus-guards": "1.1.3",
        "@radix-ui/react-focus-scope": "1.1.7",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-popper": "1.2.8",
        "@radix-ui/react-portal": "1.1.9",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-slot": "1.2.3",
        "@radix-ui/react-use-callback-ref": "1.1.1",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "@radix-ui/react-use-layout-effect": "1.1.1",
        "@radix-ui/react-use-previous": "1.1.1",
        "@radix-ui/react-visually-hidden": "1.2.3",
        "aria-hidden": "^1.2.4",
        "react-remove-scroll": "^2.6.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-select/node_modules/@radix-ui/react-slot": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.3.tgz",
      "integrity": "sha512-aeNmHnBxbi2St0au6VBVC7JXFlhLlOnvIIlePNniyUNAClzmtAUEY8/pBiK3iHjufOlwA+c20/8jngo7xcrg8A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-separator": {
      "version": "1.1.8",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-separator/-/react-separator-1.1.8.tgz",
      "integrity": "sha512-sDvqVY4itsKwwSMEe0jtKgfTh+72Sy3gPmQpjqcQneqQ4PFmr/1I0YA+2/puilhggCe2gJcx5EBAYFkWkdpa5g==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-primitive": "2.1.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-separator/node_modules/@radix-ui/react-primitive": {
      "version": "2.1.4",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-primitive/-/react-primitive-2.1.4.tgz",
      "integrity": "sha512-9hQc4+GNVtJAIEPEqlYqW5RiYdrr8ea5XQ0ZOnD6fgru+83kqT15mq2OCcbe8KnjRZl5vF3ks69AKz3kh1jrhg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-slot": "1.2.4"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-slider": {
      "version": "1.3.6",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slider/-/react-slider-1.3.6.tgz",
      "integrity": "sha512-JPYb1GuM1bxfjMRlNLE+BcmBC8onfCi60Blk7OBqi2MLTFdS+8401U4uFjnwkOr49BLmXxLC6JHkvAsx5OJvHw==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/number": "1.1.1",
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-collection": "1.1.7",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "@radix-ui/react-use-layout-effect": "1.1.1",
        "@radix-ui/react-use-previous": "1.1.1",
        "@radix-ui/react-use-size": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-slot": {
      "version": "1.2.4",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.4.tgz",
      "integrity": "sha512-Jl+bCv8HxKnlTLVrcDE8zTMJ09R9/ukw4qBs/oZClOfoQk/cOTbDn+NceXfV7j09YPVQUryJPHurafcSg6EVKA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-switch": {
      "version": "1.2.6",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-switch/-/react-switch-1.2.6.tgz",
      "integrity": "sha512-bByzr1+ep1zk4VubeEVViV592vu2lHE2BZY5OnzehZqOOgogN80+mNtCqPkhn2gklJqOpxWgPoYTSnhBCqpOXQ==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "@radix-ui/react-use-previous": "1.1.1",
        "@radix-ui/react-use-size": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-tabs": {
      "version": "1.1.13",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-tabs/-/react-tabs-1.1.13.tgz",
      "integrity": "sha512-7xdcatg7/U+7+Udyoj2zodtI9H/IIopqo+YOIcZOq1nJwXWBZ9p8xiu5llXlekDbZkca79a/fozEYQXIA4sW6A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-roving-focus": "1.1.11",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-toggle": {
      "version": "1.1.10",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-toggle/-/react-toggle-1.1.10.tgz",
      "integrity": "sha512-lS1odchhFTeZv3xwHH31YPObmJn8gOg7Lq12inrr0+BH/l3Tsq32VfjqH1oh80ARM3mlkfMic15n0kg4sD1poQ==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-toggle-group": {
      "version": "1.1.11",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-toggle-group/-/react-toggle-group-1.1.11.tgz",
      "integrity": "sha512-5umnS0T8JQzQT6HbPyO7Hh9dgd82NmS36DQr+X/YJ9ctFNCiiQd6IJAYYZ33LUwm8M+taCz5t2ui29fHZc4Y6Q==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-direction": "1.1.1",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-roving-focus": "1.1.11",
        "@radix-ui/react-toggle": "1.1.10",
        "@radix-ui/react-use-controllable-state": "1.2.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-tooltip": {
      "version": "1.2.8",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-tooltip/-/react-tooltip-1.2.8.tgz",
      "integrity": "sha512-tY7sVt1yL9ozIxvmbtN5qtmH2krXcBCfjEiCgKGLqunJHvgvZG2Pcl2oQ3kbcZARb1BGEHdkLzcYGO8ynVlieg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/primitive": "1.1.3",
        "@radix-ui/react-compose-refs": "1.1.2",
        "@radix-ui/react-context": "1.1.2",
        "@radix-ui/react-dismissable-layer": "1.1.11",
        "@radix-ui/react-id": "1.1.1",
        "@radix-ui/react-popper": "1.2.8",
        "@radix-ui/react-portal": "1.1.9",
        "@radix-ui/react-presence": "1.1.5",
        "@radix-ui/react-primitive": "2.1.3",
        "@radix-ui/react-slot": "1.2.3",
        "@radix-ui/react-use-controllable-state": "1.2.2",
        "@radix-ui/react-visually-hidden": "1.2.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-tooltip/node_modules/@radix-ui/react-slot": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-slot/-/react-slot-1.2.3.tgz",
      "integrity": "sha512-aeNmHnBxbi2St0au6VBVC7JXFlhLlOnvIIlePNniyUNAClzmtAUEY8/pBiK3iHjufOlwA+c20/8jngo7xcrg8A==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "1.1.2"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-callback-ref": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-callback-ref/-/react-use-callback-ref-1.1.1.tgz",
      "integrity": "sha512-FkBMwD+qbGQeMu1cOHnuGB6x4yzPjho8ap5WtbEJ26umhgqVXbhekKUQO+hZEL1vU92a3wHwdp0HAcqAUF5iDg==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-controllable-state": {
      "version": "1.2.2",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-controllable-state/-/react-use-controllable-state-1.2.2.tgz",
      "integrity": "sha512-BjasUjixPFdS+NKkypcyyN5Pmg83Olst0+c6vGov0diwTEo6mgdqVR6hxcEgFuh4QrAs7Rc+9KuGJ9TVCj0Zzg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-use-effect-event": "0.0.2",
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-effect-event": {
      "version": "0.0.2",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-effect-event/-/react-use-effect-event-0.0.2.tgz",
      "integrity": "sha512-Qp8WbZOBe+blgpuUT+lw2xheLP8q0oatc9UpmiemEICxGvFLYmHm9QowVZGHtJlGbS6A6yJ3iViad/2cVjnOiA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-escape-keydown": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-escape-keydown/-/react-use-escape-keydown-1.1.1.tgz",
      "integrity": "sha512-Il0+boE7w/XebUHyBjroE+DbByORGR9KKmITzbR7MyQ4akpORYP/ZmbhAr0DG7RmmBqoOnZdy2QlvajJ2QA59g==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-use-callback-ref": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-is-hydrated": {
      "version": "0.1.0",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-is-hydrated/-/react-use-is-hydrated-0.1.0.tgz",
      "integrity": "sha512-U+UORVEq+cTnRIaostJv9AGdV3G6Y+zbVd+12e18jQ5A3c0xL03IhnHuiU4UV69wolOQp5GfR58NW/EgdQhwOA==",
      "license": "MIT",
      "dependencies": {
        "use-sync-external-store": "^1.5.0"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-layout-effect": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-layout-effect/-/react-use-layout-effect-1.1.1.tgz",
      "integrity": "sha512-RbJRS4UWQFkzHTTwVymMTUv8EqYhOp8dOOviLj2ugtTiXRaRQS7GLGxZTLL1jWhMeoSCf5zmcZkqTl9IiYfXcQ==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-previous": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-previous/-/react-use-previous-1.1.1.tgz",
      "integrity": "sha512-2dHfToCj/pzca2Ck724OZ5L0EVrr3eHRNsG/b3xQJLA2hZpVCS99bLAX+hm1IHXDEnzU6by5z/5MIY794/a8NQ==",
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-rect": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-rect/-/react-use-rect-1.1.1.tgz",
      "integrity": "sha512-QTYuDesS0VtuHNNvMh+CjlKJ4LJickCMUAqjlE3+j8w+RlRpwyX3apEQKGFzbZGdo7XNG1tXa+bQqIE7HIXT2w==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/rect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-use-size": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-use-size/-/react-use-size-1.1.1.tgz",
      "integrity": "sha512-ewrXRDTAqAXlkl6t/fkXWNAhFX9I+CkKlw6zjEwk86RSPKwZr3xpBRso655aqYafwtnbpHLj6toFzmd6xdVptQ==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-use-layout-effect": "1.1.1"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/react-visually-hidden": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/@radix-ui/react-visually-hidden/-/react-visually-hidden-1.2.3.tgz",
      "integrity": "sha512-pzJq12tEaaIhqjbzpCuv/OypJY/BPavOofm+dbab+MHLajy277+1lLm6JFcGgF5eskJ6mquGirhXY2GD/8u8Ug==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-primitive": "2.1.3"
      },
      "peerDependencies": {
        "@types/react": "*",
        "@types/react-dom": "*",
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        },
        "@types/react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/@radix-ui/rect": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/@radix-ui/rect/-/rect-1.1.1.tgz",
      "integrity": "sha512-HPwpGIzkl28mWyZqG52jiqDJ12waP11Pa1lGoiyUkIEuMLBP0oeK/C89esbXrxsky5we7dfd8U58nm0SgAWpVw==",
      "license": "MIT"
    },
    "node_modules/@rolldown/pluginutils": {
      "version": "1.0.0-beta.53",
      "resolved": "https://registry.npmjs.org/@rolldown/pluginutils/-/pluginutils-1.0.0-beta.53.tgz",
      "integrity": "sha512-vENRlFU4YbrwVqNDZ7fLvy+JR1CRkyr01jhSiDpE1u6py3OMzQfztQU2jxykW3ALNxO4kSlqIDeYyD0Y9RcQeQ==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/@rollup/rollup-android-arm-eabi": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-android-arm-eabi/-/rollup-android-arm-eabi-4.55.1.tgz",
      "integrity": "sha512-9R0DM/ykwfGIlNu6+2U09ga0WXeZ9MRC2Ter8jnz8415VbuIykVuc6bhdrbORFZANDmTDvq26mJrEVTl8TdnDg==",
      "cpu": [
        "arm"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "android"
      ]
    },
    "node_modules/@rollup/rollup-android-arm64": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-android-arm64/-/rollup-android-arm64-4.55.1.tgz",
      "integrity": "sha512-eFZCb1YUqhTysgW3sj/55du5cG57S7UTNtdMjCW7LwVcj3dTTcowCsC8p7uBdzKsZYa8J7IDE8lhMI+HX1vQvg==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "android"
      ]
    },
    "node_modules/@rollup/rollup-darwin-arm64": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-darwin-arm64/-/rollup-darwin-arm64-4.55.1.tgz",
      "integrity": "sha512-p3grE2PHcQm2e8PSGZdzIhCKbMCw/xi9XvMPErPhwO17vxtvCN5FEA2mSLgmKlCjHGMQTP6phuQTYWUnKewwGg==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "darwin"
      ]
    },
    "node_modules/@rollup/rollup-darwin-x64": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-darwin-x64/-/rollup-darwin-x64-4.55.1.tgz",
      "integrity": "sha512-rDUjG25C9qoTm+e02Esi+aqTKSBYwVTaoS1wxcN47/Luqef57Vgp96xNANwt5npq9GDxsH7kXxNkJVEsWEOEaQ==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "darwin"
      ]
    },
    "node_modules/@rollup/rollup-freebsd-arm64": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-freebsd-arm64/-/rollup-freebsd-arm64-4.55.1.tgz",
      "integrity": "sha512-+JiU7Jbp5cdxekIgdte0jfcu5oqw4GCKr6i3PJTlXTCU5H5Fvtkpbs4XJHRmWNXF+hKmn4v7ogI5OQPaupJgOg==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "freebsd"
      ]
    },
    "node_modules/@rollup/rollup-freebsd-x64": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-freebsd-x64/-/rollup-freebsd-x64-4.55.1.tgz",
      "integrity": "sha512-V5xC1tOVWtLLmr3YUk2f6EJK4qksksOYiz/TCsFHu/R+woubcLWdC9nZQmwjOAbmExBIVKsm1/wKmEy4z4u4Bw==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "freebsd"
      ]
    },
    "node_modules/@rollup/rollup-linux-arm-gnueabihf": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-arm-gnueabihf/-/rollup-linux-arm-gnueabihf-4.55.1.tgz",
      "integrity": "sha512-Rn3n+FUk2J5VWx+ywrG/HGPTD9jXNbicRtTM11e/uorplArnXZYsVifnPPqNNP5BsO3roI4n8332ukpY/zN7rQ==",
      "cpu": [
        "arm"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-arm-musleabihf": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-arm-musleabihf/-/rollup-linux-arm-musleabihf-4.55.1.tgz",
      "integrity": "sha512-grPNWydeKtc1aEdrJDWk4opD7nFtQbMmV7769hiAaYyUKCT1faPRm2av8CX1YJsZ4TLAZcg9gTR1KvEzoLjXkg==",
      "cpu": [
        "arm"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-arm64-gnu": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-arm64-gnu/-/rollup-linux-arm64-gnu-4.55.1.tgz",
      "integrity": "sha512-a59mwd1k6x8tXKcUxSyISiquLwB5pX+fJW9TkWU46lCqD/GRDe9uDN31jrMmVP3feI3mhAdvcCClhV8V5MhJFQ==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-arm64-musl": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-arm64-musl/-/rollup-linux-arm64-musl-4.55.1.tgz",
      "integrity": "sha512-puS1MEgWX5GsHSoiAsF0TYrpomdvkaXm0CofIMG5uVkP6IBV+ZO9xhC5YEN49nsgYo1DuuMquF9+7EDBVYu4uA==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-loong64-gnu": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-loong64-gnu/-/rollup-linux-loong64-gnu-4.55.1.tgz",
      "integrity": "sha512-r3Wv40in+lTsULSb6nnoudVbARdOwb2u5fpeoOAZjFLznp6tDU8kd+GTHmJoqZ9lt6/Sys33KdIHUaQihFcu7g==",
      "cpu": [
        "loong64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-loong64-musl": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-loong64-musl/-/rollup-linux-loong64-musl-4.55.1.tgz",
      "integrity": "sha512-MR8c0+UxAlB22Fq4R+aQSPBayvYa3+9DrwG/i1TKQXFYEaoW3B5b/rkSRIypcZDdWjWnpcvxbNaAJDcSbJU3Lw==",
      "cpu": [
        "loong64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-ppc64-gnu": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-ppc64-gnu/-/rollup-linux-ppc64-gnu-4.55.1.tgz",
      "integrity": "sha512-3KhoECe1BRlSYpMTeVrD4sh2Pw2xgt4jzNSZIIPLFEsnQn9gAnZagW9+VqDqAHgm1Xc77LzJOo2LdigS5qZ+gw==",
      "cpu": [
        "ppc64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-ppc64-musl": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-ppc64-musl/-/rollup-linux-ppc64-musl-4.55.1.tgz",
      "integrity": "sha512-ziR1OuZx0vdYZZ30vueNZTg73alF59DicYrPViG0NEgDVN8/Jl87zkAPu4u6VjZST2llgEUjaiNl9JM6HH1Vdw==",
      "cpu": [
        "ppc64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-riscv64-gnu": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-riscv64-gnu/-/rollup-linux-riscv64-gnu-4.55.1.tgz",
      "integrity": "sha512-uW0Y12ih2XJRERZ4jAfKamTyIHVMPQnTZcQjme2HMVDAHY4amf5u414OqNYC+x+LzRdRcnIG1YodLrrtA8xsxw==",
      "cpu": [
        "riscv64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-riscv64-musl": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-riscv64-musl/-/rollup-linux-riscv64-musl-4.55.1.tgz",
      "integrity": "sha512-u9yZ0jUkOED1BFrqu3BwMQoixvGHGZ+JhJNkNKY/hyoEgOwlqKb62qu+7UjbPSHYjiVy8kKJHvXKv5coH4wDeg==",
      "cpu": [
        "riscv64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-s390x-gnu": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-s390x-gnu/-/rollup-linux-s390x-gnu-4.55.1.tgz",
      "integrity": "sha512-/0PenBCmqM4ZUd0190j7J0UsQ/1nsi735iPRakO8iPciE7BQ495Y6msPzaOmvx0/pn+eJVVlZrNrSh4WSYLxNg==",
      "cpu": [
        "s390x"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-x64-gnu": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-x64-gnu/-/rollup-linux-x64-gnu-4.55.1.tgz",
      "integrity": "sha512-a8G4wiQxQG2BAvo+gU6XrReRRqj+pLS2NGXKm8io19goR+K8lw269eTrPkSdDTALwMmJp4th2Uh0D8J9bEV1vg==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-linux-x64-musl": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-linux-x64-musl/-/rollup-linux-x64-musl-4.55.1.tgz",
      "integrity": "sha512-bD+zjpFrMpP/hqkfEcnjXWHMw5BIghGisOKPj+2NaNDuVT+8Ds4mPf3XcPHuat1tz89WRL+1wbcxKY3WSbiT7w==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "linux"
      ]
    },
    "node_modules/@rollup/rollup-openbsd-x64": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-openbsd-x64/-/rollup-openbsd-x64-4.55.1.tgz",
      "integrity": "sha512-eLXw0dOiqE4QmvikfQ6yjgkg/xDM+MdU9YJuP4ySTibXU0oAvnEWXt7UDJmD4UkYialMfOGFPJnIHSe/kdzPxg==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "openbsd"
      ]
    },
    "node_modules/@rollup/rollup-openharmony-arm64": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-openharmony-arm64/-/rollup-openharmony-arm64-4.55.1.tgz",
      "integrity": "sha512-xzm44KgEP11te3S2HCSyYf5zIzWmx3n8HDCc7EE59+lTcswEWNpvMLfd9uJvVX8LCg9QWG67Xt75AuHn4vgsXw==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "openharmony"
      ]
    },
    "node_modules/@rollup/rollup-win32-arm64-msvc": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-win32-arm64-msvc/-/rollup-win32-arm64-msvc-4.55.1.tgz",
      "integrity": "sha512-yR6Bl3tMC/gBok5cz/Qi0xYnVbIxGx5Fcf/ca0eB6/6JwOY+SRUcJfI0OpeTpPls7f194as62thCt/2BjxYN8g==",
      "cpu": [
        "arm64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "win32"
      ]
    },
    "node_modules/@rollup/rollup-win32-ia32-msvc": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-win32-ia32-msvc/-/rollup-win32-ia32-msvc-4.55.1.tgz",
      "integrity": "sha512-3fZBidchE0eY0oFZBnekYCfg+5wAB0mbpCBuofh5mZuzIU/4jIVkbESmd2dOsFNS78b53CYv3OAtwqkZZmU5nA==",
      "cpu": [
        "ia32"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "win32"
      ]
    },
    "node_modules/@rollup/rollup-win32-x64-gnu": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-win32-x64-gnu/-/rollup-win32-x64-gnu-4.55.1.tgz",
      "integrity": "sha512-xGGY5pXj69IxKb4yv/POoocPy/qmEGhimy/FoTpTSVju3FYXUQQMFCaZZXJVidsmGxRioZAwpThl/4zX41gRKg==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "win32"
      ]
    },
    "node_modules/@rollup/rollup-win32-x64-msvc": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/@rollup/rollup-win32-x64-msvc/-/rollup-win32-x64-msvc-4.55.1.tgz",
      "integrity": "sha512-SPEpaL6DX4rmcXtnhdrQYgzQ5W2uW3SCJch88lB2zImhJRhIIK44fkUrgIV/Q8yUNfw5oyZ5vkeQsZLhCb06lw==",
      "cpu": [
        "x64"
      ],
      "dev": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "win32"
      ]
    },
    "node_modules/@standard-schema/utils": {
      "version": "0.3.0",
      "resolved": "https://registry.npmjs.org/@standard-schema/utils/-/utils-0.3.0.tgz",
      "integrity": "sha512-e7Mew686owMaPJVNNLs55PUvgz371nKgwsc4vxE49zsODpJEnxgxRo2y/OKrqueavXgZNMDVj3DdHFlaSAeU8g==",
      "license": "MIT"
    },
    "node_modules/@tweenjs/tween.js": {
      "version": "23.1.3",
      "resolved": "https://registry.npmmirror.com/@tweenjs/tween.js/-/tween.js-23.1.3.tgz",
      "integrity": "sha512-vJmvvwFxYuGnF2axRtPYocag6Clbb5YS7kLL+SO/TeVFzHqDIWrNKYtcsPMibjDx9O+bu+psAy9NKfWklassUA==",
      "license": "MIT"
    },
    "node_modules/@types/babel__core": {
      "version": "7.20.5",
      "resolved": "https://registry.npmjs.org/@types/babel__core/-/babel__core-7.20.5.tgz",
      "integrity": "sha512-qoQprZvz5wQFJwMDqeseRXWv3rqMvhgpbXFfVyWhbx9X47POIA6i/+dXefEmZKoAgOaTdaIgNSMqMIU61yRyzA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/parser": "^7.20.7",
        "@babel/types": "^7.20.7",
        "@types/babel__generator": "*",
        "@types/babel__template": "*",
        "@types/babel__traverse": "*"
      }
    },
    "node_modules/@types/babel__generator": {
      "version": "7.27.0",
      "resolved": "https://registry.npmjs.org/@types/babel__generator/-/babel__generator-7.27.0.tgz",
      "integrity": "sha512-ufFd2Xi92OAVPYsy+P4n7/U7e68fex0+Ee8gSG9KX7eo084CWiQ4sdxktvdl0bOPupXtVJPY19zk6EwWqUQ8lg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/types": "^7.0.0"
      }
    },
    "node_modules/@types/babel__template": {
      "version": "7.4.4",
      "resolved": "https://registry.npmjs.org/@types/babel__template/-/babel__template-7.4.4.tgz",
      "integrity": "sha512-h/NUaSyG5EyxBIp8YRxo4RMe2/qQgvyowRwVMzhYhBCONbW8PUsg4lkFMrhgZhUe5z3L3MiLDuvyJ/CaPa2A8A==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/parser": "^7.1.0",
        "@babel/types": "^7.0.0"
      }
    },
    "node_modules/@types/babel__traverse": {
      "version": "7.28.0",
      "resolved": "https://registry.npmjs.org/@types/babel__traverse/-/babel__traverse-7.28.0.tgz",
      "integrity": "sha512-8PvcXf70gTDZBgt9ptxJ8elBeBjcLOAcOtoO/mPJjtji1+CdGbHgm77om1GrsPxsiE+uXIpNSK64UYaIwQXd4Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/types": "^7.28.2"
      }
    },
    "node_modules/@types/d3-array": {
      "version": "3.2.2",
      "resolved": "https://registry.npmjs.org/@types/d3-array/-/d3-array-3.2.2.tgz",
      "integrity": "sha512-hOLWVbm7uRza0BYXpIIW5pxfrKe0W+D5lrFiAEYR+pb6w3N2SwSMaJbXdUfSEv+dT4MfHBLtn5js0LAWaO6otw==",
      "license": "MIT"
    },
    "node_modules/@types/d3-color": {
      "version": "3.1.3",
      "resolved": "https://registry.npmjs.org/@types/d3-color/-/d3-color-3.1.3.tgz",
      "integrity": "sha512-iO90scth9WAbmgv7ogoq57O9YpKmFBbmoEoCHDB2xMBY0+/KVrqAaCDyCE16dUspeOvIxFFRI+0sEtqDqy2b4A==",
      "license": "MIT"
    },
    "node_modules/@types/d3-ease": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/@types/d3-ease/-/d3-ease-3.0.2.tgz",
      "integrity": "sha512-NcV1JjO5oDzoK26oMzbILE6HW7uVXOHLQvHshBUW4UMdZGfiY6v5BeQwh9a9tCzv+CeefZQHJt5SRgK154RtiA==",
      "license": "MIT"
    },
    "node_modules/@types/d3-interpolate": {
      "version": "3.0.4",
      "resolved": "https://registry.npmjs.org/@types/d3-interpolate/-/d3-interpolate-3.0.4.tgz",
      "integrity": "sha512-mgLPETlrpVV1YRJIglr4Ez47g7Yxjl1lj7YKsiMCb27VJH9W8NVM6Bb9d8kkpG/uAQS5AmbA48q2IAolKKo1MA==",
      "license": "MIT",
      "dependencies": {
        "@types/d3-color": "*"
      }
    },
    "node_modules/@types/d3-path": {
      "version": "3.1.1",
      "resolved": "https://registry.npmjs.org/@types/d3-path/-/d3-path-3.1.1.tgz",
      "integrity": "sha512-VMZBYyQvbGmWyWVea0EHs/BwLgxc+MKi1zLDCONksozI4YJMcTt8ZEuIR4Sb1MMTE8MMW49v0IwI5+b7RmfWlg==",
      "license": "MIT"
    },
    "node_modules/@types/d3-scale": {
      "version": "4.0.9",
      "resolved": "https://registry.npmjs.org/@types/d3-scale/-/d3-scale-4.0.9.tgz",
      "integrity": "sha512-dLmtwB8zkAeO/juAMfnV+sItKjlsw2lKdZVVy6LRr0cBmegxSABiLEpGVmSJJ8O08i4+sGR6qQtb6WtuwJdvVw==",
      "license": "MIT",
      "dependencies": {
        "@types/d3-time": "*"
      }
    },
    "node_modules/@types/d3-shape": {
      "version": "3.1.7",
      "resolved": "https://registry.npmjs.org/@types/d3-shape/-/d3-shape-3.1.7.tgz",
      "integrity": "sha512-VLvUQ33C+3J+8p+Daf+nYSOsjB4GXp19/S/aGo60m9h1v6XaxjiT82lKVWJCfzhtuZ3yD7i/TPeC/fuKLLOSmg==",
      "license": "MIT",
      "dependencies": {
        "@types/d3-path": "*"
      }
    },
    "node_modules/@types/d3-time": {
      "version": "3.0.4",
      "resolved": "https://registry.npmjs.org/@types/d3-time/-/d3-time-3.0.4.tgz",
      "integrity": "sha512-yuzZug1nkAAaBlBBikKZTgzCeA+k1uy4ZFwWANOfKw5z5LRhV0gNA7gNkKm7HoK+HRN0wX3EkxGk0fpbWhmB7g==",
      "license": "MIT"
    },
    "node_modules/@types/d3-timer": {
      "version": "3.0.2",
      "resolved": "https://registry.npmjs.org/@types/d3-timer/-/d3-timer-3.0.2.tgz",
      "integrity": "sha512-Ps3T8E8dZDam6fUyNiMkekK3XUsaUEik+idO9/YjPtfj2qruF8tFBXS7XhtE4iIXBLxhmLjP3SXpLhVf21I9Lw==",
      "license": "MIT"
    },
    "node_modules/@types/estree": {
      "version": "1.0.8",
      "resolved": "https://registry.npmjs.org/@types/estree/-/estree-1.0.8.tgz",
      "integrity": "sha512-dWHzHa2WqEXI/O1E9OjrocMTKJl2mSrEolh1Iomrv6U+JuNwaHXsXx9bLu5gG7BUWFIN0skIQJQ/L1rIex4X6w==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/@types/json-schema": {
      "version": "7.0.15",
      "resolved": "https://registry.npmjs.org/@types/json-schema/-/json-schema-7.0.15.tgz",
      "integrity": "sha512-5+fP8P8MFNC+AyZCDxrB2pkZFPGzqQWUzpSeuuVLvm8VMcorNYavBqoFcxK8bQz4Qsbn4oUEEem4wDLfcysGHA==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/@types/node": {
      "version": "24.10.4",
      "resolved": "https://registry.npmjs.org/@types/node/-/node-24.10.4.tgz",
      "integrity": "sha512-vnDVpYPMzs4wunl27jHrfmwojOGKya0xyM3sH+UE5iv5uPS6vX7UIoh6m+vQc5LGBq52HBKPIn/zcSZVzeDEZg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "undici-types": "~7.16.0"
      }
    },
    "node_modules/@types/react": {
      "version": "19.2.7",
      "resolved": "https://registry.npmjs.org/@types/react/-/react-19.2.7.tgz",
      "integrity": "sha512-MWtvHrGZLFttgeEj28VXHxpmwYbor/ATPYbBfSFZEIRK0ecCFLl2Qo55z52Hss+UV9CRN7trSeq1zbgx7YDWWg==",
      "devOptional": true,
      "license": "MIT",
      "dependencies": {
        "csstype": "^3.2.2"
      }
    },
    "node_modules/@types/react-dom": {
      "version": "19.2.3",
      "resolved": "https://registry.npmjs.org/@types/react-dom/-/react-dom-19.2.3.tgz",
      "integrity": "sha512-jp2L/eY6fn+KgVVQAOqYItbF0VY/YApe5Mz2F0aykSO8gx31bYCZyvSeYxCHKvzHG5eZjc+zyaS5BrBWya2+kQ==",
      "devOptional": true,
      "license": "MIT",
      "peerDependencies": {
        "@types/react": "^19.2.0"
      }
    },
    "node_modules/@types/stats.js": {
      "version": "0.17.4",
      "resolved": "https://registry.npmmirror.com/@types/stats.js/-/stats.js-0.17.4.tgz",
      "integrity": "sha512-jIBvWWShCvlBqBNIZt0KAshWpvSjhkwkEu4ZUcASoAvhmrgAUI2t1dXrjSL4xXVLB4FznPrIsX3nKXFl/Dt4vA==",
      "license": "MIT"
    },
    "node_modules/@types/three": {
      "version": "0.184.1",
      "resolved": "https://registry.npmmirror.com/@types/three/-/three-0.184.1.tgz",
      "integrity": "sha512-6q4VdiqVsrTRqmk62/BnlcAvIrnDM0zf2ZDVKI5kZiniWrSaOHaQzmbp+BNzoggc/8tgW412pL//wZIxu2PPTA==",
      "license": "MIT",
      "dependencies": {
        "@dimforge/rapier3d-compat": "~0.12.0",
        "@tweenjs/tween.js": "~23.1.3",
        "@types/stats.js": "*",
        "@types/webxr": ">=0.5.17",
        "fflate": "~0.8.2",
        "meshoptimizer": "~1.1.1"
      }
    },
    "node_modules/@types/webxr": {
      "version": "0.5.24",
      "resolved": "https://registry.npmmirror.com/@types/webxr/-/webxr-0.5.24.tgz",
      "integrity": "sha512-h8fgEd/DpoS9CBrjEQXR+dIDraopAEfu4wYVNY2tEPwk60stPWhvZMf4Foo5FakuQ7HFZoa8WceaWFervK2Ovg==",
      "license": "MIT"
    },
    "node_modules/@typescript-eslint/eslint-plugin": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/eslint-plugin/-/eslint-plugin-8.52.0.tgz",
      "integrity": "sha512-okqtOgqu2qmZJ5iN4TWlgfF171dZmx2FzdOv2K/ixL2LZWDStL8+JgQerI2sa8eAEfoydG9+0V96m7V+P8yE1Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@eslint-community/regexpp": "^4.12.2",
        "@typescript-eslint/scope-manager": "8.52.0",
        "@typescript-eslint/type-utils": "8.52.0",
        "@typescript-eslint/utils": "8.52.0",
        "@typescript-eslint/visitor-keys": "8.52.0",
        "ignore": "^7.0.5",
        "natural-compare": "^1.4.0",
        "ts-api-utils": "^2.4.0"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      },
      "peerDependencies": {
        "@typescript-eslint/parser": "^8.52.0",
        "eslint": "^8.57.0 || ^9.0.0",
        "typescript": ">=4.8.4 <6.0.0"
      }
    },
    "node_modules/@typescript-eslint/eslint-plugin/node_modules/ignore": {
      "version": "7.0.5",
      "resolved": "https://registry.npmjs.org/ignore/-/ignore-7.0.5.tgz",
      "integrity": "sha512-Hs59xBNfUIunMFgWAbGX5cq6893IbWg4KnrjbYwX3tx0ztorVgTDA6B2sxf8ejHJ4wz8BqGUMYlnzNBer5NvGg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 4"
      }
    },
    "node_modules/@typescript-eslint/parser": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/parser/-/parser-8.52.0.tgz",
      "integrity": "sha512-iIACsx8pxRnguSYhHiMn2PvhvfpopO9FXHyn1mG5txZIsAaB6F0KwbFnUQN3KCiG3Jcuad/Cao2FAs1Wp7vAyg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@typescript-eslint/scope-manager": "8.52.0",
        "@typescript-eslint/types": "8.52.0",
        "@typescript-eslint/typescript-estree": "8.52.0",
        "@typescript-eslint/visitor-keys": "8.52.0",
        "debug": "^4.4.3"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      },
      "peerDependencies": {
        "eslint": "^8.57.0 || ^9.0.0",
        "typescript": ">=4.8.4 <6.0.0"
      }
    },
    "node_modules/@typescript-eslint/project-service": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/project-service/-/project-service-8.52.0.tgz",
      "integrity": "sha512-xD0MfdSdEmeFa3OmVqonHi+Cciab96ls1UhIF/qX/O/gPu5KXD0bY9lu33jj04fjzrXHcuvjBcBC+D3SNSadaw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@typescript-eslint/tsconfig-utils": "^8.52.0",
        "@typescript-eslint/types": "^8.52.0",
        "debug": "^4.4.3"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      },
      "peerDependencies": {
        "typescript": ">=4.8.4 <6.0.0"
      }
    },
    "node_modules/@typescript-eslint/scope-manager": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/scope-manager/-/scope-manager-8.52.0.tgz",
      "integrity": "sha512-ixxqmmCcc1Nf8S0mS0TkJ/3LKcC8mruYJPOU6Ia2F/zUUR4pApW7LzrpU3JmtePbRUTes9bEqRc1Gg4iyRnDzA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@typescript-eslint/types": "8.52.0",
        "@typescript-eslint/visitor-keys": "8.52.0"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      }
    },
    "node_modules/@typescript-eslint/tsconfig-utils": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/tsconfig-utils/-/tsconfig-utils-8.52.0.tgz",
      "integrity": "sha512-jl+8fzr/SdzdxWJznq5nvoI7qn2tNYV/ZBAEcaFMVXf+K6jmXvAFrgo/+5rxgnL152f//pDEAYAhhBAZGrVfwg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      },
      "peerDependencies": {
        "typescript": ">=4.8.4 <6.0.0"
      }
    },
    "node_modules/@typescript-eslint/type-utils": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/type-utils/-/type-utils-8.52.0.tgz",
      "integrity": "sha512-JD3wKBRWglYRQkAtsyGz1AewDu3mTc7NtRjR/ceTyGoPqmdS5oCdx/oZMWD5Zuqmo6/MpsYs0wp6axNt88/2EQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@typescript-eslint/types": "8.52.0",
        "@typescript-eslint/typescript-estree": "8.52.0",
        "@typescript-eslint/utils": "8.52.0",
        "debug": "^4.4.3",
        "ts-api-utils": "^2.4.0"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      },
      "peerDependencies": {
        "eslint": "^8.57.0 || ^9.0.0",
        "typescript": ">=4.8.4 <6.0.0"
      }
    },
    "node_modules/@typescript-eslint/types": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/types/-/types-8.52.0.tgz",
      "integrity": "sha512-LWQV1V4q9V4cT4H5JCIx3481iIFxH1UkVk+ZkGGAV1ZGcjGI9IoFOfg3O6ywz8QqCDEp7Inlg6kovMofsNRaGg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      }
    },
    "node_modules/@typescript-eslint/typescript-estree": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/typescript-estree/-/typescript-estree-8.52.0.tgz",
      "integrity": "sha512-XP3LClsCc0FsTK5/frGjolyADTh3QmsLp6nKd476xNI9CsSsLnmn4f0jrzNoAulmxlmNIpeXuHYeEQv61Q6qeQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@typescript-eslint/project-service": "8.52.0",
        "@typescript-eslint/tsconfig-utils": "8.52.0",
        "@typescript-eslint/types": "8.52.0",
        "@typescript-eslint/visitor-keys": "8.52.0",
        "debug": "^4.4.3",
        "minimatch": "^9.0.5",
        "semver": "^7.7.3",
        "tinyglobby": "^0.2.15",
        "ts-api-utils": "^2.4.0"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      },
      "peerDependencies": {
        "typescript": ">=4.8.4 <6.0.0"
      }
    },
    "node_modules/@typescript-eslint/typescript-estree/node_modules/brace-expansion": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/brace-expansion/-/brace-expansion-2.0.2.tgz",
      "integrity": "sha512-Jt0vHyM+jmUBqojB7E1NIYadt0vI0Qxjxd2TErW94wDz+E2LAm5vKMXXwg6ZZBTHPuUlDgQHKXvjGBdfcF1ZDQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "balanced-match": "^1.0.0"
      }
    },
    "node_modules/@typescript-eslint/typescript-estree/node_modules/minimatch": {
      "version": "9.0.5",
      "resolved": "https://registry.npmjs.org/minimatch/-/minimatch-9.0.5.tgz",
      "integrity": "sha512-G6T0ZX48xgozx7587koeX9Ys2NYy6Gmv//P89sEte9V9whIapMNF4idKxnW2QtCcLiTWlb/wfCabAtAFWhhBow==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "brace-expansion": "^2.0.1"
      },
      "engines": {
        "node": ">=16 || 14 >=14.17"
      },
      "funding": {
        "url": "https://github.com/sponsors/isaacs"
      }
    },
    "node_modules/@typescript-eslint/typescript-estree/node_modules/semver": {
      "version": "7.7.3",
      "resolved": "https://registry.npmjs.org/semver/-/semver-7.7.3.tgz",
      "integrity": "sha512-SdsKMrI9TdgjdweUSR9MweHA4EJ8YxHn8DFaDisvhVlUOe4BF1tLD7GAj0lIqWVl+dPb/rExr0Btby5loQm20Q==",
      "dev": true,
      "license": "ISC",
      "bin": {
        "semver": "bin/semver.js"
      },
      "engines": {
        "node": ">=10"
      }
    },
    "node_modules/@typescript-eslint/utils": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/utils/-/utils-8.52.0.tgz",
      "integrity": "sha512-wYndVMWkweqHpEpwPhwqE2lnD2DxC6WVLupU/DOt/0/v+/+iQbbzO3jOHjmBMnhu0DgLULvOaU4h4pwHYi2oRQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@eslint-community/eslint-utils": "^4.9.1",
        "@typescript-eslint/scope-manager": "8.52.0",
        "@typescript-eslint/types": "8.52.0",
        "@typescript-eslint/typescript-estree": "8.52.0"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      },
      "peerDependencies": {
        "eslint": "^8.57.0 || ^9.0.0",
        "typescript": ">=4.8.4 <6.0.0"
      }
    },
    "node_modules/@typescript-eslint/visitor-keys": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/@typescript-eslint/visitor-keys/-/visitor-keys-8.52.0.tgz",
      "integrity": "sha512-ink3/Zofus34nmBsPjow63FP5M7IGff0RKAgqR6+CFpdk22M7aLwC9gOcLGYqr7MczLPzZVERW9hRog3O4n1sQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@typescript-eslint/types": "8.52.0",
        "eslint-visitor-keys": "^4.2.1"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      }
    },
    "node_modules/@vitejs/plugin-react": {
      "version": "5.1.2",
      "resolved": "https://registry.npmjs.org/@vitejs/plugin-react/-/plugin-react-5.1.2.tgz",
      "integrity": "sha512-EcA07pHJouywpzsoTUqNh5NwGayl2PPVEJKUSinGGSxFGYn+shYbqMGBg6FXDqgXum9Ou/ecb+411ssw8HImJQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/core": "^7.28.5",
        "@babel/plugin-transform-react-jsx-self": "^7.27.1",
        "@babel/plugin-transform-react-jsx-source": "^7.27.1",
        "@rolldown/pluginutils": "1.0.0-beta.53",
        "@types/babel__core": "^7.20.5",
        "react-refresh": "^0.18.0"
      },
      "engines": {
        "node": "^20.19.0 || >=22.12.0"
      },
      "peerDependencies": {
        "vite": "^4.2.0 || ^5.0.0 || ^6.0.0 || ^7.0.0"
      }
    },
    "node_modules/acorn": {
      "version": "8.15.0",
      "resolved": "https://registry.npmjs.org/acorn/-/acorn-8.15.0.tgz",
      "integrity": "sha512-NZyJarBfL7nWwIq+FDL6Zp/yHEhePMNnnJ0y3qfieCrmNvYct8uvtiV41UvlSe6apAfk0fY1FbWx+NwfmpvtTg==",
      "dev": true,
      "license": "MIT",
      "bin": {
        "acorn": "bin/acorn"
      },
      "engines": {
        "node": ">=0.4.0"
      }
    },
    "node_modules/acorn-jsx": {
      "version": "5.3.2",
      "resolved": "https://registry.npmjs.org/acorn-jsx/-/acorn-jsx-5.3.2.tgz",
      "integrity": "sha512-rq9s+JNhf0IChjtDXxllJ7g41oZk5SlXtp0LHwyA5cejwn7vKmKp4pPri6YEePv2PU65sAsegbXtIinmDFDXgQ==",
      "dev": true,
      "license": "MIT",
      "peerDependencies": {
        "acorn": "^6.0.0 || ^7.0.0 || ^8.0.0"
      }
    },
    "node_modules/ajv": {
      "version": "6.12.6",
      "resolved": "https://registry.npmjs.org/ajv/-/ajv-6.12.6.tgz",
      "integrity": "sha512-j3fVLgvTo527anyYyJOGTYJbG+vnnQYvE0m5mmkc1TK+nxAppkCLMIL0aZ4dblVCNoGShhm+kzE4ZUykBoMg4g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "fast-deep-equal": "^3.1.1",
        "fast-json-stable-stringify": "^2.0.0",
        "json-schema-traverse": "^0.4.1",
        "uri-js": "^4.2.2"
      },
      "funding": {
        "type": "github",
        "url": "https://github.com/sponsors/epoberezkin"
      }
    },
    "node_modules/ansi-styles": {
      "version": "4.3.0",
      "resolved": "https://registry.npmjs.org/ansi-styles/-/ansi-styles-4.3.0.tgz",
      "integrity": "sha512-zbB9rCJAT1rbjiVDb2hqKFHNYLxgtk8NURxZ3IZwD3F6NtxbXZQCnnSi1Lkx+IDohdPlFp222wVALIheZJQSEg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "color-convert": "^2.0.1"
      },
      "engines": {
        "node": ">=8"
      },
      "funding": {
        "url": "https://github.com/chalk/ansi-styles?sponsor=1"
      }
    },
    "node_modules/any-promise": {
      "version": "1.3.0",
      "resolved": "https://registry.npmjs.org/any-promise/-/any-promise-1.3.0.tgz",
      "integrity": "sha512-7UvmKalWRt1wgjL1RrGxoSJW/0QZFIegpeGvZG9kjp8vrRu55XTHbwnqq2GpXm9uLbcuhxm3IqX9OB4MZR1b2A==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/anymatch": {
      "version": "3.1.3",
      "resolved": "https://registry.npmjs.org/anymatch/-/anymatch-3.1.3.tgz",
      "integrity": "sha512-KMReFUr0B4t+D+OBkjR3KYqvocp2XaSzO55UcB6mgQMd3KbcE+mWTyvVV7D/zsdEbNnV6acZUutkiHQXvTr1Rw==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "normalize-path": "^3.0.0",
        "picomatch": "^2.0.4"
      },
      "engines": {
        "node": ">= 8"
      }
    },
    "node_modules/anymatch/node_modules/picomatch": {
      "version": "2.3.1",
      "resolved": "https://registry.npmjs.org/picomatch/-/picomatch-2.3.1.tgz",
      "integrity": "sha512-JU3teHTNjmE2VCGFzuY8EXzCDVwEqB2a8fsIvwaStHhAWJEeVd1o1QD80CU6+ZdEXXSLbSsuLwJjkCBWqRQUVA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8.6"
      },
      "funding": {
        "url": "https://github.com/sponsors/jonschlinkert"
      }
    },
    "node_modules/arg": {
      "version": "5.0.2",
      "resolved": "https://registry.npmjs.org/arg/-/arg-5.0.2.tgz",
      "integrity": "sha512-PYjyFOLKQ9y57JvQ6QLo8dAgNqswh8M1RMJYdQduT6xbWSgK36P/Z/v+p888pM69jMMfS8Xd8F6I1kQ/I9HUGg==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/argparse": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/argparse/-/argparse-2.0.1.tgz",
      "integrity": "sha512-8+9WqebbFzpX9OR+Wa6O29asIogeRMzcGtAINdpMHHyAg10f05aSFVBbcEqGf/PXw1EjAZ+q2/bEBg3DvurK3Q==",
      "dev": true,
      "license": "Python-2.0"
    },
    "node_modules/aria-hidden": {
      "version": "1.2.6",
      "resolved": "https://registry.npmjs.org/aria-hidden/-/aria-hidden-1.2.6.tgz",
      "integrity": "sha512-ik3ZgC9dY/lYVVM++OISsaYDeg1tb0VtP5uL3ouh1koGOaUMDPpbFIei4JkFimWUFPn90sbMNMXQAIVOlnYKJA==",
      "license": "MIT",
      "dependencies": {
        "tslib": "^2.0.0"
      },
      "engines": {
        "node": ">=10"
      }
    },
    "node_modules/autoprefixer": {
      "version": "10.4.23",
      "resolved": "https://registry.npmjs.org/autoprefixer/-/autoprefixer-10.4.23.tgz",
      "integrity": "sha512-YYTXSFulfwytnjAPlw8QHncHJmlvFKtczb8InXaAx9Q0LbfDnfEYDE55omerIJKihhmU61Ft+cAOSzQVaBUmeA==",
      "dev": true,
      "funding": [
        {
          "type": "opencollective",
          "url": "https://opencollective.com/postcss/"
        },
        {
          "type": "tidelift",
          "url": "https://tidelift.com/funding/github/npm/autoprefixer"
        },
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "MIT",
      "dependencies": {
        "browserslist": "^4.28.1",
        "caniuse-lite": "^1.0.30001760",
        "fraction.js": "^5.3.4",
        "picocolors": "^1.1.1",
        "postcss-value-parser": "^4.2.0"
      },
      "bin": {
        "autoprefixer": "bin/autoprefixer"
      },
      "engines": {
        "node": "^10 || ^12 || >=14"
      },
      "peerDependencies": {
        "postcss": "^8.1.0"
      }
    },
    "node_modules/babel-plugin-polyfill-corejs2": {
      "version": "0.4.17",
      "resolved": "https://registry.npmmirror.com/babel-plugin-polyfill-corejs2/-/babel-plugin-polyfill-corejs2-0.4.17.tgz",
      "integrity": "sha512-aTyf30K/rqAsNwN76zYrdtx8obu0E4KoUME29B1xj+B3WxgvWkp943vYQ+z8Mv3lw9xHXMHpvSPOBxzAkIa94w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/compat-data": "^7.28.6",
        "@babel/helper-define-polyfill-provider": "^0.6.8",
        "semver": "^6.3.1"
      },
      "peerDependencies": {
        "@babel/core": "^7.4.0 || ^8.0.0-0 <8.0.0"
      }
    },
    "node_modules/babel-plugin-polyfill-corejs3": {
      "version": "0.14.2",
      "resolved": "https://registry.npmmirror.com/babel-plugin-polyfill-corejs3/-/babel-plugin-polyfill-corejs3-0.14.2.tgz",
      "integrity": "sha512-coWpDLJ410R781Npmn/SIBZEsAetR4xVi0SxLMXPaMO4lSf1MwnkGYMtkFxew0Dn8B3/CpbpYxN0JCgg8mn67g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-define-polyfill-provider": "^0.6.8",
        "core-js-compat": "^3.48.0"
      },
      "peerDependencies": {
        "@babel/core": "^7.4.0 || ^8.0.0-0 <8.0.0"
      }
    },
    "node_modules/babel-plugin-polyfill-regenerator": {
      "version": "0.6.8",
      "resolved": "https://registry.npmmirror.com/babel-plugin-polyfill-regenerator/-/babel-plugin-polyfill-regenerator-0.6.8.tgz",
      "integrity": "sha512-M762rNHfSF1EV3SLtnCJXFoQbbIIz0OyRwnCmV0KPC7qosSfCO0QLTSuJX3ayAebubhE6oYBAYPrBA5ljowaZg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/helper-define-polyfill-provider": "^0.6.8"
      },
      "peerDependencies": {
        "@babel/core": "^7.4.0 || ^8.0.0-0 <8.0.0"
      }
    },
    "node_modules/balanced-match": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/balanced-match/-/balanced-match-1.0.2.tgz",
      "integrity": "sha512-3oSeUO0TMV67hN1AmbXsK4yaqU7tjiHlbxRDZOpH0KW9+CeX4bRAaX0Anxt0tx2MrpRpWwQaPwIlISEJhYU5Pw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/baseline-browser-mapping": {
      "version": "2.9.11",
      "resolved": "https://registry.npmjs.org/baseline-browser-mapping/-/baseline-browser-mapping-2.9.11.tgz",
      "integrity": "sha512-Sg0xJUNDU1sJNGdfGWhVHX0kkZ+HWcvmVymJbj6NSgZZmW/8S9Y2HQ5euytnIgakgxN6papOAWiwDo1ctFDcoQ==",
      "dev": true,
      "license": "Apache-2.0",
      "bin": {
        "baseline-browser-mapping": "dist/cli.js"
      }
    },
    "node_modules/binary-extensions": {
      "version": "2.3.0",
      "resolved": "https://registry.npmjs.org/binary-extensions/-/binary-extensions-2.3.0.tgz",
      "integrity": "sha512-Ceh+7ox5qe7LJuLHoY0feh3pHuUDHAcRUeyL2VYghZwfpkNIy/+8Ocg0a3UuSoYzavmylwuLWQOf3hl0jjMMIw==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/brace-expansion": {
      "version": "1.1.12",
      "resolved": "https://registry.npmjs.org/brace-expansion/-/brace-expansion-1.1.12.tgz",
      "integrity": "sha512-9T9UjW3r0UW5c1Q7GTwllptXwhvYmEzFhzMfZ9H7FQWt+uZePjZPjBP/W1ZEyZ1twGWom5/56TF4lPcqjnDHcg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "balanced-match": "^1.0.0",
        "concat-map": "0.0.1"
      }
    },
    "node_modules/braces": {
      "version": "3.0.3",
      "resolved": "https://registry.npmjs.org/braces/-/braces-3.0.3.tgz",
      "integrity": "sha512-yQbXgO/OSZVD2IsiLlro+7Hf6Q18EJrKSEsdoMzKePKXct3gvD8oLcOQdIzGupr5Fj+EDe8gO/lxc1BzfMpxvA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "fill-range": "^7.1.1"
      },
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/browserslist": {
      "version": "4.28.1",
      "resolved": "https://registry.npmjs.org/browserslist/-/browserslist-4.28.1.tgz",
      "integrity": "sha512-ZC5Bd0LgJXgwGqUknZY/vkUQ04r8NXnJZ3yYi4vDmSiZmC/pdSN0NbNRPxZpbtO4uAfDUAFffO8IZoM3Gj8IkA==",
      "dev": true,
      "funding": [
        {
          "type": "opencollective",
          "url": "https://opencollective.com/browserslist"
        },
        {
          "type": "tidelift",
          "url": "https://tidelift.com/funding/github/npm/browserslist"
        },
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "MIT",
      "dependencies": {
        "baseline-browser-mapping": "^2.9.0",
        "caniuse-lite": "^1.0.30001759",
        "electron-to-chromium": "^1.5.263",
        "node-releases": "^2.0.27",
        "update-browserslist-db": "^1.2.0"
      },
      "bin": {
        "browserslist": "cli.js"
      },
      "engines": {
        "node": "^6 || ^7 || ^8 || ^9 || ^10 || ^11 || ^12 || >=13.7"
      }
    },
    "node_modules/callsites": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/callsites/-/callsites-3.1.0.tgz",
      "integrity": "sha512-P8BjAsXvZS+VIDUI11hHCQEv74YT67YUi5JJFNWIqL235sBmjX4+qx9Muvls5ivyNENctx46xQLQ3aTuE7ssaQ==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6"
      }
    },
    "node_modules/camelcase-css": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/camelcase-css/-/camelcase-css-2.0.1.tgz",
      "integrity": "sha512-QOSvevhslijgYwRx6Rv7zKdMF8lbRmx+uQGx2+vDc+KI/eBnsy9kit5aj23AgGu3pa4t9AgwbnXWqS+iOY+2aA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 6"
      }
    },
    "node_modules/caniuse-lite": {
      "version": "1.0.30001762",
      "resolved": "https://registry.npmjs.org/caniuse-lite/-/caniuse-lite-1.0.30001762.tgz",
      "integrity": "sha512-PxZwGNvH7Ak8WX5iXzoK1KPZttBXNPuaOvI2ZYU7NrlM+d9Ov+TUvlLOBNGzVXAntMSMMlJPd+jY6ovrVjSmUw==",
      "dev": true,
      "funding": [
        {
          "type": "opencollective",
          "url": "https://opencollective.com/browserslist"
        },
        {
          "type": "tidelift",
          "url": "https://tidelift.com/funding/github/npm/caniuse-lite"
        },
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "CC-BY-4.0"
    },
    "node_modules/chalk": {
      "version": "4.1.2",
      "resolved": "https://registry.npmjs.org/chalk/-/chalk-4.1.2.tgz",
      "integrity": "sha512-oKnbhFyRIXpUuez8iBMmyEa4nbj4IOQyuhc/wy9kY7/WVPcwIO9VA668Pu8RkO7+0G76SLROeyw9CpQ061i4mA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "ansi-styles": "^4.1.0",
        "supports-color": "^7.1.0"
      },
      "engines": {
        "node": ">=10"
      },
      "funding": {
        "url": "https://github.com/chalk/chalk?sponsor=1"
      }
    },
    "node_modules/chokidar": {
      "version": "3.6.0",
      "resolved": "https://registry.npmjs.org/chokidar/-/chokidar-3.6.0.tgz",
      "integrity": "sha512-7VT13fmjotKpGipCW9JEQAusEPE+Ei8nl6/g4FBAmIm0GOOLMua9NDDo/DWp0ZAxCr3cPq5ZpBqmPAQgDda2Pw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "anymatch": "~3.1.2",
        "braces": "~3.0.2",
        "glob-parent": "~5.1.2",
        "is-binary-path": "~2.1.0",
        "is-glob": "~4.0.1",
        "normalize-path": "~3.0.0",
        "readdirp": "~3.6.0"
      },
      "engines": {
        "node": ">= 8.10.0"
      },
      "funding": {
        "url": "https://paulmillr.com/funding/"
      },
      "optionalDependencies": {
        "fsevents": "~2.3.2"
      }
    },
    "node_modules/chokidar/node_modules/glob-parent": {
      "version": "5.1.2",
      "resolved": "https://registry.npmjs.org/glob-parent/-/glob-parent-5.1.2.tgz",
      "integrity": "sha512-AOIgSQCepiJYwP3ARnGx+5VnTu2HBYdzbGP45eLw1vr3zB3vZLeyed1sC9hnbcOc9/SrMyM5RPQrkGz4aS9Zow==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "is-glob": "^4.0.1"
      },
      "engines": {
        "node": ">= 6"
      }
    },
    "node_modules/class-variance-authority": {
      "version": "0.7.1",
      "resolved": "https://registry.npmjs.org/class-variance-authority/-/class-variance-authority-0.7.1.tgz",
      "integrity": "sha512-Ka+9Trutv7G8M6WT6SeiRWz792K5qEqIGEGzXKhAE6xOWAY6pPH8U+9IY3oCMv6kqTmLsv7Xh/2w2RigkePMsg==",
      "license": "Apache-2.0",
      "dependencies": {
        "clsx": "^2.1.1"
      },
      "funding": {
        "url": "https://polar.sh/cva"
      }
    },
    "node_modules/clsx": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/clsx/-/clsx-2.1.1.tgz",
      "integrity": "sha512-eYm0QWBtUrBWZWG0d386OGAw16Z995PiOVo2B7bjWSbHedGl5e0ZWaq65kOGgUSNesEIDkB9ISbTg/JK9dhCZA==",
      "license": "MIT",
      "engines": {
        "node": ">=6"
      }
    },
    "node_modules/cmdk": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/cmdk/-/cmdk-1.1.1.tgz",
      "integrity": "sha512-Vsv7kFaXm+ptHDMZ7izaRsP70GgrW9NBNGswt9OZaVBLlE0SNpDq8eu/VGXyF9r7M0azK3Wy7OlYXsuyYLFzHg==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-compose-refs": "^1.1.1",
        "@radix-ui/react-dialog": "^1.1.6",
        "@radix-ui/react-id": "^1.1.0",
        "@radix-ui/react-primitive": "^2.0.2"
      },
      "peerDependencies": {
        "react": "^18 || ^19 || ^19.0.0-rc",
        "react-dom": "^18 || ^19 || ^19.0.0-rc"
      }
    },
    "node_modules/color-convert": {
      "version": "2.0.1",
      "resolved": "https://registry.npmjs.org/color-convert/-/color-convert-2.0.1.tgz",
      "integrity": "sha512-RRECPsj7iu/xb5oKYcsFHSppFNnsj/52OVTRKb4zP5onXwVF3zVmmToNcOfGC+CRDpfK/U584fMg38ZHCaElKQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "color-name": "~1.1.4"
      },
      "engines": {
        "node": ">=7.0.0"
      }
    },
    "node_modules/color-name": {
      "version": "1.1.4",
      "resolved": "https://registry.npmjs.org/color-name/-/color-name-1.1.4.tgz",
      "integrity": "sha512-dOy+3AuW3a2wNbZHIuMZpTcgjGuLU/uBL/ubcZF9OXbDo8ff4O8yVp5Bf0efS8uEoYo5q4Fx7dY9OgQGXgAsQA==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/commander": {
      "version": "4.1.1",
      "resolved": "https://registry.npmjs.org/commander/-/commander-4.1.1.tgz",
      "integrity": "sha512-NOKm8xhkzAjzFx8B2v5OAHT+u5pRQc2UCa2Vq9jYL/31o2wi9mxBA7LIFs3sV5VSC49z6pEhfbMULvShKj26WA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 6"
      }
    },
    "node_modules/concat-map": {
      "version": "0.0.1",
      "resolved": "https://registry.npmjs.org/concat-map/-/concat-map-0.0.1.tgz",
      "integrity": "sha512-/Srv4dswyQNBfohGpz9o6Yb3Gz3SrUDqBH5rTuhGR7ahtlbYKnVxw2bCFMRljaA7EXHaXZ8wsHdodFvbkhKmqg==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/convert-source-map": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/convert-source-map/-/convert-source-map-2.0.0.tgz",
      "integrity": "sha512-Kvp459HrV2FEJ1CAsi1Ku+MY3kasH19TFykTz2xWmMeq6bk2NU3XXvfJ+Q61m0xktWwt+1HSYf3JZsTms3aRJg==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/cookie": {
      "version": "1.1.1",
      "resolved": "https://registry.npmmirror.com/cookie/-/cookie-1.1.1.tgz",
      "integrity": "sha512-ei8Aos7ja0weRpFzJnEA9UHJ/7XQmqglbRwnf2ATjcB9Wq874VKH9kfjjirM6UhU2/E5fFYadylyhFldcqSidQ==",
      "license": "MIT",
      "engines": {
        "node": ">=18"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/express"
      }
    },
    "node_modules/core-js-compat": {
      "version": "3.49.0",
      "resolved": "https://registry.npmmirror.com/core-js-compat/-/core-js-compat-3.49.0.tgz",
      "integrity": "sha512-VQXt1jr9cBz03b331DFDCCP90b3fanciLkgiOoy8SBHy06gNf+vQ1A3WFLqG7I8TipYIKeYK9wxd0tUrvHcOZA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "browserslist": "^4.28.1"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/core-js"
      }
    },
    "node_modules/cross-spawn": {
      "version": "7.0.6",
      "resolved": "https://registry.npmjs.org/cross-spawn/-/cross-spawn-7.0.6.tgz",
      "integrity": "sha512-uV2QOWP2nWzsy2aMp8aRibhi9dlzF5Hgh5SHaB9OiTGEyDTiJJyx0uy51QXdyWbtAHNua4XJzUKca3OzKUd3vA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "path-key": "^3.1.0",
        "shebang-command": "^2.0.0",
        "which": "^2.0.1"
      },
      "engines": {
        "node": ">= 8"
      }
    },
    "node_modules/cssesc": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/cssesc/-/cssesc-3.0.0.tgz",
      "integrity": "sha512-/Tb/JcjK111nNScGob5MNtsntNM1aCNUDipB/TkwZFhyDrrE47SOx/18wF2bbjgc3ZzCSKW1T5nt5EbFoAz/Vg==",
      "dev": true,
      "license": "MIT",
      "bin": {
        "cssesc": "bin/cssesc"
      },
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/csstype": {
      "version": "3.2.3",
      "resolved": "https://registry.npmjs.org/csstype/-/csstype-3.2.3.tgz",
      "integrity": "sha512-z1HGKcYy2xA8AGQfwrn0PAy+PB7X/GSj3UVJW9qKyn43xWa+gl5nXmU4qqLMRzWVLFC8KusUX8T/0kCiOYpAIQ==",
      "license": "MIT"
    },
    "node_modules/d3-array": {
      "version": "3.2.4",
      "resolved": "https://registry.npmjs.org/d3-array/-/d3-array-3.2.4.tgz",
      "integrity": "sha512-tdQAmyA18i4J7wprpYq8ClcxZy3SC31QMeByyCFyRt7BVHdREQZ5lpzoe5mFEYZUWe+oq8HBvk9JjpibyEV4Jg==",
      "license": "ISC",
      "dependencies": {
        "internmap": "1 - 2"
      },
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-color": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/d3-color/-/d3-color-3.1.0.tgz",
      "integrity": "sha512-zg/chbXyeBtMQ1LbD/WSoW2DpC3I0mpmPdW+ynRTj/x2DAWYrIY7qeZIHidozwV24m4iavr15lNwIwLxRmOxhA==",
      "license": "ISC",
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-ease": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/d3-ease/-/d3-ease-3.0.1.tgz",
      "integrity": "sha512-wR/XK3D3XcLIZwpbvQwQ5fK+8Ykds1ip7A2Txe0yxncXSdq1L9skcG7blcedkOX+ZcgxGAmLX1FrRGbADwzi0w==",
      "license": "BSD-3-Clause",
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-format": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/d3-format/-/d3-format-3.1.0.tgz",
      "integrity": "sha512-YyUI6AEuY/Wpt8KWLgZHsIU86atmikuoOmCfommt0LYHiQSPjvX2AcFc38PX0CBpr2RCyZhjex+NS/LPOv6YqA==",
      "license": "ISC",
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-interpolate": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/d3-interpolate/-/d3-interpolate-3.0.1.tgz",
      "integrity": "sha512-3bYs1rOD33uo8aqJfKP3JWPAibgw8Zm2+L9vBKEHJ2Rg+viTR7o5Mmv5mZcieN+FRYaAOWX5SJATX6k1PWz72g==",
      "license": "ISC",
      "dependencies": {
        "d3-color": "1 - 3"
      },
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-path": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/d3-path/-/d3-path-3.1.0.tgz",
      "integrity": "sha512-p3KP5HCf/bvjBSSKuXid6Zqijx7wIfNW+J/maPs+iwR35at5JCbLUT0LzF1cnjbCHWhqzQTIN2Jpe8pRebIEFQ==",
      "license": "ISC",
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-scale": {
      "version": "4.0.2",
      "resolved": "https://registry.npmjs.org/d3-scale/-/d3-scale-4.0.2.tgz",
      "integrity": "sha512-GZW464g1SH7ag3Y7hXjf8RoUuAFIqklOAq3MRl4OaWabTFJY9PN/E1YklhXLh+OQ3fM9yS2nOkCoS+WLZ6kvxQ==",
      "license": "ISC",
      "dependencies": {
        "d3-array": "2.10.0 - 3",
        "d3-format": "1 - 3",
        "d3-interpolate": "1.2.0 - 3",
        "d3-time": "2.1.1 - 3",
        "d3-time-format": "2 - 4"
      },
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-shape": {
      "version": "3.2.0",
      "resolved": "https://registry.npmjs.org/d3-shape/-/d3-shape-3.2.0.tgz",
      "integrity": "sha512-SaLBuwGm3MOViRq2ABk3eLoxwZELpH6zhl3FbAoJ7Vm1gofKx6El1Ib5z23NUEhF9AsGl7y+dzLe5Cw2AArGTA==",
      "license": "ISC",
      "dependencies": {
        "d3-path": "^3.1.0"
      },
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-time": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/d3-time/-/d3-time-3.1.0.tgz",
      "integrity": "sha512-VqKjzBLejbSMT4IgbmVgDjpkYrNWUYJnbCGo874u7MMKIWsILRX+OpX/gTk8MqjpT1A/c6HY2dCA77ZN0lkQ2Q==",
      "license": "ISC",
      "dependencies": {
        "d3-array": "2 - 3"
      },
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-time-format": {
      "version": "4.1.0",
      "resolved": "https://registry.npmjs.org/d3-time-format/-/d3-time-format-4.1.0.tgz",
      "integrity": "sha512-dJxPBlzC7NugB2PDLwo9Q8JiTR3M3e4/XANkreKSUxF8vvXKqm1Yfq4Q5dl8budlunRVlUUaDUgFt7eA8D6NLg==",
      "license": "ISC",
      "dependencies": {
        "d3-time": "1 - 3"
      },
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/d3-timer": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/d3-timer/-/d3-timer-3.0.1.tgz",
      "integrity": "sha512-ndfJ/JxxMd3nw31uyKoY2naivF+r29V+Lc0svZxe1JvvIRmi8hUsrMvdOwgS1o6uBHmiz91geQ0ylPP0aj1VUA==",
      "license": "ISC",
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/date-fns": {
      "version": "4.1.0",
      "resolved": "https://registry.npmjs.org/date-fns/-/date-fns-4.1.0.tgz",
      "integrity": "sha512-Ukq0owbQXxa/U3EGtsdVBkR1w7KOQ5gIBqdH2hkvknzZPYvBxb/aa6E8L7tmjFtkwZBu3UXBbjIgPo/Ez4xaNg==",
      "license": "MIT",
      "funding": {
        "type": "github",
        "url": "https://github.com/sponsors/kossnocorp"
      }
    },
    "node_modules/date-fns-jalali": {
      "version": "4.1.0-0",
      "resolved": "https://registry.npmjs.org/date-fns-jalali/-/date-fns-jalali-4.1.0-0.tgz",
      "integrity": "sha512-hTIP/z+t+qKwBDcmmsnmjWTduxCg+5KfdqWQvb2X/8C9+knYY6epN/pfxdDuyVlSVeFz0sM5eEfwIUQ70U4ckg==",
      "license": "MIT"
    },
    "node_modules/debug": {
      "version": "4.4.3",
      "resolved": "https://registry.npmjs.org/debug/-/debug-4.4.3.tgz",
      "integrity": "sha512-RGwwWnwQvkVfavKVt22FGLw+xYSdzARwm0ru6DhTVA3umU5hZc28V3kO4stgYryrTlLpuvgI9GiijltAjNbcqA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "ms": "^2.1.3"
      },
      "engines": {
        "node": ">=6.0"
      },
      "peerDependenciesMeta": {
        "supports-color": {
          "optional": true
        }
      }
    },
    "node_modules/decimal.js-light": {
      "version": "2.5.1",
      "resolved": "https://registry.npmjs.org/decimal.js-light/-/decimal.js-light-2.5.1.tgz",
      "integrity": "sha512-qIMFpTMZmny+MMIitAB6D7iVPEorVw6YQRWkvarTkT4tBeSLLiHzcwj6q0MmYSFCiVpiqPJTJEYIrpcPzVEIvg==",
      "license": "MIT"
    },
    "node_modules/deep-is": {
      "version": "0.1.4",
      "resolved": "https://registry.npmjs.org/deep-is/-/deep-is-0.1.4.tgz",
      "integrity": "sha512-oIPzksmTg4/MriiaYGO+okXDT7ztn/w3Eptv/+gSIdMdKsJo0u4CfYNFJPy+4SKMuCqGw2wxnA+URMg3t8a/bQ==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/detect-node-es": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/detect-node-es/-/detect-node-es-1.1.0.tgz",
      "integrity": "sha512-ypdmJU/TbBby2Dxibuv7ZLW3Bs1QEmM7nHjEANfohJLvE0XVujisn1qPJcZxg+qDucsr+bP6fLD1rPS3AhJ7EQ==",
      "license": "MIT"
    },
    "node_modules/didyoumean": {
      "version": "1.2.2",
      "resolved": "https://registry.npmjs.org/didyoumean/-/didyoumean-1.2.2.tgz",
      "integrity": "sha512-gxtyfqMg7GKyhQmb056K7M3xszy/myH8w+B4RT+QXBQsvAOdc3XymqDDPHx1BgPgsdAA5SIifona89YtRATDzw==",
      "dev": true,
      "license": "Apache-2.0"
    },
    "node_modules/dlv": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/dlv/-/dlv-1.1.3.tgz",
      "integrity": "sha512-+HlytyjlPKnIG8XuRG8WvmBP8xs8P71y+SKKS6ZXWoEgLuePxtDoUEiH7WkdePWrQ5JBpE6aoVqfZfJUQkjXwA==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/dom-helpers": {
      "version": "5.2.1",
      "resolved": "https://registry.npmjs.org/dom-helpers/-/dom-helpers-5.2.1.tgz",
      "integrity": "sha512-nRCa7CK3VTrM2NmGkIy4cbK7IZlgBE/PYMn55rrXefr5xXDP0LdtfPnblFDoVdcAfslJ7or6iqAUnx0CCGIWQA==",
      "license": "MIT",
      "dependencies": {
        "@babel/runtime": "^7.8.7",
        "csstype": "^3.0.2"
      }
    },
    "node_modules/electron-to-chromium": {
      "version": "1.5.267",
      "resolved": "https://registry.npmjs.org/electron-to-chromium/-/electron-to-chromium-1.5.267.tgz",
      "integrity": "sha512-0Drusm6MVRXSOJpGbaSVgcQsuB4hEkMpHXaVstcPmhu5LIedxs1xNK/nIxmQIU/RPC0+1/o0AVZfBTkTNJOdUw==",
      "dev": true,
      "license": "ISC"
    },
    "node_modules/embla-carousel": {
      "version": "8.6.0",
      "resolved": "https://registry.npmjs.org/embla-carousel/-/embla-carousel-8.6.0.tgz",
      "integrity": "sha512-SjWyZBHJPbqxHOzckOfo8lHisEaJWmwd23XppYFYVh10bU66/Pn5tkVkbkCMZVdbUE5eTCI2nD8OyIP4Z+uwkA==",
      "license": "MIT"
    },
    "node_modules/embla-carousel-react": {
      "version": "8.6.0",
      "resolved": "https://registry.npmjs.org/embla-carousel-react/-/embla-carousel-react-8.6.0.tgz",
      "integrity": "sha512-0/PjqU7geVmo6F734pmPqpyHqiM99olvyecY7zdweCw+6tKEXnrE90pBiBbMMU8s5tICemzpQ3hi5EpxzGW+JA==",
      "license": "MIT",
      "dependencies": {
        "embla-carousel": "8.6.0",
        "embla-carousel-reactive-utils": "8.6.0"
      },
      "peerDependencies": {
        "react": "^16.8.0 || ^17.0.1 || ^18.0.0 || ^19.0.0 || ^19.0.0-rc"
      }
    },
    "node_modules/embla-carousel-reactive-utils": {
      "version": "8.6.0",
      "resolved": "https://registry.npmjs.org/embla-carousel-reactive-utils/-/embla-carousel-reactive-utils-8.6.0.tgz",
      "integrity": "sha512-fMVUDUEx0/uIEDM0Mz3dHznDhfX+znCCDCeIophYb1QGVM7YThSWX+wz11zlYwWFOr74b4QLGg0hrGPJeG2s4A==",
      "license": "MIT",
      "peerDependencies": {
        "embla-carousel": "8.6.0"
      }
    },
    "node_modules/esbuild": {
      "version": "0.27.2",
      "resolved": "https://registry.npmjs.org/esbuild/-/esbuild-0.27.2.tgz",
      "integrity": "sha512-HyNQImnsOC7X9PMNaCIeAm4ISCQXs5a5YasTXVliKv4uuBo1dKrG0A+uQS8M5eXjVMnLg3WgXaKvprHlFJQffw==",
      "dev": true,
      "hasInstallScript": true,
      "license": "MIT",
      "bin": {
        "esbuild": "bin/esbuild"
      },
      "engines": {
        "node": ">=18"
      },
      "optionalDependencies": {
        "@esbuild/aix-ppc64": "0.27.2",
        "@esbuild/android-arm": "0.27.2",
        "@esbuild/android-arm64": "0.27.2",
        "@esbuild/android-x64": "0.27.2",
        "@esbuild/darwin-arm64": "0.27.2",
        "@esbuild/darwin-x64": "0.27.2",
        "@esbuild/freebsd-arm64": "0.27.2",
        "@esbuild/freebsd-x64": "0.27.2",
        "@esbuild/linux-arm": "0.27.2",
        "@esbuild/linux-arm64": "0.27.2",
        "@esbuild/linux-ia32": "0.27.2",
        "@esbuild/linux-loong64": "0.27.2",
        "@esbuild/linux-mips64el": "0.27.2",
        "@esbuild/linux-ppc64": "0.27.2",
        "@esbuild/linux-riscv64": "0.27.2",
        "@esbuild/linux-s390x": "0.27.2",
        "@esbuild/linux-x64": "0.27.2",
        "@esbuild/netbsd-arm64": "0.27.2",
        "@esbuild/netbsd-x64": "0.27.2",
        "@esbuild/openbsd-arm64": "0.27.2",
        "@esbuild/openbsd-x64": "0.27.2",
        "@esbuild/openharmony-arm64": "0.27.2",
        "@esbuild/sunos-x64": "0.27.2",
        "@esbuild/win32-arm64": "0.27.2",
        "@esbuild/win32-ia32": "0.27.2",
        "@esbuild/win32-x64": "0.27.2"
      }
    },
    "node_modules/escalade": {
      "version": "3.2.0",
      "resolved": "https://registry.npmjs.org/escalade/-/escalade-3.2.0.tgz",
      "integrity": "sha512-WUj2qlxaQtO4g6Pq5c29GTcWGDyd8itL8zTlipgECz3JesAiiOKotd8JU6otB3PACgG6xkJUyVhboMS+bje/jA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6"
      }
    },
    "node_modules/escape-string-regexp": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/escape-string-regexp/-/escape-string-regexp-4.0.0.tgz",
      "integrity": "sha512-TtpcNJ3XAzx3Gq8sWRzJaVajRs0uVxA2YAkdb1jm2YkPz4G6egUFAyA3n5vtEIZefPk5Wa4UXbKuS5fKkJWdgA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=10"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/eslint": {
      "version": "9.39.2",
      "resolved": "https://registry.npmjs.org/eslint/-/eslint-9.39.2.tgz",
      "integrity": "sha512-LEyamqS7W5HB3ujJyvi0HQK/dtVINZvd5mAAp9eT5S/ujByGjiZLCzPcHVzuXbpJDJF/cxwHlfceVUDZ2lnSTw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@eslint-community/eslint-utils": "^4.8.0",
        "@eslint-community/regexpp": "^4.12.1",
        "@eslint/config-array": "^0.21.1",
        "@eslint/config-helpers": "^0.4.2",
        "@eslint/core": "^0.17.0",
        "@eslint/eslintrc": "^3.3.1",
        "@eslint/js": "9.39.2",
        "@eslint/plugin-kit": "^0.4.1",
        "@humanfs/node": "^0.16.6",
        "@humanwhocodes/module-importer": "^1.0.1",
        "@humanwhocodes/retry": "^0.4.2",
        "@types/estree": "^1.0.6",
        "ajv": "^6.12.4",
        "chalk": "^4.0.0",
        "cross-spawn": "^7.0.6",
        "debug": "^4.3.2",
        "escape-string-regexp": "^4.0.0",
        "eslint-scope": "^8.4.0",
        "eslint-visitor-keys": "^4.2.1",
        "espree": "^10.4.0",
        "esquery": "^1.5.0",
        "esutils": "^2.0.2",
        "fast-deep-equal": "^3.1.3",
        "file-entry-cache": "^8.0.0",
        "find-up": "^5.0.0",
        "glob-parent": "^6.0.2",
        "ignore": "^5.2.0",
        "imurmurhash": "^0.1.4",
        "is-glob": "^4.0.0",
        "json-stable-stringify-without-jsonify": "^1.0.1",
        "lodash.merge": "^4.6.2",
        "minimatch": "^3.1.2",
        "natural-compare": "^1.4.0",
        "optionator": "^0.9.3"
      },
      "bin": {
        "eslint": "bin/eslint.js"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "url": "https://eslint.org/donate"
      },
      "peerDependencies": {
        "jiti": "*"
      },
      "peerDependenciesMeta": {
        "jiti": {
          "optional": true
        }
      }
    },
    "node_modules/eslint-plugin-react-hooks": {
      "version": "7.0.1",
      "resolved": "https://registry.npmjs.org/eslint-plugin-react-hooks/-/eslint-plugin-react-hooks-7.0.1.tgz",
      "integrity": "sha512-O0d0m04evaNzEPoSW+59Mezf8Qt0InfgGIBJnpC0h3NH/WjUAR7BIKUfysC6todmtiZ/A0oUVS8Gce0WhBrHsA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@babel/core": "^7.24.4",
        "@babel/parser": "^7.24.4",
        "hermes-parser": "^0.25.1",
        "zod": "^3.25.0 || ^4.0.0",
        "zod-validation-error": "^3.5.0 || ^4.0.0"
      },
      "engines": {
        "node": ">=18"
      },
      "peerDependencies": {
        "eslint": "^3.0.0 || ^4.0.0 || ^5.0.0 || ^6.0.0 || ^7.0.0 || ^8.0.0-0 || ^9.0.0"
      }
    },
    "node_modules/eslint-plugin-react-refresh": {
      "version": "0.4.26",
      "resolved": "https://registry.npmjs.org/eslint-plugin-react-refresh/-/eslint-plugin-react-refresh-0.4.26.tgz",
      "integrity": "sha512-1RETEylht2O6FM/MvgnyvT+8K21wLqDNg4qD51Zj3guhjt433XbnnkVttHMyaVyAFD03QSV4LPS5iE3VQmO7XQ==",
      "dev": true,
      "license": "MIT",
      "peerDependencies": {
        "eslint": ">=8.40"
      }
    },
    "node_modules/eslint-scope": {
      "version": "8.4.0",
      "resolved": "https://registry.npmjs.org/eslint-scope/-/eslint-scope-8.4.0.tgz",
      "integrity": "sha512-sNXOfKCn74rt8RICKMvJS7XKV/Xk9kA7DyJr8mJik3S7Cwgy3qlkkmyS2uQB3jiJg6VNdZd/pDBJu0nvG2NlTg==",
      "dev": true,
      "license": "BSD-2-Clause",
      "dependencies": {
        "esrecurse": "^4.3.0",
        "estraverse": "^5.2.0"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "url": "https://opencollective.com/eslint"
      }
    },
    "node_modules/eslint-visitor-keys": {
      "version": "4.2.1",
      "resolved": "https://registry.npmjs.org/eslint-visitor-keys/-/eslint-visitor-keys-4.2.1.tgz",
      "integrity": "sha512-Uhdk5sfqcee/9H/rCOJikYz67o0a2Tw2hGRPOG2Y1R2dg7brRe1uG0yaNQDHu+TO/uQPF/5eCapvYSmHUjt7JQ==",
      "dev": true,
      "license": "Apache-2.0",
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "url": "https://opencollective.com/eslint"
      }
    },
    "node_modules/espree": {
      "version": "10.4.0",
      "resolved": "https://registry.npmjs.org/espree/-/espree-10.4.0.tgz",
      "integrity": "sha512-j6PAQ2uUr79PZhBjP5C5fhl8e39FmRnOjsD5lGnWrFU8i2G776tBK7+nP8KuQUTTyAZUwfQqXAgrVH5MbH9CYQ==",
      "dev": true,
      "license": "BSD-2-Clause",
      "dependencies": {
        "acorn": "^8.15.0",
        "acorn-jsx": "^5.3.2",
        "eslint-visitor-keys": "^4.2.1"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "url": "https://opencollective.com/eslint"
      }
    },
    "node_modules/esquery": {
      "version": "1.7.0",
      "resolved": "https://registry.npmjs.org/esquery/-/esquery-1.7.0.tgz",
      "integrity": "sha512-Ap6G0WQwcU/LHsvLwON1fAQX9Zp0A2Y6Y/cJBl9r/JbW90Zyg4/zbG6zzKa2OTALELarYHmKu0GhpM5EO+7T0g==",
      "dev": true,
      "license": "BSD-3-Clause",
      "dependencies": {
        "estraverse": "^5.1.0"
      },
      "engines": {
        "node": ">=0.10"
      }
    },
    "node_modules/esrecurse": {
      "version": "4.3.0",
      "resolved": "https://registry.npmjs.org/esrecurse/-/esrecurse-4.3.0.tgz",
      "integrity": "sha512-KmfKL3b6G+RXvP8N1vr3Tq1kL/oCFgn2NYXEtqP8/L3pKapUA4G8cFVaoF3SU323CD4XypR/ffioHmkti6/Tag==",
      "dev": true,
      "license": "BSD-2-Clause",
      "dependencies": {
        "estraverse": "^5.2.0"
      },
      "engines": {
        "node": ">=4.0"
      }
    },
    "node_modules/estraverse": {
      "version": "5.3.0",
      "resolved": "https://registry.npmjs.org/estraverse/-/estraverse-5.3.0.tgz",
      "integrity": "sha512-MMdARuVEQziNTeJD8DgMqmhwR11BRQ/cBP+pLtYdSTnf3MIO8fFeiINEbX36ZdNlfU/7A9f3gUw49B3oQsvwBA==",
      "dev": true,
      "license": "BSD-2-Clause",
      "engines": {
        "node": ">=4.0"
      }
    },
    "node_modules/esutils": {
      "version": "2.0.3",
      "resolved": "https://registry.npmjs.org/esutils/-/esutils-2.0.3.tgz",
      "integrity": "sha512-kVscqXk4OCp68SZ0dkgEKVi6/8ij300KBWTJq32P/dYeWTSwK41WyTxalN1eRmA5Z9UU/LX9D7FWSmV9SAYx6g==",
      "dev": true,
      "license": "BSD-2-Clause",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/eventemitter3": {
      "version": "4.0.7",
      "resolved": "https://registry.npmjs.org/eventemitter3/-/eventemitter3-4.0.7.tgz",
      "integrity": "sha512-8guHBZCwKnFhYdHr2ysuRWErTwhoN2X8XELRlrRwpmfeY2jjuUN4taQMsULKUVo1K4DvZl+0pgfyoysHxvmvEw==",
      "license": "MIT"
    },
    "node_modules/fast-deep-equal": {
      "version": "3.1.3",
      "resolved": "https://registry.npmjs.org/fast-deep-equal/-/fast-deep-equal-3.1.3.tgz",
      "integrity": "sha512-f3qQ9oQy9j2AhBe/H9VC91wLmKBCCU/gDOnKNAYG5hswO7BLKj09Hc5HYNz9cGI++xlpDCIgDaitVs03ATR84Q==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/fast-equals": {
      "version": "5.4.0",
      "resolved": "https://registry.npmjs.org/fast-equals/-/fast-equals-5.4.0.tgz",
      "integrity": "sha512-jt2DW/aNFNwke7AUd+Z+e6pz39KO5rzdbbFCg2sGafS4mk13MI7Z8O5z9cADNn5lhGODIgLwug6TZO2ctf7kcw==",
      "license": "MIT",
      "engines": {
        "node": ">=6.0.0"
      }
    },
    "node_modules/fast-glob": {
      "version": "3.3.3",
      "resolved": "https://registry.npmjs.org/fast-glob/-/fast-glob-3.3.3.tgz",
      "integrity": "sha512-7MptL8U0cqcFdzIzwOTHoilX9x5BrNqye7Z/LuC7kCMRio1EMSyqRK3BEAUD7sXRq4iT4AzTVuZdhgQ2TCvYLg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@nodelib/fs.stat": "^2.0.2",
        "@nodelib/fs.walk": "^1.2.3",
        "glob-parent": "^5.1.2",
        "merge2": "^1.3.0",
        "micromatch": "^4.0.8"
      },
      "engines": {
        "node": ">=8.6.0"
      }
    },
    "node_modules/fast-glob/node_modules/glob-parent": {
      "version": "5.1.2",
      "resolved": "https://registry.npmjs.org/glob-parent/-/glob-parent-5.1.2.tgz",
      "integrity": "sha512-AOIgSQCepiJYwP3ARnGx+5VnTu2HBYdzbGP45eLw1vr3zB3vZLeyed1sC9hnbcOc9/SrMyM5RPQrkGz4aS9Zow==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "is-glob": "^4.0.1"
      },
      "engines": {
        "node": ">= 6"
      }
    },
    "node_modules/fast-json-stable-stringify": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/fast-json-stable-stringify/-/fast-json-stable-stringify-2.1.0.tgz",
      "integrity": "sha512-lhd/wF+Lk98HZoTCtlVraHtfh5XYijIjalXck7saUtuanSDyLMxnHhSXEDJqHxD7msR8D0uCmqlkwjCV8xvwHw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/fast-levenshtein": {
      "version": "2.0.6",
      "resolved": "https://registry.npmjs.org/fast-levenshtein/-/fast-levenshtein-2.0.6.tgz",
      "integrity": "sha512-DCXu6Ifhqcks7TZKY3Hxp3y6qphY5SJZmrWMDrKcERSOXWQdMhU9Ig/PYrzyw/ul9jOIyh0N4M0tbC5hodg8dw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/fastq": {
      "version": "1.20.1",
      "resolved": "https://registry.npmjs.org/fastq/-/fastq-1.20.1.tgz",
      "integrity": "sha512-GGToxJ/w1x32s/D2EKND7kTil4n8OVk/9mycTc4VDza13lOvpUZTGX3mFSCtV9ksdGBVzvsyAVLM6mHFThxXxw==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "reusify": "^1.0.4"
      }
    },
    "node_modules/fdir": {
      "version": "6.5.0",
      "resolved": "https://registry.npmjs.org/fdir/-/fdir-6.5.0.tgz",
      "integrity": "sha512-tIbYtZbucOs0BRGqPJkshJUYdL+SDH7dVM8gjy+ERp3WAUjLEFJE+02kanyHtwjWOnwrKYBiwAmM0p4kLJAnXg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=12.0.0"
      },
      "peerDependencies": {
        "picomatch": "^3 || ^4"
      },
      "peerDependenciesMeta": {
        "picomatch": {
          "optional": true
        }
      }
    },
    "node_modules/fflate": {
      "version": "0.8.3",
      "resolved": "https://registry.npmmirror.com/fflate/-/fflate-0.8.3.tgz",
      "integrity": "sha512-tbZNuJrLwGUp3zshBtdy4W+ORxZuIh8a5ilyIEQDC5rY1f3U20JMry0Ll3WBzU58EZKsEuJFXhb5gwv8CsPvgA==",
      "license": "MIT"
    },
    "node_modules/file-entry-cache": {
      "version": "8.0.0",
      "resolved": "https://registry.npmjs.org/file-entry-cache/-/file-entry-cache-8.0.0.tgz",
      "integrity": "sha512-XXTUwCvisa5oacNGRP9SfNtYBNAMi+RPwBFmblZEF7N7swHYQS6/Zfk7SRwx4D5j3CH211YNRco1DEMNVfZCnQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "flat-cache": "^4.0.0"
      },
      "engines": {
        "node": ">=16.0.0"
      }
    },
    "node_modules/fill-range": {
      "version": "7.1.1",
      "resolved": "https://registry.npmjs.org/fill-range/-/fill-range-7.1.1.tgz",
      "integrity": "sha512-YsGpe3WHLK8ZYi4tWDg2Jy3ebRz2rXowDxnld4bkQB00cc/1Zw9AWnC0i9ztDJitivtQvaI9KaLyKrc+hBW0yg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "to-regex-range": "^5.0.1"
      },
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/find-up": {
      "version": "5.0.0",
      "resolved": "https://registry.npmjs.org/find-up/-/find-up-5.0.0.tgz",
      "integrity": "sha512-78/PXT1wlLLDgTzDs7sjq9hzz0vXD+zn+7wypEe4fXQxCmdmqfGsEPQxmiCSQI3ajFV91bVSsvNtrJRiW6nGng==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "locate-path": "^6.0.0",
        "path-exists": "^4.0.0"
      },
      "engines": {
        "node": ">=10"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/flat-cache": {
      "version": "4.0.1",
      "resolved": "https://registry.npmjs.org/flat-cache/-/flat-cache-4.0.1.tgz",
      "integrity": "sha512-f7ccFPK3SXFHpx15UIGyRJ/FJQctuKZ0zVuN3frBo4HnK3cay9VEW0R6yPYFHC0AgqhukPzKjq22t5DmAyqGyw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "flatted": "^3.2.9",
        "keyv": "^4.5.4"
      },
      "engines": {
        "node": ">=16"
      }
    },
    "node_modules/flatted": {
      "version": "3.3.3",
      "resolved": "https://registry.npmjs.org/flatted/-/flatted-3.3.3.tgz",
      "integrity": "sha512-GX+ysw4PBCz0PzosHDepZGANEuFCMLrnRTiEy9McGjmkCQYwRq4A/X786G/fjM/+OjsWSU1ZrY5qyARZmO/uwg==",
      "dev": true,
      "license": "ISC"
    },
    "node_modules/fraction.js": {
      "version": "5.3.4",
      "resolved": "https://registry.npmjs.org/fraction.js/-/fraction.js-5.3.4.tgz",
      "integrity": "sha512-1X1NTtiJphryn/uLQz3whtY6jK3fTqoE3ohKs0tT+Ujr1W59oopxmoEh7Lu5p6vBaPbgoM0bzveAW4Qi5RyWDQ==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": "*"
      },
      "funding": {
        "type": "github",
        "url": "https://github.com/sponsors/rawify"
      }
    },
    "node_modules/fsevents": {
      "version": "2.3.3",
      "resolved": "https://registry.npmjs.org/fsevents/-/fsevents-2.3.3.tgz",
      "integrity": "sha512-5xoDfX+fL7faATnagmWPpbFtwh/R77WmMMqqHGS65C3vvB0YHrgF+B1YmZ3441tMj5n63k0212XNoJwzlhffQw==",
      "dev": true,
      "hasInstallScript": true,
      "license": "MIT",
      "optional": true,
      "os": [
        "darwin"
      ],
      "engines": {
        "node": "^8.16.0 || ^10.6.0 || >=11.0.0"
      }
    },
    "node_modules/function-bind": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/function-bind/-/function-bind-1.1.2.tgz",
      "integrity": "sha512-7XHNxH7qX9xG5mIwxkhumTox/MIRNcOgDrxWsMt2pAr23WHp6MrRlN7FBSFpCpr+oVO0F744iUgR82nJMfG2SA==",
      "dev": true,
      "license": "MIT",
      "funding": {
        "url": "https://github.com/sponsors/ljharb"
      }
    },
    "node_modules/gensync": {
      "version": "1.0.0-beta.2",
      "resolved": "https://registry.npmjs.org/gensync/-/gensync-1.0.0-beta.2.tgz",
      "integrity": "sha512-3hN7NaskYvMDLQY55gnW3NQ+mesEAepTqlg+VEbj7zzqEMBVNhzcGYYeqFo/TlYz6eQiFcp1HcsCZO+nGgS8zg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6.9.0"
      }
    },
    "node_modules/get-nonce": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/get-nonce/-/get-nonce-1.0.1.tgz",
      "integrity": "sha512-FJhYRoDaiatfEkUK8HKlicmu/3SGFD51q3itKDGoSTysQJBnfOcxU5GxnhE1E6soB76MbT0MBtnKJuXyAx+96Q==",
      "license": "MIT",
      "engines": {
        "node": ">=6"
      }
    },
    "node_modules/glob-parent": {
      "version": "6.0.2",
      "resolved": "https://registry.npmjs.org/glob-parent/-/glob-parent-6.0.2.tgz",
      "integrity": "sha512-XxwI8EOhVQgWp6iDL+3b0r86f4d6AX6zSU55HfB4ydCEuXLXc5FcYeOu+nnGftS4TEju/11rt4KJPTMgbfmv4A==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "is-glob": "^4.0.3"
      },
      "engines": {
        "node": ">=10.13.0"
      }
    },
    "node_modules/globals": {
      "version": "16.5.0",
      "resolved": "https://registry.npmjs.org/globals/-/globals-16.5.0.tgz",
      "integrity": "sha512-c/c15i26VrJ4IRt5Z89DnIzCGDn9EcebibhAOjw5ibqEHsE1wLUgkPn9RDmNcUKyU87GeaL633nyJ+pplFR2ZQ==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=18"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/gsap": {
      "version": "3.15.0",
      "resolved": "https://registry.npmmirror.com/gsap/-/gsap-3.15.0.tgz",
      "integrity": "sha512-dMW4CWBTUK1AEEDeZc1g4xpPGIrSf9fJF960qbTZmN/QwZIWY5wgliS6JWl9/25fpTGJrMRtSjGtOmPnfjZB+A==",
      "license": "Standard 'no charge' license: https://gsap.com/standard-license."
    },
    "node_modules/has-flag": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/has-flag/-/has-flag-4.0.0.tgz",
      "integrity": "sha512-EykJT/Q1KjTWctppgIAgfSO0tKVuZUjhgMr17kqTumMl6Afv3EISleU7qZUzoXDFTAHTDC4NOoG/ZxU3EvlMPQ==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/hasown": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/hasown/-/hasown-2.0.2.tgz",
      "integrity": "sha512-0hJU9SCPvmMzIBdZFqNPXWa6dqh7WdH0cII9y+CyS8rG3nL48Bclra9HmKhVVUHyPWNH5Y7xDwAB7bfgSjkUMQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "function-bind": "^1.1.2"
      },
      "engines": {
        "node": ">= 0.4"
      }
    },
    "node_modules/hermes-estree": {
      "version": "0.25.1",
      "resolved": "https://registry.npmjs.org/hermes-estree/-/hermes-estree-0.25.1.tgz",
      "integrity": "sha512-0wUoCcLp+5Ev5pDW2OriHC2MJCbwLwuRx+gAqMTOkGKJJiBCLjtrvy4PWUGn6MIVefecRpzoOZ/UV6iGdOr+Cw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/hermes-parser": {
      "version": "0.25.1",
      "resolved": "https://registry.npmjs.org/hermes-parser/-/hermes-parser-0.25.1.tgz",
      "integrity": "sha512-6pEjquH3rqaI6cYAXYPcz9MS4rY6R4ngRgrgfDshRptUZIc3lw0MCIJIGDj9++mfySOuPTHB4nrSW99BCvOPIA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "hermes-estree": "0.25.1"
      }
    },
    "node_modules/ignore": {
      "version": "5.3.2",
      "resolved": "https://registry.npmjs.org/ignore/-/ignore-5.3.2.tgz",
      "integrity": "sha512-hsBTNUqQTDwkWtcdYI2i06Y/nUBEsNEDJKjWdigLvegy8kDuJAS8uRlpkkcQpyEXL0Z/pjDy5HBmMjRCJ2gq+g==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 4"
      }
    },
    "node_modules/import-fresh": {
      "version": "3.3.1",
      "resolved": "https://registry.npmjs.org/import-fresh/-/import-fresh-3.3.1.tgz",
      "integrity": "sha512-TR3KfrTZTYLPB6jUjfx6MF9WcWrHL9su5TObK4ZkYgBdWKPOFoSoQIdEuTuR82pmtxH2spWG9h6etwfr1pLBqQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "parent-module": "^1.0.0",
        "resolve-from": "^4.0.0"
      },
      "engines": {
        "node": ">=6"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/imurmurhash": {
      "version": "0.1.4",
      "resolved": "https://registry.npmjs.org/imurmurhash/-/imurmurhash-0.1.4.tgz",
      "integrity": "sha512-JmXMZ6wuvDmLiHEml9ykzqO6lwFbof0GG4IkcGaENdCRDDmMVnny7s5HsIgHCbaq0w2MyPhDqkhTUgS2LU2PHA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=0.8.19"
      }
    },
    "node_modules/input-otp": {
      "version": "1.4.2",
      "resolved": "https://registry.npmjs.org/input-otp/-/input-otp-1.4.2.tgz",
      "integrity": "sha512-l3jWwYNvrEa6NTCt7BECfCm48GvwuZzkoeG3gBL2w4CHeOXW3eKFmf9UNYkNfYc3mxMrthMnxjIE07MT0zLBQA==",
      "license": "MIT",
      "peerDependencies": {
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0.0 || ^19.0.0-rc"
      }
    },
    "node_modules/internmap": {
      "version": "2.0.3",
      "resolved": "https://registry.npmjs.org/internmap/-/internmap-2.0.3.tgz",
      "integrity": "sha512-5Hh7Y1wQbvY5ooGgPbDaL5iYLAPzMTUrjMulskHLH6wnv/A+1q5rgEaiuqEjB+oxGXIVZs1FF+R/KPN3ZSQYYg==",
      "license": "ISC",
      "engines": {
        "node": ">=12"
      }
    },
    "node_modules/is-binary-path": {
      "version": "2.1.0",
      "resolved": "https://registry.npmjs.org/is-binary-path/-/is-binary-path-2.1.0.tgz",
      "integrity": "sha512-ZMERYes6pDydyuGidse7OsHxtbI7WVeUEozgR/g7rd0xUimYNlvZRE/K2MgZTjWy725IfelLeVcEM97mmtRGXw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "binary-extensions": "^2.0.0"
      },
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/is-core-module": {
      "version": "2.16.1",
      "resolved": "https://registry.npmjs.org/is-core-module/-/is-core-module-2.16.1.tgz",
      "integrity": "sha512-UfoeMA6fIJ8wTYFEUjelnaGI67v6+N7qXJEvQuIGa99l4xsCruSYOVSQ0uPANn4dAzm8lkYPaKLrrijLq7x23w==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "hasown": "^2.0.2"
      },
      "engines": {
        "node": ">= 0.4"
      },
      "funding": {
        "url": "https://github.com/sponsors/ljharb"
      }
    },
    "node_modules/is-extglob": {
      "version": "2.1.1",
      "resolved": "https://registry.npmjs.org/is-extglob/-/is-extglob-2.1.1.tgz",
      "integrity": "sha512-SbKbANkN603Vi4jEZv49LeVJMn4yGwsbzZworEoyEiutsN3nJYdbO36zfhGJ6QEDpOZIFkDtnq5JRxmvl3jsoQ==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/is-glob": {
      "version": "4.0.3",
      "resolved": "https://registry.npmjs.org/is-glob/-/is-glob-4.0.3.tgz",
      "integrity": "sha512-xelSayHH36ZgE7ZWhli7pW34hNbNl8Ojv5KVmkJD4hBdD3th8Tfk9vYasLM+mXWOZhFkgZfxhLSnrwRr4elSSg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "is-extglob": "^2.1.1"
      },
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/is-number": {
      "version": "7.0.0",
      "resolved": "https://registry.npmjs.org/is-number/-/is-number-7.0.0.tgz",
      "integrity": "sha512-41Cifkg6e8TylSpdtTpeLVMqvSBEVzTttHvERD741+pnZ8ANv0004MRL43QKPDlK9cGvNp6NZWZUBlbGXYxxng==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=0.12.0"
      }
    },
    "node_modules/isexe": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/isexe/-/isexe-2.0.0.tgz",
      "integrity": "sha512-RHxMLp9lnKHGHRng9QFhRCMbYAcVpn69smSGcq3f36xjgVVWThj4qqLbTLlq7Ssj8B+fIQ1EuCEGI2lKsyQeIw==",
      "dev": true,
      "license": "ISC"
    },
    "node_modules/jiti": {
      "version": "1.21.7",
      "resolved": "https://registry.npmjs.org/jiti/-/jiti-1.21.7.tgz",
      "integrity": "sha512-/imKNG4EbWNrVjoNC/1H5/9GFy+tqjGBHCaSsN+P2RnPqjsLmv6UD3Ej+Kj8nBWaRAwyk7kK5ZUc+OEatnTR3A==",
      "dev": true,
      "license": "MIT",
      "bin": {
        "jiti": "bin/jiti.js"
      }
    },
    "node_modules/js-tokens": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/js-tokens/-/js-tokens-4.0.0.tgz",
      "integrity": "sha512-RdJUflcE3cUzKiMqQgsCu06FPu9UdIJO0beYbPhHN4k6apgJtifcoCtT9bcxOpYBtpD2kCM6Sbzg4CausW/PKQ==",
      "license": "MIT"
    },
    "node_modules/js-yaml": {
      "version": "4.1.1",
      "resolved": "https://registry.npmjs.org/js-yaml/-/js-yaml-4.1.1.tgz",
      "integrity": "sha512-qQKT4zQxXl8lLwBtHMWwaTcGfFOZviOJet3Oy/xmGk2gZH677CJM9EvtfdSkgWcATZhj/55JZ0rmy3myCT5lsA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "argparse": "^2.0.1"
      },
      "bin": {
        "js-yaml": "bin/js-yaml.js"
      }
    },
    "node_modules/jsesc": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/jsesc/-/jsesc-3.1.0.tgz",
      "integrity": "sha512-/sM3dO2FOzXjKQhJuo0Q173wf2KOo8t4I8vHy6lF9poUp7bKT0/NHE8fPX23PwfhnykfqnC2xRxOnVw5XuGIaA==",
      "dev": true,
      "license": "MIT",
      "bin": {
        "jsesc": "bin/jsesc"
      },
      "engines": {
        "node": ">=6"
      }
    },
    "node_modules/json-buffer": {
      "version": "3.0.1",
      "resolved": "https://registry.npmjs.org/json-buffer/-/json-buffer-3.0.1.tgz",
      "integrity": "sha512-4bV5BfR2mqfQTJm+V5tPPdf+ZpuhiIvTuAB5g8kcrXOZpTT/QwwVRWBywX1ozr6lEuPdbHxwaJlm9G6mI2sfSQ==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/json-schema-traverse": {
      "version": "0.4.1",
      "resolved": "https://registry.npmjs.org/json-schema-traverse/-/json-schema-traverse-0.4.1.tgz",
      "integrity": "sha512-xbbCH5dCYU5T8LcEhhuh7HJ88HXuW3qsI3Y0zOZFKfZEHcpWiHU/Jxzk629Brsab/mMiHQti9wMP+845RPe3Vg==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/json-stable-stringify-without-jsonify": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/json-stable-stringify-without-jsonify/-/json-stable-stringify-without-jsonify-1.0.1.tgz",
      "integrity": "sha512-Bdboy+l7tA3OGW6FjyFHWkP5LuByj1Tk33Ljyq0axyzdk9//JSi2u3fP1QSmd1KNwq6VOKYGlAu87CisVir6Pw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/json5": {
      "version": "2.2.3",
      "resolved": "https://registry.npmjs.org/json5/-/json5-2.2.3.tgz",
      "integrity": "sha512-XmOWe7eyHYH14cLdVPoyg+GOH3rYX++KpzrylJwSW98t3Nk+U8XOl8FWKOgwtzdb8lXGf6zYwDUzeHMWfxasyg==",
      "dev": true,
      "license": "MIT",
      "bin": {
        "json5": "lib/cli.js"
      },
      "engines": {
        "node": ">=6"
      }
    },
    "node_modules/keyv": {
      "version": "4.5.4",
      "resolved": "https://registry.npmjs.org/keyv/-/keyv-4.5.4.tgz",
      "integrity": "sha512-oxVHkHR/EJf2CNXnWxRLW6mg7JyCCUcG0DtEGmL2ctUo1PNTin1PUil+r/+4r5MpVgC/fn1kjsx7mjSujKqIpw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "json-buffer": "3.0.1"
      }
    },
    "node_modules/kimi-plugin-inspect-react": {
      "version": "1.0.3",
      "resolved": "https://registry.npmmirror.com/kimi-plugin-inspect-react/-/kimi-plugin-inspect-react-1.0.3.tgz",
      "integrity": "sha512-dU0dYaFYvczJZWwsyAVQ2No2NTaycd93zk3zrbLj9IPwdZaLBK4d0cESz88lVju3rQuFiwRXYNDaCnbPxn4JcQ==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "@babel/core": "^7.23.0",
        "@babel/plugin-proposal-decorators": "^7.23.0",
        "@babel/preset-env": "^7.23.0",
        "@babel/preset-react": "^7.23.0",
        "@babel/preset-typescript": "^7.23.0",
        "@babel/types": "^7.23.0",
        "magic-string": "^0.30.0"
      },
      "peerDependencies": {
        "vite": "^7.2.0"
      }
    },
    "node_modules/levn": {
      "version": "0.4.1",
      "resolved": "https://registry.npmjs.org/levn/-/levn-0.4.1.tgz",
      "integrity": "sha512-+bT2uH4E5LGE7h/n3evcS/sQlJXCpIp6ym8OWJ5eV6+67Dsql/LaaT7qJBAt2rzfoa/5QBGBhxDix1dMt2kQKQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "prelude-ls": "^1.2.1",
        "type-check": "~0.4.0"
      },
      "engines": {
        "node": ">= 0.8.0"
      }
    },
    "node_modules/lilconfig": {
      "version": "3.1.3",
      "resolved": "https://registry.npmjs.org/lilconfig/-/lilconfig-3.1.3.tgz",
      "integrity": "sha512-/vlFKAoH5Cgt3Ie+JLhRbwOsCQePABiU3tJ1egGvyQ+33R/vcwM2Zl2QR/LzjsBeItPt3oSVXapn+m4nQDvpzw==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=14"
      },
      "funding": {
        "url": "https://github.com/sponsors/antonk52"
      }
    },
    "node_modules/lines-and-columns": {
      "version": "1.2.4",
      "resolved": "https://registry.npmjs.org/lines-and-columns/-/lines-and-columns-1.2.4.tgz",
      "integrity": "sha512-7ylylesZQ/PV29jhEDl3Ufjo6ZX7gCqJr5F7PKrqc93v7fzSymt1BpwEU8nAUXs8qzzvqhbjhK5QZg6Mt/HkBg==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/locate-path": {
      "version": "6.0.0",
      "resolved": "https://registry.npmjs.org/locate-path/-/locate-path-6.0.0.tgz",
      "integrity": "sha512-iPZK6eYjbxRu3uB4/WZ3EsEIMJFMqAoopl3R+zuq0UjcAm/MO6KCweDgPfP3elTztoKP3KtnVHxTn2NHBSDVUw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "p-locate": "^5.0.0"
      },
      "engines": {
        "node": ">=10"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/lodash": {
      "version": "4.17.21",
      "resolved": "https://registry.npmjs.org/lodash/-/lodash-4.17.21.tgz",
      "integrity": "sha512-v2kDEe57lecTulaDIuNTPy3Ry4gLGJ6Z1O3vE1krgXZNrsQ+LFTGHVxVjcXPs17LhbZVGedAJv8XZ1tvj5FvSg==",
      "license": "MIT"
    },
    "node_modules/lodash.debounce": {
      "version": "4.0.8",
      "resolved": "https://registry.npmmirror.com/lodash.debounce/-/lodash.debounce-4.0.8.tgz",
      "integrity": "sha512-FT1yDzDYEoYWhnSGnpE/4Kj1fLZkDFyqRb7fNt6FdYOSxlUWAtp42Eh6Wb0rGIv/m9Bgo7x4GhQbm5Ys4SG5ow==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/lodash.merge": {
      "version": "4.6.2",
      "resolved": "https://registry.npmjs.org/lodash.merge/-/lodash.merge-4.6.2.tgz",
      "integrity": "sha512-0KpjqXRVvrYyCsX1swR/XTK0va6VQkQM6MNo7PqW77ByjAhoARA8EfrP1N4+KlKj8YS0ZUCtRT/YUuhyYDujIQ==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/loose-envify": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/loose-envify/-/loose-envify-1.4.0.tgz",
      "integrity": "sha512-lyuxPGr/Wfhrlem2CL/UcnUc1zcqKAImBDzukY7Y5F/yQiNdko6+fRLevlw1HgMySw7f611UIY408EtxRSoK3Q==",
      "license": "MIT",
      "dependencies": {
        "js-tokens": "^3.0.0 || ^4.0.0"
      },
      "bin": {
        "loose-envify": "cli.js"
      }
    },
    "node_modules/lru-cache": {
      "version": "5.1.1",
      "resolved": "https://registry.npmjs.org/lru-cache/-/lru-cache-5.1.1.tgz",
      "integrity": "sha512-KpNARQA3Iwv+jTA0utUVVbrh+Jlrr1Fv0e56GGzAFOXN7dk/FviaDW8LHmK52DlcH4WP2n6gI8vN1aesBFgo9w==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "yallist": "^3.0.2"
      }
    },
    "node_modules/lucide-react": {
      "version": "0.562.0",
      "resolved": "https://registry.npmjs.org/lucide-react/-/lucide-react-0.562.0.tgz",
      "integrity": "sha512-82hOAu7y0dbVuFfmO4bYF1XEwYk/mEbM5E+b1jgci/udUBEE/R7LF5Ip0CCEmXe8AybRM8L+04eP+LGZeDvkiw==",
      "license": "ISC",
      "peerDependencies": {
        "react": "^16.5.1 || ^17.0.0 || ^18.0.0 || ^19.0.0"
      }
    },
    "node_modules/magic-string": {
      "version": "0.30.21",
      "resolved": "https://registry.npmmirror.com/magic-string/-/magic-string-0.30.21.tgz",
      "integrity": "sha512-vd2F4YUyEXKGcLHoq+TEyCjxueSeHnFxyyjNp80yg0XV4vUhnDer/lvvlqM/arB5bXQN5K2/3oinyCRyx8T2CQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@jridgewell/sourcemap-codec": "^1.5.5"
      }
    },
    "node_modules/merge2": {
      "version": "1.4.1",
      "resolved": "https://registry.npmjs.org/merge2/-/merge2-1.4.1.tgz",
      "integrity": "sha512-8q7VEgMJW4J8tcfVPy8g09NcQwZdbwFEqhe/WZkoIzjn/3TGDwtOCYtXGxA3O8tPzpczCCDgv+P2P5y00ZJOOg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 8"
      }
    },
    "node_modules/meshoptimizer": {
      "version": "1.1.1",
      "resolved": "https://registry.npmmirror.com/meshoptimizer/-/meshoptimizer-1.1.1.tgz",
      "integrity": "sha512-oRFNWJRDA/WTrVj7NWvqa5HqE1t9MYDj2VaWirQCzCCrAd2GHrqR/sQezCxiWATPNlKTcRaPRHPJwIRoPBAp5g==",
      "license": "MIT"
    },
    "node_modules/micromatch": {
      "version": "4.0.8",
      "resolved": "https://registry.npmjs.org/micromatch/-/micromatch-4.0.8.tgz",
      "integrity": "sha512-PXwfBhYu0hBCPw8Dn0E+WDYb7af3dSLVWKi3HGv84IdF4TyFoC0ysxFd0Goxw7nSv4T/PzEJQxsYsEiFCKo2BA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "braces": "^3.0.3",
        "picomatch": "^2.3.1"
      },
      "engines": {
        "node": ">=8.6"
      }
    },
    "node_modules/micromatch/node_modules/picomatch": {
      "version": "2.3.1",
      "resolved": "https://registry.npmjs.org/picomatch/-/picomatch-2.3.1.tgz",
      "integrity": "sha512-JU3teHTNjmE2VCGFzuY8EXzCDVwEqB2a8fsIvwaStHhAWJEeVd1o1QD80CU6+ZdEXXSLbSsuLwJjkCBWqRQUVA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8.6"
      },
      "funding": {
        "url": "https://github.com/sponsors/jonschlinkert"
      }
    },
    "node_modules/minimatch": {
      "version": "3.1.2",
      "resolved": "https://registry.npmjs.org/minimatch/-/minimatch-3.1.2.tgz",
      "integrity": "sha512-J7p63hRiAjw1NDEww1W7i37+ByIrOWO5XQQAzZ3VOcL0PNybwpfmV/N05zFAzwQ9USyEcX6t3UO+K5aqBQOIHw==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "brace-expansion": "^1.1.7"
      },
      "engines": {
        "node": "*"
      }
    },
    "node_modules/ms": {
      "version": "2.1.3",
      "resolved": "https://registry.npmjs.org/ms/-/ms-2.1.3.tgz",
      "integrity": "sha512-6FlzubTLZG3J2a/NVCAleEhjzq5oxgHyaCU9yYXvcLsvoVaHJq/s5xXI6/XXP6tz7R9xAOtHnSO/tXtF3WRTlA==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/mz": {
      "version": "2.7.0",
      "resolved": "https://registry.npmjs.org/mz/-/mz-2.7.0.tgz",
      "integrity": "sha512-z81GNO7nnYMEhrGh9LeymoE4+Yr0Wn5McHIZMK5cfQCl+NDX08sCZgUc9/6MHni9IWuFLm1Z3HTCXu2z9fN62Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "any-promise": "^1.0.0",
        "object-assign": "^4.0.1",
        "thenify-all": "^1.0.0"
      }
    },
    "node_modules/nanoid": {
      "version": "3.3.11",
      "resolved": "https://registry.npmjs.org/nanoid/-/nanoid-3.3.11.tgz",
      "integrity": "sha512-N8SpfPUnUp1bK+PMYW8qSWdl9U+wwNWI4QKxOYDy9JAro3WMX7p2OeVRF9v+347pnakNevPmiHhNmZ2HbFA76w==",
      "dev": true,
      "funding": [
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "MIT",
      "bin": {
        "nanoid": "bin/nanoid.cjs"
      },
      "engines": {
        "node": "^10 || ^12 || ^13.7 || ^14 || >=15.0.1"
      }
    },
    "node_modules/natural-compare": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/natural-compare/-/natural-compare-1.4.0.tgz",
      "integrity": "sha512-OWND8ei3VtNC9h7V60qff3SVobHr996CTwgxubgyQYEpg290h9J0buyECNNJexkFm5sOajh5G116RYA1c8ZMSw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/next-themes": {
      "version": "0.4.6",
      "resolved": "https://registry.npmjs.org/next-themes/-/next-themes-0.4.6.tgz",
      "integrity": "sha512-pZvgD5L0IEvX5/9GWyHMf3m8BKiVQwsCMHfoFosXtXBMnaS0ZnIJ9ST4b4NqLVKDEm8QBxoNNGNaBv2JNF6XNA==",
      "license": "MIT",
      "peerDependencies": {
        "react": "^16.8 || ^17 || ^18 || ^19 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17 || ^18 || ^19 || ^19.0.0-rc"
      }
    },
    "node_modules/node-releases": {
      "version": "2.0.27",
      "resolved": "https://registry.npmjs.org/node-releases/-/node-releases-2.0.27.tgz",
      "integrity": "sha512-nmh3lCkYZ3grZvqcCH+fjmQ7X+H0OeZgP40OierEaAptX4XofMh5kwNbWh7lBduUzCcV/8kZ+NDLCwm2iorIlA==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/normalize-path": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/normalize-path/-/normalize-path-3.0.0.tgz",
      "integrity": "sha512-6eZs5Ls3WtCisHWp9S2GUy8dqkpGi4BVSz3GaqiE6ezub0512ESztXUwUB6C6IKbQkY2Pnb/mD4WYojCRwcwLA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/object-assign": {
      "version": "4.1.1",
      "resolved": "https://registry.npmjs.org/object-assign/-/object-assign-4.1.1.tgz",
      "integrity": "sha512-rJgTQnkUnH1sFw8yT6VSU3zD3sWmu6sZhIseY8VX+GRu3P6F7Fu+JNDoXfklElbLJSnc3FUQHVe4cU5hj+BcUg==",
      "license": "MIT",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/object-hash": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/object-hash/-/object-hash-3.0.0.tgz",
      "integrity": "sha512-RSn9F68PjH9HqtltsSnqYC1XXoWe9Bju5+213R98cNGttag9q9yAOTzdbsqvIa7aNm5WffBZFpWYr2aWrklWAw==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 6"
      }
    },
    "node_modules/optionator": {
      "version": "0.9.4",
      "resolved": "https://registry.npmjs.org/optionator/-/optionator-0.9.4.tgz",
      "integrity": "sha512-6IpQ7mKUxRcZNLIObR0hz7lxsapSSIYNZJwXPGeF0mTVqGKFIXj1DQcMoT22S3ROcLyY/rz0PWaWZ9ayWmad9g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "deep-is": "^0.1.3",
        "fast-levenshtein": "^2.0.6",
        "levn": "^0.4.1",
        "prelude-ls": "^1.2.1",
        "type-check": "^0.4.0",
        "word-wrap": "^1.2.5"
      },
      "engines": {
        "node": ">= 0.8.0"
      }
    },
    "node_modules/p-limit": {
      "version": "3.1.0",
      "resolved": "https://registry.npmjs.org/p-limit/-/p-limit-3.1.0.tgz",
      "integrity": "sha512-TYOanM3wGwNGsZN2cVTYPArw454xnXj5qmWF1bEoAc4+cU/ol7GVh7odevjp1FNHduHc3KZMcFduxU5Xc6uJRQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "yocto-queue": "^0.1.0"
      },
      "engines": {
        "node": ">=10"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/p-locate": {
      "version": "5.0.0",
      "resolved": "https://registry.npmjs.org/p-locate/-/p-locate-5.0.0.tgz",
      "integrity": "sha512-LaNjtRWUBY++zB5nE/NwcaoMylSPk+S+ZHNB1TzdbMJMny6dynpAGt7X/tl/QYq3TIeE6nxHppbo2LGymrG5Pw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "p-limit": "^3.0.2"
      },
      "engines": {
        "node": ">=10"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/parent-module": {
      "version": "1.0.1",
      "resolved": "https://registry.npmjs.org/parent-module/-/parent-module-1.0.1.tgz",
      "integrity": "sha512-GQ2EWRpQV8/o+Aw8YqtfZZPfNRWZYkbidE9k5rpl/hC3vtHHBfGm2Ifi6qWV+coDGkrUKZAxE3Lot5kcsRlh+g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "callsites": "^3.0.0"
      },
      "engines": {
        "node": ">=6"
      }
    },
    "node_modules/path-exists": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/path-exists/-/path-exists-4.0.0.tgz",
      "integrity": "sha512-ak9Qy5Q7jYb2Wwcey5Fpvg2KoAc/ZIhLSLOSBmRmygPsGwkVVt0fZa0qrtMz+m6tJTAHfZQ8FnmB4MG4LWy7/w==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/path-key": {
      "version": "3.1.1",
      "resolved": "https://registry.npmjs.org/path-key/-/path-key-3.1.1.tgz",
      "integrity": "sha512-ojmeN0qd+y0jszEtoY48r0Peq5dwMEkIlCOu6Q5f41lfkswXuKtYrhgoTpLnyIcHm24Uhqx+5Tqm2InSwLhE6Q==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/path-parse": {
      "version": "1.0.7",
      "resolved": "https://registry.npmjs.org/path-parse/-/path-parse-1.0.7.tgz",
      "integrity": "sha512-LDJzPVEEEPR+y48z93A0Ed0yXb8pAByGWo/k5YYdYgpY2/2EsOsksJrq7lOHxryrVOn1ejG6oAp8ahvOIQD8sw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/picocolors": {
      "version": "1.1.1",
      "resolved": "https://registry.npmjs.org/picocolors/-/picocolors-1.1.1.tgz",
      "integrity": "sha512-xceH2snhtb5M9liqDsmEw56le376mTZkEX/jEb/RxNFyegNul7eNslCXP9FDj/Lcu0X8KEyMceP2ntpaHrDEVA==",
      "dev": true,
      "license": "ISC"
    },
    "node_modules/picomatch": {
      "version": "4.0.3",
      "resolved": "https://registry.npmjs.org/picomatch/-/picomatch-4.0.3.tgz",
      "integrity": "sha512-5gTmgEY/sqK6gFXLIsQNH19lWb4ebPDLA4SdLP7dsWkIXHWlG66oPuVvXSGFPppYZz8ZDZq0dYYrbHfBCVUb1Q==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=12"
      },
      "funding": {
        "url": "https://github.com/sponsors/jonschlinkert"
      }
    },
    "node_modules/pify": {
      "version": "2.3.0",
      "resolved": "https://registry.npmjs.org/pify/-/pify-2.3.0.tgz",
      "integrity": "sha512-udgsAY+fTnvv7kI7aaxbqwWNb0AHiB0qBO89PZKPkoTmGOgdbrHDKD+0B2X4uTfJ/FT1R09r9gTsjUjNJotuog==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/pirates": {
      "version": "4.0.7",
      "resolved": "https://registry.npmjs.org/pirates/-/pirates-4.0.7.tgz",
      "integrity": "sha512-TfySrs/5nm8fQJDcBDuUng3VOUKsd7S+zqvbOTiGXHfxX4wK31ard+hoNuvkicM/2YFzlpDgABOevKSsB4G/FA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 6"
      }
    },
    "node_modules/postcss": {
      "version": "8.5.6",
      "resolved": "https://registry.npmjs.org/postcss/-/postcss-8.5.6.tgz",
      "integrity": "sha512-3Ybi1tAuwAP9s0r1UQ2J4n5Y0G05bJkpUIO0/bI9MhwmD70S5aTWbXGBwxHrelT+XM1k6dM0pk+SwNkpTRN7Pg==",
      "dev": true,
      "funding": [
        {
          "type": "opencollective",
          "url": "https://opencollective.com/postcss/"
        },
        {
          "type": "tidelift",
          "url": "https://tidelift.com/funding/github/npm/postcss"
        },
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "MIT",
      "dependencies": {
        "nanoid": "^3.3.11",
        "picocolors": "^1.1.1",
        "source-map-js": "^1.2.1"
      },
      "engines": {
        "node": "^10 || ^12 || >=14"
      }
    },
    "node_modules/postcss-import": {
      "version": "15.1.0",
      "resolved": "https://registry.npmjs.org/postcss-import/-/postcss-import-15.1.0.tgz",
      "integrity": "sha512-hpr+J05B2FVYUAXHeK1YyI267J/dDDhMU6B6civm8hSY1jYJnBXxzKDKDswzJmtLHryrjhnDjqqp/49t8FALew==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "postcss-value-parser": "^4.0.0",
        "read-cache": "^1.0.0",
        "resolve": "^1.1.7"
      },
      "engines": {
        "node": ">=14.0.0"
      },
      "peerDependencies": {
        "postcss": "^8.0.0"
      }
    },
    "node_modules/postcss-js": {
      "version": "4.1.0",
      "resolved": "https://registry.npmjs.org/postcss-js/-/postcss-js-4.1.0.tgz",
      "integrity": "sha512-oIAOTqgIo7q2EOwbhb8UalYePMvYoIeRY2YKntdpFQXNosSu3vLrniGgmH9OKs/qAkfoj5oB3le/7mINW1LCfw==",
      "dev": true,
      "funding": [
        {
          "type": "opencollective",
          "url": "https://opencollective.com/postcss/"
        },
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "MIT",
      "dependencies": {
        "camelcase-css": "^2.0.1"
      },
      "engines": {
        "node": "^12 || ^14 || >= 16"
      },
      "peerDependencies": {
        "postcss": "^8.4.21"
      }
    },
    "node_modules/postcss-load-config": {
      "version": "6.0.1",
      "resolved": "https://registry.npmjs.org/postcss-load-config/-/postcss-load-config-6.0.1.tgz",
      "integrity": "sha512-oPtTM4oerL+UXmx+93ytZVN82RrlY/wPUV8IeDxFrzIjXOLF1pN+EmKPLbubvKHT2HC20xXsCAH2Z+CKV6Oz/g==",
      "dev": true,
      "funding": [
        {
          "type": "opencollective",
          "url": "https://opencollective.com/postcss/"
        },
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "MIT",
      "dependencies": {
        "lilconfig": "^3.1.1"
      },
      "engines": {
        "node": ">= 18"
      },
      "peerDependencies": {
        "jiti": ">=1.21.0",
        "postcss": ">=8.0.9",
        "tsx": "^4.8.1",
        "yaml": "^2.4.2"
      },
      "peerDependenciesMeta": {
        "jiti": {
          "optional": true
        },
        "postcss": {
          "optional": true
        },
        "tsx": {
          "optional": true
        },
        "yaml": {
          "optional": true
        }
      }
    },
    "node_modules/postcss-nested": {
      "version": "6.2.0",
      "resolved": "https://registry.npmjs.org/postcss-nested/-/postcss-nested-6.2.0.tgz",
      "integrity": "sha512-HQbt28KulC5AJzG+cZtj9kvKB93CFCdLvog1WFLf1D+xmMvPGlBstkpTEZfK5+AN9hfJocyBFCNiqyS48bpgzQ==",
      "dev": true,
      "funding": [
        {
          "type": "opencollective",
          "url": "https://opencollective.com/postcss/"
        },
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "MIT",
      "dependencies": {
        "postcss-selector-parser": "^6.1.1"
      },
      "engines": {
        "node": ">=12.0"
      },
      "peerDependencies": {
        "postcss": "^8.2.14"
      }
    },
    "node_modules/postcss-selector-parser": {
      "version": "6.1.2",
      "resolved": "https://registry.npmjs.org/postcss-selector-parser/-/postcss-selector-parser-6.1.2.tgz",
      "integrity": "sha512-Q8qQfPiZ+THO/3ZrOrO0cJJKfpYCagtMUkXbnEfmgUjwXg6z/WBeOyS9APBBPCTSiDV+s4SwQGu8yFsiMRIudg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "cssesc": "^3.0.0",
        "util-deprecate": "^1.0.2"
      },
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/postcss-value-parser": {
      "version": "4.2.0",
      "resolved": "https://registry.npmjs.org/postcss-value-parser/-/postcss-value-parser-4.2.0.tgz",
      "integrity": "sha512-1NNCs6uurfkVbeXG4S8JFT9t19m45ICnif8zWLd5oPSZ50QnwMfK+H3jv408d4jw/7Bttv5axS5IiHoLaVNHeQ==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/prelude-ls": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/prelude-ls/-/prelude-ls-1.2.1.tgz",
      "integrity": "sha512-vkcDPrRZo1QZLbn5RLGPpg/WmIQ65qoWWhcGKf/b5eplkkarX0m9z8ppCat4mlOqUsWpyNuYgO3VRyrYHSzX5g==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 0.8.0"
      }
    },
    "node_modules/prop-types": {
      "version": "15.8.1",
      "resolved": "https://registry.npmjs.org/prop-types/-/prop-types-15.8.1.tgz",
      "integrity": "sha512-oj87CgZICdulUohogVAR7AjlC0327U4el4L6eAvOqCeudMDVU0NThNaV+b9Df4dXgSP1gXMTnPdhfe/2qDH5cg==",
      "license": "MIT",
      "dependencies": {
        "loose-envify": "^1.4.0",
        "object-assign": "^4.1.1",
        "react-is": "^16.13.1"
      }
    },
    "node_modules/prop-types/node_modules/react-is": {
      "version": "16.13.1",
      "resolved": "https://registry.npmjs.org/react-is/-/react-is-16.13.1.tgz",
      "integrity": "sha512-24e6ynE2H+OKt4kqsOvNd8kBpV65zoxbA4BVsEOB3ARVWQki/DHzaUoC5KuON/BiccDaCCTZBuOcfZs70kR8bQ==",
      "license": "MIT"
    },
    "node_modules/punycode": {
      "version": "2.3.1",
      "resolved": "https://registry.npmjs.org/punycode/-/punycode-2.3.1.tgz",
      "integrity": "sha512-vYt7UD1U9Wg6138shLtLOvdAu+8DsC/ilFtEVHcH+wydcSpNE20AfSOduf6MkRFahL5FY7X1oU7nKVZFtfq8Fg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=6"
      }
    },
    "node_modules/queue-microtask": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/queue-microtask/-/queue-microtask-1.2.3.tgz",
      "integrity": "sha512-NuaNSa6flKT5JaSYQzJok04JzTL1CA6aGhv5rfLW3PgqA+M2ChpZQnAC8h8i4ZFkBS8X5RqkDBHA7r4hej3K9A==",
      "dev": true,
      "funding": [
        {
          "type": "github",
          "url": "https://github.com/sponsors/feross"
        },
        {
          "type": "patreon",
          "url": "https://www.patreon.com/feross"
        },
        {
          "type": "consulting",
          "url": "https://feross.org/support"
        }
      ],
      "license": "MIT"
    },
    "node_modules/react": {
      "version": "19.2.3",
      "resolved": "https://registry.npmjs.org/react/-/react-19.2.3.tgz",
      "integrity": "sha512-Ku/hhYbVjOQnXDZFv2+RibmLFGwFdeeKHFcOTlrt7xplBnya5OGn/hIRDsqDiSUcfORsDC7MPxwork8jBwsIWA==",
      "license": "MIT",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/react-day-picker": {
      "version": "9.13.0",
      "resolved": "https://registry.npmjs.org/react-day-picker/-/react-day-picker-9.13.0.tgz",
      "integrity": "sha512-euzj5Hlq+lOHqI53NiuNhCP8HWgsPf/bBAVijR50hNaY1XwjKjShAnIe8jm8RD2W9IJUvihDIZ+KrmqfFzNhFQ==",
      "license": "MIT",
      "dependencies": {
        "@date-fns/tz": "^1.4.1",
        "date-fns": "^4.1.0",
        "date-fns-jalali": "^4.1.0-0"
      },
      "engines": {
        "node": ">=18"
      },
      "funding": {
        "type": "individual",
        "url": "https://github.com/sponsors/gpbl"
      },
      "peerDependencies": {
        "react": ">=16.8.0"
      }
    },
    "node_modules/react-dom": {
      "version": "19.2.3",
      "resolved": "https://registry.npmjs.org/react-dom/-/react-dom-19.2.3.tgz",
      "integrity": "sha512-yELu4WmLPw5Mr/lmeEpox5rw3RETacE++JgHqQzd2dg+YbJuat3jH4ingc+WPZhxaoFzdv9y33G+F7Nl5O0GBg==",
      "license": "MIT",
      "dependencies": {
        "scheduler": "^0.27.0"
      },
      "peerDependencies": {
        "react": "^19.2.3"
      }
    },
    "node_modules/react-hook-form": {
      "version": "7.70.0",
      "resolved": "https://registry.npmjs.org/react-hook-form/-/react-hook-form-7.70.0.tgz",
      "integrity": "sha512-COOMajS4FI3Wuwrs3GPpi/Jeef/5W1DRR84Yl5/ShlT3dKVFUfoGiEZ/QE6Uw8P4T2/CLJdcTVYKvWBMQTEpvw==",
      "license": "MIT",
      "engines": {
        "node": ">=18.0.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/react-hook-form"
      },
      "peerDependencies": {
        "react": "^16.8.0 || ^17 || ^18 || ^19"
      }
    },
    "node_modules/react-is": {
      "version": "18.3.1",
      "resolved": "https://registry.npmjs.org/react-is/-/react-is-18.3.1.tgz",
      "integrity": "sha512-/LLMVyas0ljjAtoYiPqYiL8VWXzUUdThrmU5+n20DZv+a+ClRoevUzw5JxU+Ieh5/c87ytoTBV9G1FiKfNJdmg==",
      "license": "MIT"
    },
    "node_modules/react-refresh": {
      "version": "0.18.0",
      "resolved": "https://registry.npmjs.org/react-refresh/-/react-refresh-0.18.0.tgz",
      "integrity": "sha512-QgT5//D3jfjJb6Gsjxv0Slpj23ip+HtOpnNgnb2S5zU3CB26G/IDPGoy4RJB42wzFE46DRsstbW6tKHoKbhAxw==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/react-remove-scroll": {
      "version": "2.7.2",
      "resolved": "https://registry.npmjs.org/react-remove-scroll/-/react-remove-scroll-2.7.2.tgz",
      "integrity": "sha512-Iqb9NjCCTt6Hf+vOdNIZGdTiH1QSqr27H/Ek9sv/a97gfueI/5h1s3yRi1nngzMUaOOToin5dI1dXKdXiF+u0Q==",
      "license": "MIT",
      "dependencies": {
        "react-remove-scroll-bar": "^2.3.7",
        "react-style-singleton": "^2.2.3",
        "tslib": "^2.1.0",
        "use-callback-ref": "^1.3.3",
        "use-sidecar": "^1.1.3"
      },
      "engines": {
        "node": ">=10"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8.0 || ^17.0.0 || ^18.0.0 || ^19.0.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/react-remove-scroll-bar": {
      "version": "2.3.8",
      "resolved": "https://registry.npmjs.org/react-remove-scroll-bar/-/react-remove-scroll-bar-2.3.8.tgz",
      "integrity": "sha512-9r+yi9+mgU33AKcj6IbT9oRCO78WriSj6t/cF8DWBZJ9aOGPOTEDvdUDz1FwKim7QXWwmHqtdHnRJfhAxEG46Q==",
      "license": "MIT",
      "dependencies": {
        "react-style-singleton": "^2.2.2",
        "tslib": "^2.0.0"
      },
      "engines": {
        "node": ">=10"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8.0 || ^17.0.0 || ^18.0.0 || ^19.0.0"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/react-resizable-panels": {
      "version": "4.2.2",
      "resolved": "https://registry.npmjs.org/react-resizable-panels/-/react-resizable-panels-4.2.2.tgz",
      "integrity": "sha512-BxDTFHxDCyCRPK54X5hpnhoLZbBslUrTTelQDRHo4107FXODjPSTqEWOPlFxE/ho0Vw4JrsRgaWdx6GIK073XA==",
      "license": "MIT",
      "peerDependencies": {
        "react": "^18.0.0 || ^19.0.0",
        "react-dom": "^18.0.0 || ^19.0.0"
      }
    },
    "node_modules/react-router": {
      "version": "7.15.1",
      "resolved": "https://registry.npmmirror.com/react-router/-/react-router-7.15.1.tgz",
      "integrity": "sha512-R8rl9HhgikFYoPJymnUtPXWbnDb3oget6lQnfIoupbt61aT9aOhRkDsY2XRhZRyX1Z/8a5sL74fXmFNm3NRK5A==",
      "license": "MIT",
      "dependencies": {
        "cookie": "^1.0.1",
        "set-cookie-parser": "^2.6.0"
      },
      "engines": {
        "node": ">=20.0.0"
      },
      "peerDependencies": {
        "react": ">=18",
        "react-dom": ">=18"
      },
      "peerDependenciesMeta": {
        "react-dom": {
          "optional": true
        }
      }
    },
    "node_modules/react-router-dom": {
      "version": "7.15.1",
      "resolved": "https://registry.npmmirror.com/react-router-dom/-/react-router-dom-7.15.1.tgz",
      "integrity": "sha512-AzF62gjY6U9rkMq4RfP/r2EVtQ7DMfNMjyOp/flLTCrtRylLiK4wT4pSq6O8rOXZ2eXdZYJPEYe+ifomiv+Igg==",
      "license": "MIT",
      "dependencies": {
        "react-router": "7.15.1"
      },
      "engines": {
        "node": ">=20.0.0"
      },
      "peerDependencies": {
        "react": ">=18",
        "react-dom": ">=18"
      }
    },
    "node_modules/react-smooth": {
      "version": "4.0.4",
      "resolved": "https://registry.npmjs.org/react-smooth/-/react-smooth-4.0.4.tgz",
      "integrity": "sha512-gnGKTpYwqL0Iii09gHobNolvX4Kiq4PKx6eWBCYYix+8cdw+cGo3do906l1NBPKkSWx1DghC1dlWG9L2uGd61Q==",
      "license": "MIT",
      "dependencies": {
        "fast-equals": "^5.0.1",
        "prop-types": "^15.8.1",
        "react-transition-group": "^4.4.5"
      },
      "peerDependencies": {
        "react": "^16.8.0 || ^17.0.0 || ^18.0.0 || ^19.0.0",
        "react-dom": "^16.8.0 || ^17.0.0 || ^18.0.0 || ^19.0.0"
      }
    },
    "node_modules/react-style-singleton": {
      "version": "2.2.3",
      "resolved": "https://registry.npmjs.org/react-style-singleton/-/react-style-singleton-2.2.3.tgz",
      "integrity": "sha512-b6jSvxvVnyptAiLjbkWLE/lOnR4lfTtDAl+eUC7RZy+QQWc6wRzIV2CE6xBuMmDxc2qIihtDCZD5NPOFl7fRBQ==",
      "license": "MIT",
      "dependencies": {
        "get-nonce": "^1.0.0",
        "tslib": "^2.0.0"
      },
      "engines": {
        "node": ">=10"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8.0 || ^17.0.0 || ^18.0.0 || ^19.0.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/react-transition-group": {
      "version": "4.4.5",
      "resolved": "https://registry.npmjs.org/react-transition-group/-/react-transition-group-4.4.5.tgz",
      "integrity": "sha512-pZcd1MCJoiKiBR2NRxeCRg13uCXbydPnmB4EOeRrY7480qNWO8IIgQG6zlDkm6uRMsURXPuKq0GWtiM59a5Q6g==",
      "license": "BSD-3-Clause",
      "dependencies": {
        "@babel/runtime": "^7.5.5",
        "dom-helpers": "^5.0.1",
        "loose-envify": "^1.4.0",
        "prop-types": "^15.6.2"
      },
      "peerDependencies": {
        "react": ">=16.6.0",
        "react-dom": ">=16.6.0"
      }
    },
    "node_modules/read-cache": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/read-cache/-/read-cache-1.0.0.tgz",
      "integrity": "sha512-Owdv/Ft7IjOgm/i0xvNDZ1LrRANRfew4b2prF3OWMQLxLfu3bS8FVhCsrSCMK4lR56Y9ya+AThoTpDCTxCmpRA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "pify": "^2.3.0"
      }
    },
    "node_modules/readdirp": {
      "version": "3.6.0",
      "resolved": "https://registry.npmjs.org/readdirp/-/readdirp-3.6.0.tgz",
      "integrity": "sha512-hOS089on8RduqdbhvQ5Z37A0ESjsqz6qnRcffsMU3495FuTdqSm+7bhJ29JvIOsBDEEnan5DPu9t3To9VRlMzA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "picomatch": "^2.2.1"
      },
      "engines": {
        "node": ">=8.10.0"
      }
    },
    "node_modules/readdirp/node_modules/picomatch": {
      "version": "2.3.1",
      "resolved": "https://registry.npmjs.org/picomatch/-/picomatch-2.3.1.tgz",
      "integrity": "sha512-JU3teHTNjmE2VCGFzuY8EXzCDVwEqB2a8fsIvwaStHhAWJEeVd1o1QD80CU6+ZdEXXSLbSsuLwJjkCBWqRQUVA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8.6"
      },
      "funding": {
        "url": "https://github.com/sponsors/jonschlinkert"
      }
    },
    "node_modules/recharts": {
      "version": "2.15.4",
      "resolved": "https://registry.npmjs.org/recharts/-/recharts-2.15.4.tgz",
      "integrity": "sha512-UT/q6fwS3c1dHbXv2uFgYJ9BMFHu3fwnd7AYZaEQhXuYQ4hgsxLvsUXzGdKeZrW5xopzDCvuA2N41WJ88I7zIw==",
      "license": "MIT",
      "dependencies": {
        "clsx": "^2.0.0",
        "eventemitter3": "^4.0.1",
        "lodash": "^4.17.21",
        "react-is": "^18.3.1",
        "react-smooth": "^4.0.4",
        "recharts-scale": "^0.4.4",
        "tiny-invariant": "^1.3.1",
        "victory-vendor": "^36.6.8"
      },
      "engines": {
        "node": ">=14"
      },
      "peerDependencies": {
        "react": "^16.0.0 || ^17.0.0 || ^18.0.0 || ^19.0.0",
        "react-dom": "^16.0.0 || ^17.0.0 || ^18.0.0 || ^19.0.0"
      }
    },
    "node_modules/recharts-scale": {
      "version": "0.4.5",
      "resolved": "https://registry.npmjs.org/recharts-scale/-/recharts-scale-0.4.5.tgz",
      "integrity": "sha512-kivNFO+0OcUNu7jQquLXAxz1FIwZj8nrj+YkOKc5694NbjCvcT6aSZiIzNzd2Kul4o4rTto8QVR9lMNtxD4G1w==",
      "license": "MIT",
      "dependencies": {
        "decimal.js-light": "^2.4.1"
      }
    },
    "node_modules/regenerate": {
      "version": "1.4.2",
      "resolved": "https://registry.npmmirror.com/regenerate/-/regenerate-1.4.2.tgz",
      "integrity": "sha512-zrceR/XhGYU/d/opr2EKO7aRHUeiBI8qjtfHqADTwZd6Szfy16la6kqD0MIUs5z5hx6AaKa+PixpPrR289+I0A==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/regenerate-unicode-properties": {
      "version": "10.2.2",
      "resolved": "https://registry.npmmirror.com/regenerate-unicode-properties/-/regenerate-unicode-properties-10.2.2.tgz",
      "integrity": "sha512-m03P+zhBeQd1RGnYxrGyDAPpWX/epKirLrp8e3qevZdVkKtnCrjjWczIbYc8+xd6vcTStVlqfycTx1KR4LOr0g==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "regenerate": "^1.4.2"
      },
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/regexpu-core": {
      "version": "6.4.0",
      "resolved": "https://registry.npmmirror.com/regexpu-core/-/regexpu-core-6.4.0.tgz",
      "integrity": "sha512-0ghuzq67LI9bLXpOX/ISfve/Mq33a4aFRzoQYhnnok1JOFpmE/A2TBGkNVenOGEeSBCjIiWcc6MVOG5HEQv0sA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "regenerate": "^1.4.2",
        "regenerate-unicode-properties": "^10.2.2",
        "regjsgen": "^0.8.0",
        "regjsparser": "^0.13.0",
        "unicode-match-property-ecmascript": "^2.0.0",
        "unicode-match-property-value-ecmascript": "^2.2.1"
      },
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/regjsgen": {
      "version": "0.8.0",
      "resolved": "https://registry.npmmirror.com/regjsgen/-/regjsgen-0.8.0.tgz",
      "integrity": "sha512-RvwtGe3d7LvWiDQXeQw8p5asZUmfU1G/l6WbUXeHta7Y2PEIvBTwH6E2EfmYUK8pxcxEdEmaomqyp0vZZ7C+3Q==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/regjsparser": {
      "version": "0.13.1",
      "resolved": "https://registry.npmmirror.com/regjsparser/-/regjsparser-0.13.1.tgz",
      "integrity": "sha512-dLsljMd9sqwRkby8zhO1gSg3PnJIBFid8f4CQj/sXx+7cKx+E7u0PKhZ+U4wmhx7EfmtvnA318oVaIkAB1lRJw==",
      "dev": true,
      "license": "BSD-2-Clause",
      "dependencies": {
        "jsesc": "~3.1.0"
      },
      "bin": {
        "regjsparser": "bin/parser"
      }
    },
    "node_modules/resolve": {
      "version": "1.22.11",
      "resolved": "https://registry.npmjs.org/resolve/-/resolve-1.22.11.tgz",
      "integrity": "sha512-RfqAvLnMl313r7c9oclB1HhUEAezcpLjz95wFH4LVuhk9JF/r22qmVP9AMmOU4vMX7Q8pN8jwNg/CSpdFnMjTQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "is-core-module": "^2.16.1",
        "path-parse": "^1.0.7",
        "supports-preserve-symlinks-flag": "^1.0.0"
      },
      "bin": {
        "resolve": "bin/resolve"
      },
      "engines": {
        "node": ">= 0.4"
      },
      "funding": {
        "url": "https://github.com/sponsors/ljharb"
      }
    },
    "node_modules/resolve-from": {
      "version": "4.0.0",
      "resolved": "https://registry.npmjs.org/resolve-from/-/resolve-from-4.0.0.tgz",
      "integrity": "sha512-pb/MYmXstAkysRFx8piNI1tGFNQIFA3vkE3Gq4EuA1dF6gHp/+vgZqsCGJapvy8N3Q+4o7FwvquPJcnZ7RYy4g==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/reusify": {
      "version": "1.1.0",
      "resolved": "https://registry.npmjs.org/reusify/-/reusify-1.1.0.tgz",
      "integrity": "sha512-g6QUff04oZpHs0eG5p83rFLhHeV00ug/Yf9nZM6fLeUrPguBTkTQOdpAWWspMh55TZfVQDPaN3NQJfbVRAxdIw==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "iojs": ">=1.0.0",
        "node": ">=0.10.0"
      }
    },
    "node_modules/rollup": {
      "version": "4.55.1",
      "resolved": "https://registry.npmjs.org/rollup/-/rollup-4.55.1.tgz",
      "integrity": "sha512-wDv/Ht1BNHB4upNbK74s9usvl7hObDnvVzknxqY/E/O3X6rW1U1rV1aENEfJ54eFZDTNo7zv1f5N4edCluH7+A==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@types/estree": "1.0.8"
      },
      "bin": {
        "rollup": "dist/bin/rollup"
      },
      "engines": {
        "node": ">=18.0.0",
        "npm": ">=8.0.0"
      },
      "optionalDependencies": {
        "@rollup/rollup-android-arm-eabi": "4.55.1",
        "@rollup/rollup-android-arm64": "4.55.1",
        "@rollup/rollup-darwin-arm64": "4.55.1",
        "@rollup/rollup-darwin-x64": "4.55.1",
        "@rollup/rollup-freebsd-arm64": "4.55.1",
        "@rollup/rollup-freebsd-x64": "4.55.1",
        "@rollup/rollup-linux-arm-gnueabihf": "4.55.1",
        "@rollup/rollup-linux-arm-musleabihf": "4.55.1",
        "@rollup/rollup-linux-arm64-gnu": "4.55.1",
        "@rollup/rollup-linux-arm64-musl": "4.55.1",
        "@rollup/rollup-linux-loong64-gnu": "4.55.1",
        "@rollup/rollup-linux-loong64-musl": "4.55.1",
        "@rollup/rollup-linux-ppc64-gnu": "4.55.1",
        "@rollup/rollup-linux-ppc64-musl": "4.55.1",
        "@rollup/rollup-linux-riscv64-gnu": "4.55.1",
        "@rollup/rollup-linux-riscv64-musl": "4.55.1",
        "@rollup/rollup-linux-s390x-gnu": "4.55.1",
        "@rollup/rollup-linux-x64-gnu": "4.55.1",
        "@rollup/rollup-linux-x64-musl": "4.55.1",
        "@rollup/rollup-openbsd-x64": "4.55.1",
        "@rollup/rollup-openharmony-arm64": "4.55.1",
        "@rollup/rollup-win32-arm64-msvc": "4.55.1",
        "@rollup/rollup-win32-ia32-msvc": "4.55.1",
        "@rollup/rollup-win32-x64-gnu": "4.55.1",
        "@rollup/rollup-win32-x64-msvc": "4.55.1",
        "fsevents": "~2.3.2"
      }
    },
    "node_modules/run-parallel": {
      "version": "1.2.0",
      "resolved": "https://registry.npmjs.org/run-parallel/-/run-parallel-1.2.0.tgz",
      "integrity": "sha512-5l4VyZR86LZ/lDxZTR6jqL8AFE2S0IFLMP26AbjsLVADxHdhB/c0GUsH+y39UfCi3dzz8OlQuPmnaJOMoDHQBA==",
      "dev": true,
      "funding": [
        {
          "type": "github",
          "url": "https://github.com/sponsors/feross"
        },
        {
          "type": "patreon",
          "url": "https://www.patreon.com/feross"
        },
        {
          "type": "consulting",
          "url": "https://feross.org/support"
        }
      ],
      "license": "MIT",
      "dependencies": {
        "queue-microtask": "^1.2.2"
      }
    },
    "node_modules/scheduler": {
      "version": "0.27.0",
      "resolved": "https://registry.npmjs.org/scheduler/-/scheduler-0.27.0.tgz",
      "integrity": "sha512-eNv+WrVbKu1f3vbYJT/xtiF5syA5HPIMtf9IgY/nKg0sWqzAUEvqY/xm7OcZc/qafLx/iO9FgOmeSAp4v5ti/Q==",
      "license": "MIT"
    },
    "node_modules/semver": {
      "version": "6.3.1",
      "resolved": "https://registry.npmjs.org/semver/-/semver-6.3.1.tgz",
      "integrity": "sha512-BR7VvDCVHO+q2xBEWskxS6DJE1qRnb7DxzUrogb71CWoSficBxYsiAGd+Kl0mmq/MprG9yArRkyrQxTO6XjMzA==",
      "dev": true,
      "license": "ISC",
      "bin": {
        "semver": "bin/semver.js"
      }
    },
    "node_modules/set-cookie-parser": {
      "version": "2.7.2",
      "resolved": "https://registry.npmmirror.com/set-cookie-parser/-/set-cookie-parser-2.7.2.tgz",
      "integrity": "sha512-oeM1lpU/UvhTxw+g3cIfxXHyJRc/uidd3yK1P242gzHds0udQBYzs3y8j4gCCW+ZJ7ad0yctld8RYO+bdurlvw==",
      "license": "MIT"
    },
    "node_modules/shebang-command": {
      "version": "2.0.0",
      "resolved": "https://registry.npmjs.org/shebang-command/-/shebang-command-2.0.0.tgz",
      "integrity": "sha512-kHxr2zZpYtdmrN1qDjrrX/Z1rR1kG8Dx+gkpK1G4eXmvXswmcE1hTWBWYUzlraYw1/yZp6YuDY77YtvbN0dmDA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "shebang-regex": "^3.0.0"
      },
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/shebang-regex": {
      "version": "3.0.0",
      "resolved": "https://registry.npmjs.org/shebang-regex/-/shebang-regex-3.0.0.tgz",
      "integrity": "sha512-7++dFhtcx3353uBaq8DDR4NuxBetBzC7ZQOhmTQInHEd6bSrXdiEyzCvG07Z44UYdLShWUyXt5M/yhz8ekcb1A==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/sonner": {
      "version": "2.0.7",
      "resolved": "https://registry.npmjs.org/sonner/-/sonner-2.0.7.tgz",
      "integrity": "sha512-W6ZN4p58k8aDKA4XPcx2hpIQXBRAgyiWVkYhT7CvK6D3iAu7xjvVyhQHg2/iaKJZ1XVJ4r7XuwGL+WGEK37i9w==",
      "license": "MIT",
      "peerDependencies": {
        "react": "^18.0.0 || ^19.0.0 || ^19.0.0-rc",
        "react-dom": "^18.0.0 || ^19.0.0 || ^19.0.0-rc"
      }
    },
    "node_modules/source-map-js": {
      "version": "1.2.1",
      "resolved": "https://registry.npmjs.org/source-map-js/-/source-map-js-1.2.1.tgz",
      "integrity": "sha512-UXWMKhLOwVKb728IUtQPXxfYU+usdybtUrK/8uGE8CQMvrhOpwvzDBwj0QhSL7MQc7vIsISBG8VQ8+IDQxpfQA==",
      "dev": true,
      "license": "BSD-3-Clause",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/strip-json-comments": {
      "version": "3.1.1",
      "resolved": "https://registry.npmjs.org/strip-json-comments/-/strip-json-comments-3.1.1.tgz",
      "integrity": "sha512-6fPc+R4ihwqP6N/aIv2f1gMH8lOVtWQHoqC4yK6oSDVVocumAsfCqjkXnqiYMhmMwS/mEHLp7Vehlt3ql6lEig==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=8"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/sucrase": {
      "version": "3.35.1",
      "resolved": "https://registry.npmjs.org/sucrase/-/sucrase-3.35.1.tgz",
      "integrity": "sha512-DhuTmvZWux4H1UOnWMB3sk0sbaCVOoQZjv8u1rDoTV0HTdGem9hkAZtl4JZy8P2z4Bg0nT+YMeOFyVr4zcG5Tw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@jridgewell/gen-mapping": "^0.3.2",
        "commander": "^4.0.0",
        "lines-and-columns": "^1.1.6",
        "mz": "^2.7.0",
        "pirates": "^4.0.1",
        "tinyglobby": "^0.2.11",
        "ts-interface-checker": "^0.1.9"
      },
      "bin": {
        "sucrase": "bin/sucrase",
        "sucrase-node": "bin/sucrase-node"
      },
      "engines": {
        "node": ">=16 || 14 >=14.17"
      }
    },
    "node_modules/supports-color": {
      "version": "7.2.0",
      "resolved": "https://registry.npmjs.org/supports-color/-/supports-color-7.2.0.tgz",
      "integrity": "sha512-qpCAvRl9stuOHveKsn7HncJRvv501qIacKzQlO/+Lwxc9+0q2wLyv4Dfvt80/DPn2pqOBsJdDiogXGR9+OvwRw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "has-flag": "^4.0.0"
      },
      "engines": {
        "node": ">=8"
      }
    },
    "node_modules/supports-preserve-symlinks-flag": {
      "version": "1.0.0",
      "resolved": "https://registry.npmjs.org/supports-preserve-symlinks-flag/-/supports-preserve-symlinks-flag-1.0.0.tgz",
      "integrity": "sha512-ot0WnXS9fgdkgIcePe6RHNk1WA8+muPa6cSjeR3V8K27q9BB1rTE3R1p7Hv0z1ZyAc8s6Vvv8DIyWf681MAt0w==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">= 0.4"
      },
      "funding": {
        "url": "https://github.com/sponsors/ljharb"
      }
    },
    "node_modules/tailwind-merge": {
      "version": "3.4.0",
      "resolved": "https://registry.npmjs.org/tailwind-merge/-/tailwind-merge-3.4.0.tgz",
      "integrity": "sha512-uSaO4gnW+b3Y2aWoWfFpX62vn2sR3skfhbjsEnaBI81WD1wBLlHZe5sWf0AqjksNdYTbGBEd0UasQMT3SNV15g==",
      "license": "MIT",
      "funding": {
        "type": "github",
        "url": "https://github.com/sponsors/dcastil"
      }
    },
    "node_modules/tailwindcss": {
      "version": "3.4.19",
      "resolved": "https://registry.npmjs.org/tailwindcss/-/tailwindcss-3.4.19.tgz",
      "integrity": "sha512-3ofp+LL8E+pK/JuPLPggVAIaEuhvIz4qNcf3nA1Xn2o/7fb7s/TYpHhwGDv1ZU3PkBluUVaF8PyCHcm48cKLWQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@alloc/quick-lru": "^5.2.0",
        "arg": "^5.0.2",
        "chokidar": "^3.6.0",
        "didyoumean": "^1.2.2",
        "dlv": "^1.1.3",
        "fast-glob": "^3.3.2",
        "glob-parent": "^6.0.2",
        "is-glob": "^4.0.3",
        "jiti": "^1.21.7",
        "lilconfig": "^3.1.3",
        "micromatch": "^4.0.8",
        "normalize-path": "^3.0.0",
        "object-hash": "^3.0.0",
        "picocolors": "^1.1.1",
        "postcss": "^8.4.47",
        "postcss-import": "^15.1.0",
        "postcss-js": "^4.0.1",
        "postcss-load-config": "^4.0.2 || ^5.0 || ^6.0",
        "postcss-nested": "^6.2.0",
        "postcss-selector-parser": "^6.1.2",
        "resolve": "^1.22.8",
        "sucrase": "^3.35.0"
      },
      "bin": {
        "tailwind": "lib/cli.js",
        "tailwindcss": "lib/cli.js"
      },
      "engines": {
        "node": ">=14.0.0"
      }
    },
    "node_modules/tailwindcss-animate": {
      "version": "1.0.7",
      "resolved": "https://registry.npmjs.org/tailwindcss-animate/-/tailwindcss-animate-1.0.7.tgz",
      "integrity": "sha512-bl6mpH3T7I3UFxuvDEXLxy/VuFxBk5bbzplh7tXI68mwMokNYd1t9qPBHlnyTwfa4JGC4zP516I1hYYtQ/vspA==",
      "dev": true,
      "license": "MIT",
      "peerDependencies": {
        "tailwindcss": ">=3.0.0 || insiders"
      }
    },
    "node_modules/thenify": {
      "version": "3.3.1",
      "resolved": "https://registry.npmjs.org/thenify/-/thenify-3.3.1.tgz",
      "integrity": "sha512-RVZSIV5IG10Hk3enotrhvz0T9em6cyHBLkH/YAZuKqd8hRkKhSfCGIcP2KUY0EPxndzANBmNllzWPwak+bheSw==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "any-promise": "^1.0.0"
      }
    },
    "node_modules/thenify-all": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/thenify-all/-/thenify-all-1.6.0.tgz",
      "integrity": "sha512-RNxQH/qI8/t3thXJDwcstUO4zeqo64+Uy/+sNVRBx4Xn2OX+OZ9oP+iJnNFqplFra2ZUVeKCSa2oVWi3T4uVmA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "thenify": ">= 3.1.0 < 4"
      },
      "engines": {
        "node": ">=0.8"
      }
    },
    "node_modules/three": {
      "version": "0.184.0",
      "resolved": "https://registry.npmmirror.com/three/-/three-0.184.0.tgz",
      "integrity": "sha512-wtTRjG92pM5eUg/KuUnHsqSAlPM296brTOcLgMRqEeylYTh/CdtvKUvCyyCQTzFuStieWxvZb8mVTMvdPyUpxg==",
      "license": "MIT"
    },
    "node_modules/tiny-invariant": {
      "version": "1.3.3",
      "resolved": "https://registry.npmjs.org/tiny-invariant/-/tiny-invariant-1.3.3.tgz",
      "integrity": "sha512-+FbBPE1o9QAYvviau/qC5SE3caw21q3xkvWKBtja5vgqOWIHHJ3ioaq1VPfn/Szqctz2bU/oYeKd9/z5BL+PVg==",
      "license": "MIT"
    },
    "node_modules/tinyglobby": {
      "version": "0.2.15",
      "resolved": "https://registry.npmjs.org/tinyglobby/-/tinyglobby-0.2.15.tgz",
      "integrity": "sha512-j2Zq4NyQYG5XMST4cbs02Ak8iJUdxRM0XI5QyxXuZOzKOINmWurp3smXu3y5wDcJrptwpSjgXHzIQxR0omXljQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "fdir": "^6.5.0",
        "picomatch": "^4.0.3"
      },
      "engines": {
        "node": ">=12.0.0"
      },
      "funding": {
        "url": "https://github.com/sponsors/SuperchupuDev"
      }
    },
    "node_modules/to-regex-range": {
      "version": "5.0.1",
      "resolved": "https://registry.npmjs.org/to-regex-range/-/to-regex-range-5.0.1.tgz",
      "integrity": "sha512-65P7iz6X5yEr1cwcgvQxbbIw7Uk3gOy5dIdtZ4rDveLqhrdJP+Li/Hx6tyK0NEb+2GCyneCMJiGqrADCSNk8sQ==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "is-number": "^7.0.0"
      },
      "engines": {
        "node": ">=8.0"
      }
    },
    "node_modules/ts-api-utils": {
      "version": "2.4.0",
      "resolved": "https://registry.npmjs.org/ts-api-utils/-/ts-api-utils-2.4.0.tgz",
      "integrity": "sha512-3TaVTaAv2gTiMB35i3FiGJaRfwb3Pyn/j3m/bfAvGe8FB7CF6u+LMYqYlDh7reQf7UNvoTvdfAqHGmPGOSsPmA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=18.12"
      },
      "peerDependencies": {
        "typescript": ">=4.8.4"
      }
    },
    "node_modules/ts-interface-checker": {
      "version": "0.1.13",
      "resolved": "https://registry.npmjs.org/ts-interface-checker/-/ts-interface-checker-0.1.13.tgz",
      "integrity": "sha512-Y/arvbn+rrz3JCKl9C4kVNfTfSm2/mEp5FSz5EsZSANGPSlQrpRI5M4PKF+mJnE52jOO90PnPSc3Ur3bTQw0gA==",
      "dev": true,
      "license": "Apache-2.0"
    },
    "node_modules/tslib": {
      "version": "2.8.1",
      "resolved": "https://registry.npmjs.org/tslib/-/tslib-2.8.1.tgz",
      "integrity": "sha512-oJFu94HQb+KVduSUQL7wnpmqnfmLsOA/nAh6b6EH0wCEoK0/mPeXU6c3wKDV83MkOuHPRHtSXKKU99IBazS/2w==",
      "license": "0BSD"
    },
    "node_modules/tw-animate-css": {
      "version": "1.4.0",
      "resolved": "https://registry.npmjs.org/tw-animate-css/-/tw-animate-css-1.4.0.tgz",
      "integrity": "sha512-7bziOlRqH0hJx80h/3mbicLW7o8qLsH5+RaLR2t+OHM3D0JlWGODQKQ4cxbK7WlvmUxpcj6Kgu6EKqjrGFe3QQ==",
      "dev": true,
      "license": "MIT",
      "funding": {
        "url": "https://github.com/sponsors/Wombosvideo"
      }
    },
    "node_modules/type-check": {
      "version": "0.4.0",
      "resolved": "https://registry.npmjs.org/type-check/-/type-check-0.4.0.tgz",
      "integrity": "sha512-XleUoc9uwGXqjWwXaUTZAmzMcFZ5858QA2vvx1Ur5xIcixXIP+8LnFDgRplU30us6teqdlskFfu+ae4K79Ooew==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "prelude-ls": "^1.2.1"
      },
      "engines": {
        "node": ">= 0.8.0"
      }
    },
    "node_modules/typescript": {
      "version": "5.9.3",
      "resolved": "https://registry.npmjs.org/typescript/-/typescript-5.9.3.tgz",
      "integrity": "sha512-jl1vZzPDinLr9eUt3J/t7V6FgNEw9QjvBPdysz9KfQDD41fQrC2Y4vKQdiaUpFT4bXlb1RHhLpp8wtm6M5TgSw==",
      "dev": true,
      "license": "Apache-2.0",
      "bin": {
        "tsc": "bin/tsc",
        "tsserver": "bin/tsserver"
      },
      "engines": {
        "node": ">=14.17"
      }
    },
    "node_modules/typescript-eslint": {
      "version": "8.52.0",
      "resolved": "https://registry.npmjs.org/typescript-eslint/-/typescript-eslint-8.52.0.tgz",
      "integrity": "sha512-atlQQJ2YkO4pfTVQmQ+wvYQwexPDOIgo+RaVcD7gHgzy/IQA+XTyuxNM9M9TVXvttkF7koBHmcwisKdOAf2EcA==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "@typescript-eslint/eslint-plugin": "8.52.0",
        "@typescript-eslint/parser": "8.52.0",
        "@typescript-eslint/typescript-estree": "8.52.0",
        "@typescript-eslint/utils": "8.52.0"
      },
      "engines": {
        "node": "^18.18.0 || ^20.9.0 || >=21.1.0"
      },
      "funding": {
        "type": "opencollective",
        "url": "https://opencollective.com/typescript-eslint"
      },
      "peerDependencies": {
        "eslint": "^8.57.0 || ^9.0.0",
        "typescript": ">=4.8.4 <6.0.0"
      }
    },
    "node_modules/undici-types": {
      "version": "7.16.0",
      "resolved": "https://registry.npmjs.org/undici-types/-/undici-types-7.16.0.tgz",
      "integrity": "sha512-Zz+aZWSj8LE6zoxD+xrjh4VfkIG8Ya6LvYkZqtUQGJPZjYl53ypCaUwWqo7eI0x66KBGeRo+mlBEkMSeSZ38Nw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/unicode-canonical-property-names-ecmascript": {
      "version": "2.0.1",
      "resolved": "https://registry.npmmirror.com/unicode-canonical-property-names-ecmascript/-/unicode-canonical-property-names-ecmascript-2.0.1.tgz",
      "integrity": "sha512-dA8WbNeb2a6oQzAQ55YlT5vQAWGV9WXOsi3SskE3bcCdM0P4SDd+24zS/OCacdRq5BkdsRj9q3Pg6YyQoxIGqg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/unicode-match-property-ecmascript": {
      "version": "2.0.0",
      "resolved": "https://registry.npmmirror.com/unicode-match-property-ecmascript/-/unicode-match-property-ecmascript-2.0.0.tgz",
      "integrity": "sha512-5kaZCrbp5mmbz5ulBkDkbY0SsPOjKqVS35VpL9ulMPfSl0J0Xsm+9Evphv9CoIZFwre7aJoa94AY6seMKGVN5Q==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "unicode-canonical-property-names-ecmascript": "^2.0.0",
        "unicode-property-aliases-ecmascript": "^2.0.0"
      },
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/unicode-match-property-value-ecmascript": {
      "version": "2.2.1",
      "resolved": "https://registry.npmmirror.com/unicode-match-property-value-ecmascript/-/unicode-match-property-value-ecmascript-2.2.1.tgz",
      "integrity": "sha512-JQ84qTuMg4nVkx8ga4A16a1epI9H6uTXAknqxkGF/aFfRLw1xC/Bp24HNLaZhHSkWd3+84t8iXnp1J0kYcZHhg==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/unicode-property-aliases-ecmascript": {
      "version": "2.2.0",
      "resolved": "https://registry.npmmirror.com/unicode-property-aliases-ecmascript/-/unicode-property-aliases-ecmascript-2.2.0.tgz",
      "integrity": "sha512-hpbDzxUY9BFwX+UeBnxv3Sh1q7HFxj48DTmXchNgRa46lO8uj3/1iEn3MiNUYTg1g9ctIqXCCERn8gYZhHC5lQ==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=4"
      }
    },
    "node_modules/update-browserslist-db": {
      "version": "1.2.3",
      "resolved": "https://registry.npmjs.org/update-browserslist-db/-/update-browserslist-db-1.2.3.tgz",
      "integrity": "sha512-Js0m9cx+qOgDxo0eMiFGEueWztz+d4+M3rGlmKPT+T4IS/jP4ylw3Nwpu6cpTTP8R1MAC1kF4VbdLt3ARf209w==",
      "dev": true,
      "funding": [
        {
          "type": "opencollective",
          "url": "https://opencollective.com/browserslist"
        },
        {
          "type": "tidelift",
          "url": "https://tidelift.com/funding/github/npm/browserslist"
        },
        {
          "type": "github",
          "url": "https://github.com/sponsors/ai"
        }
      ],
      "license": "MIT",
      "dependencies": {
        "escalade": "^3.2.0",
        "picocolors": "^1.1.1"
      },
      "bin": {
        "update-browserslist-db": "cli.js"
      },
      "peerDependencies": {
        "browserslist": ">= 4.21.0"
      }
    },
    "node_modules/uri-js": {
      "version": "4.4.1",
      "resolved": "https://registry.npmjs.org/uri-js/-/uri-js-4.4.1.tgz",
      "integrity": "sha512-7rKUyy33Q1yc98pQ1DAmLtwX109F7TIfWlW1Ydo8Wl1ii1SeHieeh0HHfPeL2fMXK6z0s8ecKs9frCuLJvndBg==",
      "dev": true,
      "license": "BSD-2-Clause",
      "dependencies": {
        "punycode": "^2.1.0"
      }
    },
    "node_modules/use-callback-ref": {
      "version": "1.3.3",
      "resolved": "https://registry.npmjs.org/use-callback-ref/-/use-callback-ref-1.3.3.tgz",
      "integrity": "sha512-jQL3lRnocaFtu3V00JToYz/4QkNWswxijDaCVNZRiRTO3HQDLsdu1ZtmIUvV4yPp+rvWm5j0y0TG/S61cuijTg==",
      "license": "MIT",
      "dependencies": {
        "tslib": "^2.0.0"
      },
      "engines": {
        "node": ">=10"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8.0 || ^17.0.0 || ^18.0.0 || ^19.0.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/use-sidecar": {
      "version": "1.1.3",
      "resolved": "https://registry.npmjs.org/use-sidecar/-/use-sidecar-1.1.3.tgz",
      "integrity": "sha512-Fedw0aZvkhynoPYlA5WXrMCAMm+nSWdZt6lzJQ7Ok8S6Q+VsHmHpRWndVRJ8Be0ZbkfPc5LRYH+5XrzXcEeLRQ==",
      "license": "MIT",
      "dependencies": {
        "detect-node-es": "^1.1.0",
        "tslib": "^2.0.0"
      },
      "engines": {
        "node": ">=10"
      },
      "peerDependencies": {
        "@types/react": "*",
        "react": "^16.8.0 || ^17.0.0 || ^18.0.0 || ^19.0.0 || ^19.0.0-rc"
      },
      "peerDependenciesMeta": {
        "@types/react": {
          "optional": true
        }
      }
    },
    "node_modules/use-sync-external-store": {
      "version": "1.6.0",
      "resolved": "https://registry.npmjs.org/use-sync-external-store/-/use-sync-external-store-1.6.0.tgz",
      "integrity": "sha512-Pp6GSwGP/NrPIrxVFAIkOQeyw8lFenOHijQWkUTrDvrF4ALqylP2C/KCkeS9dpUM3KvYRQhna5vt7IL95+ZQ9w==",
      "license": "MIT",
      "peerDependencies": {
        "react": "^16.8.0 || ^17.0.0 || ^18.0.0 || ^19.0.0"
      }
    },
    "node_modules/util-deprecate": {
      "version": "1.0.2",
      "resolved": "https://registry.npmjs.org/util-deprecate/-/util-deprecate-1.0.2.tgz",
      "integrity": "sha512-EPD5q1uXyFxJpCrLnCc1nHnq3gOa6DZBocAIiI2TaSCA7VCJ1UJDMagCzIkXNsUYfD1daK//LTEQ8xiIbrHtcw==",
      "dev": true,
      "license": "MIT"
    },
    "node_modules/vaul": {
      "version": "1.1.2",
      "resolved": "https://registry.npmjs.org/vaul/-/vaul-1.1.2.tgz",
      "integrity": "sha512-ZFkClGpWyI2WUQjdLJ/BaGuV6AVQiJ3uELGk3OYtP+B6yCO7Cmn9vPFXVJkRaGkOJu3m8bQMgtyzNHixULceQA==",
      "license": "MIT",
      "dependencies": {
        "@radix-ui/react-dialog": "^1.1.1"
      },
      "peerDependencies": {
        "react": "^16.8 || ^17.0 || ^18.0 || ^19.0.0 || ^19.0.0-rc",
        "react-dom": "^16.8 || ^17.0 || ^18.0 || ^19.0.0 || ^19.0.0-rc"
      }
    },
    "node_modules/victory-vendor": {
      "version": "36.9.2",
      "resolved": "https://registry.npmjs.org/victory-vendor/-/victory-vendor-36.9.2.tgz",
      "integrity": "sha512-PnpQQMuxlwYdocC8fIJqVXvkeViHYzotI+NJrCuav0ZYFoq912ZHBk3mCeuj+5/VpodOjPe1z0Fk2ihgzlXqjQ==",
      "license": "MIT AND ISC",
      "dependencies": {
        "@types/d3-array": "^3.0.3",
        "@types/d3-ease": "^3.0.0",
        "@types/d3-interpolate": "^3.0.1",
        "@types/d3-scale": "^4.0.2",
        "@types/d3-shape": "^3.1.0",
        "@types/d3-time": "^3.0.0",
        "@types/d3-timer": "^3.0.0",
        "d3-array": "^3.1.6",
        "d3-ease": "^3.0.1",
        "d3-interpolate": "^3.0.1",
        "d3-scale": "^4.0.2",
        "d3-shape": "^3.1.0",
        "d3-time": "^3.0.0",
        "d3-timer": "^3.0.1"
      }
    },
    "node_modules/vite": {
      "version": "7.3.0",
      "resolved": "https://registry.npmjs.org/vite/-/vite-7.3.0.tgz",
      "integrity": "sha512-dZwN5L1VlUBewiP6H9s2+B3e3Jg96D0vzN+Ry73sOefebhYr9f94wwkMNN/9ouoU8pV1BqA1d1zGk8928cx0rg==",
      "dev": true,
      "license": "MIT",
      "dependencies": {
        "esbuild": "^0.27.0",
        "fdir": "^6.5.0",
        "picomatch": "^4.0.3",
        "postcss": "^8.5.6",
        "rollup": "^4.43.0",
        "tinyglobby": "^0.2.15"
      },
      "bin": {
        "vite": "bin/vite.js"
      },
      "engines": {
        "node": "^20.19.0 || >=22.12.0"
      },
      "funding": {
        "url": "https://github.com/vitejs/vite?sponsor=1"
      },
      "optionalDependencies": {
        "fsevents": "~2.3.3"
      },
      "peerDependencies": {
        "@types/node": "^20.19.0 || >=22.12.0",
        "jiti": ">=1.21.0",
        "less": "^4.0.0",
        "lightningcss": "^1.21.0",
        "sass": "^1.70.0",
        "sass-embedded": "^1.70.0",
        "stylus": ">=0.54.8",
        "sugarss": "^5.0.0",
        "terser": "^5.16.0",
        "tsx": "^4.8.1",
        "yaml": "^2.4.2"
      },
      "peerDependenciesMeta": {
        "@types/node": {
          "optional": true
        },
        "jiti": {
          "optional": true
        },
        "less": {
          "optional": true
        },
        "lightningcss": {
          "optional": true
        },
        "sass": {
          "optional": true
        },
        "sass-embedded": {
          "optional": true
        },
        "stylus": {
          "optional": true
        },
        "sugarss": {
          "optional": true
        },
        "terser": {
          "optional": true
        },
        "tsx": {
          "optional": true
        },
        "yaml": {
          "optional": true
        }
      }
    },
    "node_modules/which": {
      "version": "2.0.2",
      "resolved": "https://registry.npmjs.org/which/-/which-2.0.2.tgz",
      "integrity": "sha512-BLI3Tl1TW3Pvl70l3yq3Y64i+awpwXqsGBYWkkqMtnbXgrMD+yj7rhW0kuEDxzJaYXGjEW5ogapKNMEKNMjibA==",
      "dev": true,
      "license": "ISC",
      "dependencies": {
        "isexe": "^2.0.0"
      },
      "bin": {
        "node-which": "bin/node-which"
      },
      "engines": {
        "node": ">= 8"
      }
    },
    "node_modules/word-wrap": {
      "version": "1.2.5",
      "resolved": "https://registry.npmjs.org/word-wrap/-/word-wrap-1.2.5.tgz",
      "integrity": "sha512-BN22B5eaMMI9UMtjrGd5g5eCYPpCPDUy0FJXbYsaT5zYxjFOckS53SQDE3pWkVoWpHXVb3BrYcEN4Twa55B5cA==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=0.10.0"
      }
    },
    "node_modules/yallist": {
      "version": "3.1.1",
      "resolved": "https://registry.npmjs.org/yallist/-/yallist-3.1.1.tgz",
      "integrity": "sha512-a4UGQaWPH59mOXUYnAG2ewncQS4i4F43Tv3JoAM+s2VDAmS9NsK8GpDMLrCHPksFT7h3K6TOoUNn2pb7RoXx4g==",
      "dev": true,
      "license": "ISC"
    },
    "node_modules/yocto-queue": {
      "version": "0.1.0",
      "resolved": "https://registry.npmjs.org/yocto-queue/-/yocto-queue-0.1.0.tgz",
      "integrity": "sha512-rVksvsnNCdJ/ohGc6xgPwyN8eheCxsiLM8mxuE/t/mOVqJewPuO1miLpTHQiRgTKCLexL4MeAFVagts7HmNZ2Q==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=10"
      },
      "funding": {
        "url": "https://github.com/sponsors/sindresorhus"
      }
    },
    "node_modules/zod": {
      "version": "4.3.5",
      "resolved": "https://registry.npmjs.org/zod/-/zod-4.3.5.tgz",
      "integrity": "sha512-k7Nwx6vuWx1IJ9Bjuf4Zt1PEllcwe7cls3VNzm4CQ1/hgtFUK2bRNG3rvnpPUhFjmqJKAKtjV576KnUkHocg/g==",
      "license": "MIT",
      "funding": {
        "url": "https://github.com/sponsors/colinhacks"
      }
    },
    "node_modules/zod-validation-error": {
      "version": "4.0.2",
      "resolved": "https://registry.npmjs.org/zod-validation-error/-/zod-validation-error-4.0.2.tgz",
      "integrity": "sha512-Q6/nZLe6jxuU80qb/4uJ4t5v2VEZ44lzQjPDhYJNztRQ4wyWc6VF3D3Kb/fAuPetZQnhS3hnajCf9CsWesghLQ==",
      "dev": true,
      "license": "MIT",
      "engines": {
        "node": ">=18.0.0"
      },
      "peerDependencies": {
        "zod": "^3.25.0 || ^4.0.0"
      }
    }
  }
}



================================================================================
FILE: app/package.json
================================================================================

{
  "name": "my-app",
  "private": true,
  "version": "0.0.0",
  "type": "module",
  "scripts": {
    "dev": "vite",
    "build": "tsc -b && vite build",
    "lint": "eslint .",
    "preview": "vite preview"
  },
  "dependencies": {
    "@hookform/resolvers": "^5.2.2",
    "@radix-ui/react-accordion": "^1.2.12",
    "@radix-ui/react-alert-dialog": "^1.1.15",
    "@radix-ui/react-aspect-ratio": "^1.1.8",
    "@radix-ui/react-avatar": "^1.1.11",
    "@radix-ui/react-checkbox": "^1.3.3",
    "@radix-ui/react-collapsible": "^1.1.12",
    "@radix-ui/react-context-menu": "^2.2.16",
    "@radix-ui/react-dialog": "^1.1.15",
    "@radix-ui/react-dropdown-menu": "^2.1.16",
    "@radix-ui/react-hover-card": "^1.1.15",
    "@radix-ui/react-label": "^2.1.8",
    "@radix-ui/react-menubar": "^1.1.16",
    "@radix-ui/react-navigation-menu": "^1.2.14",
    "@radix-ui/react-popover": "^1.1.15",
    "@radix-ui/react-progress": "^1.1.8",
    "@radix-ui/react-radio-group": "^1.3.8",
    "@radix-ui/react-scroll-area": "^1.2.10",
    "@radix-ui/react-select": "^2.2.6",
    "@radix-ui/react-separator": "^1.1.8",
    "@radix-ui/react-slider": "^1.3.6",
    "@radix-ui/react-slot": "^1.2.4",
    "@radix-ui/react-switch": "^1.2.6",
    "@radix-ui/react-tabs": "^1.1.13",
    "@radix-ui/react-toggle": "^1.1.10",
    "@radix-ui/react-toggle-group": "^1.1.11",
    "@radix-ui/react-tooltip": "^1.2.8",
    "@types/three": "^0.184.1",
    "class-variance-authority": "^0.7.1",
    "clsx": "^2.1.1",
    "cmdk": "^1.1.1",
    "date-fns": "^4.1.0",
    "embla-carousel-react": "^8.6.0",
    "gsap": "^3.15.0",
    "input-otp": "^1.4.2",
    "lucide-react": "^0.562.0",
    "next-themes": "^0.4.6",
    "react": "^19.2.0",
    "react-day-picker": "^9.13.0",
    "react-dom": "^19.2.0",
    "react-hook-form": "^7.70.0",
    "react-resizable-panels": "^4.2.2",
    "react-router": "^7.6.1",
    "react-router-dom": "^7.15.1",
    "recharts": "^2.15.4",
    "sonner": "^2.0.7",
    "tailwind-merge": "^3.4.0",
    "three": "^0.184.0",
    "vaul": "^1.1.2",
    "zod": "^4.3.5"
  },
  "devDependencies": {
    "@eslint/js": "^9.39.1",
    "@types/node": "^24.10.1",
    "@types/react": "^19.2.5",
    "@types/react-dom": "^19.2.3",
    "@vitejs/plugin-react": "^5.1.1",
    "autoprefixer": "^10.4.23",
    "eslint": "^9.39.1",
    "eslint-plugin-react-hooks": "^7.0.1",
    "eslint-plugin-react-refresh": "^0.4.24",
    "globals": "^16.5.0",
    "kimi-plugin-inspect-react": "^1.0.3",
    "postcss": "^8.5.6",
    "tailwindcss": "^3.4.19",
    "tailwindcss-animate": "^1.0.7",
    "tw-animate-css": "^1.4.0",
    "typescript": "~5.9.3",
    "typescript-eslint": "^8.46.4",
    "vite": "^7.2.4"
  }
}



================================================================================
FILE: app/postcss.config.js
================================================================================

export default {
  plugins: {
    tailwindcss: {},
    autoprefixer: {},
  },
}



================================================================================
FILE: app/tailwind.config.js
================================================================================

/** @type {import('tailwindcss').Config} */
module.exports = {
  darkMode: ["class"],
  content: ['./index.html', './src/**/*.{js,ts,jsx,tsx}'],
  theme: {
    extend: {
      colors: {
        border: "hsl(var(--border))",
        input: "hsl(var(--input))",
        ring: "hsl(var(--ring))",
        background: "hsl(var(--background))",
        foreground: "hsl(var(--foreground))",
        primary: {
          DEFAULT: "hsl(var(--primary))",
          foreground: "hsl(var(--primary-foreground))",
        },
        secondary: {
          DEFAULT: "hsl(var(--secondary))",
          foreground: "hsl(var(--secondary-foreground))",
        },
        destructive: {
          DEFAULT: "hsl(var(--destructive) / <alpha-value>)",
          foreground: "hsl(var(--destructive-foreground) / <alpha-value>)",
        },
        muted: {
          DEFAULT: "hsl(var(--muted))",
          foreground: "hsl(var(--muted-foreground))",
        },
        accent: {
          DEFAULT: "hsl(var(--accent))",
          foreground: "hsl(var(--accent-foreground))",
        },
        popover: {
          DEFAULT: "hsl(var(--popover))",
          foreground: "hsl(var(--popover-foreground))",
        },
        card: {
          DEFAULT: "hsl(var(--card))",
          foreground: "hsl(var(--card-foreground))",
        },
        sidebar: {
          DEFAULT: "hsl(var(--sidebar-background))",
          foreground: "hsl(var(--sidebar-foreground))",
          primary: "hsl(var(--sidebar-primary))",
          "primary-foreground": "hsl(var(--sidebar-primary-foreground))",
          accent: "hsl(var(--sidebar-accent))",
          "accent-foreground": "hsl(var(--sidebar-accent-foreground))",
          border: "hsl(var(--sidebar-border))",
          ring: "hsl(var(--sidebar-ring))",
        },
      },
      borderRadius: {
        xl: "calc(var(--radius) + 4px)",
        lg: "var(--radius)",
        md: "calc(var(--radius) - 2px)",
        sm: "calc(var(--radius) - 4px)",
        xs: "calc(var(--radius) - 6px)",
      },
      boxShadow: {
        xs: "0 1px 2px 0 rgb(0 0 0 / 0.05)",
      },
      keyframes: {
        "accordion-down": {
          from: { height: "0" },
          to: { height: "var(--radix-accordion-content-height)" },
        },
        "accordion-up": {
          from: { height: "var(--radix-accordion-content-height)" },
          to: { height: "0" },
        },
        "caret-blink": {
          "0%,70%,100%": { opacity: "1" },
          "20%,50%": { opacity: "0" },
        },
      },
      animation: {
        "accordion-down": "accordion-down 0.2s ease-out",
        "accordion-up": "accordion-up 0.2s ease-out",
        "caret-blink": "caret-blink 1.25s ease-out infinite",
      },
    },
  },
  plugins: [require("tailwindcss-animate")],
}


================================================================================
FILE: app/tsconfig.app.json
================================================================================

{
  "compilerOptions": {
    "tsBuildInfoFile": "./node_modules/.tmp/tsconfig.app.tsbuildinfo",
    "target": "ES2022",
    "useDefineForClassFields": true,
    "lib": ["ES2022", "DOM", "DOM.Iterable"],
    "module": "ESNext",
    "types": ["vite/client"],
    "skipLibCheck": true,

    "baseUrl": ".",
    "paths": {
      "@/*": [
        "./src/*"
      ]
    },
    /* Bundler mode */
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "verbatimModuleSyntax": true,
    "moduleDetection": "force",
    "noEmit": true,
    "jsx": "react-jsx",

    /* Linting */
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "erasableSyntaxOnly": true,
    "noFallthroughCasesInSwitch": true,
    "noUncheckedSideEffectImports": true
  },
  "include": ["src"]
}



================================================================================
FILE: app/tsconfig.json
================================================================================

{
  "files": [],
  "references": [
    {
      "path": "./tsconfig.app.json"
    },
    {
      "path": "./tsconfig.node.json"
    }
  ],
  "compilerOptions": {
    "baseUrl": ".",
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}


================================================================================
FILE: app/tsconfig.node.json
================================================================================

{
  "compilerOptions": {
    "tsBuildInfoFile": "./node_modules/.tmp/tsconfig.node.tsbuildinfo",
    "target": "ES2023",
    "lib": ["ES2023"],
    "module": "ESNext",
    "types": ["node"],
    "skipLibCheck": true,

    /* Bundler mode */
    "moduleResolution": "bundler",
    "allowImportingTsExtensions": true,
    "verbatimModuleSyntax": true,
    "moduleDetection": "force",
    "noEmit": true,

    /* Linting */
    "strict": true,
    "noUnusedLocals": true,
    "noUnusedParameters": true,
    "erasableSyntaxOnly": true,
    "noFallthroughCasesInSwitch": true,
    "noUncheckedSideEffectImports": true
  },
  "include": ["vite.config.ts"]
}



================================================================================
FILE: app/vite.config.ts
================================================================================

import path from "path"
import react from "@vitejs/plugin-react"
import { defineConfig } from "vite"
import { inspectAttr } from 'kimi-plugin-inspect-react'

// https://vite.dev/config/
export default defineConfig({
  base: './',
  plugins: [inspectAttr(), react()],
  server: {
    port: 3000,
  },
  resolve: {
    alias: {
      "@": path.resolve(__dirname, "./src"),
    },
  },
});



================================================================================
FILE: app/src/App.css
================================================================================

#root {
  max-width: 1280px;
  margin: 0 auto;
  padding: 2rem;
  text-align: center;
}

.logo {
  height: 6em;
  padding: 1.5em;
  will-change: filter;
  transition: filter 300ms;
}
.logo:hover {
  filter: drop-shadow(0 0 2em #646cffaa);
}
.logo.react:hover {
  filter: drop-shadow(0 0 2em #61dafbaa);
}

@keyframes logo-spin {
  from {
    transform: rotate(0deg);
  }
  to {
    transform: rotate(360deg);
  }
}

@media (prefers-reduced-motion: no-preference) {
  a:nth-of-type(2) .logo {
    animation: logo-spin infinite 20s linear;
  }
}

.card {
  padding: 2em;
}

.read-the-docs {
  color: #888;
}



================================================================================
FILE: app/src/App.tsx
================================================================================

import { Routes, Route } from 'react-router-dom';
import { AppProvider } from '@/context/AppContext';
import Navbar from '@/components/Navbar';
import ServerHub from '@/pages/ServerHub';
import FlightLine from '@/pages/FlightLine';
import Tower8 from '@/pages/Tower8';

function App() {
  return (
    <AppProvider>
      <Navbar />
      <Routes>
        <Route path="/" element={<ServerHub />} />
        <Route path="/flightline" element={<FlightLine />} />
        <Route path="/tower8" element={<Tower8 />} />
      </Routes>
    </AppProvider>
  );
}

export default App;



================================================================================
FILE: app/src/index.css
================================================================================

@import url('https://fonts.googleapis.com/css2?family=Inter:wght@300;400;500;600;700;800;900&family=JetBrains+Mono:wght@400;500;700&display=swap');

@tailwind base;
@tailwind components;
@tailwind utilities;

@layer base {
  :root {
    --background: 0 0% 4%;
    --foreground: 0 0% 100%;
    --card: 0 0% 10%;
    --card-foreground: 0 0% 100%;
    --popover: 0 0% 10%;
    --popover-foreground: 0 0% 100%;
    --primary: 24 100% 55%;
    --primary-foreground: 0 0% 100%;
    --secondary: 0 0% 16%;
    --secondary-foreground: 0 0% 100%;
    --muted: 0 0% 16%;
    --muted-foreground: 0 0% 63%;
    --accent: 24 100% 55%;
    --accent-foreground: 0 0% 100%;
    --destructive: 0 84.2% 60.2%;
    --destructive-foreground: 0 0% 98%;
    --border: 0 0% 16%;
    --input: 0 0% 16%;
    --ring: 24 100% 55%;
    --radius: 0.75rem;
  }

  * {
    @apply border-border;
  }

  body {
    @apply bg-[#0a0a0a] text-white antialiased;
    font-family: 'Inter', system-ui, -apple-system, sans-serif;
  }

  html {
    scroll-behavior: smooth;
  }
}

@layer components {
  .font-display {
    font-family: 'Inter', system-ui, sans-serif;
  }

  .font-mono {
    font-family: 'JetBrains Mono', monospace;
  }

  .text-gradient {
    background: linear-gradient(135deg, #ffffff 0%, #a0a0a0 100%);
    -webkit-background-clip: text;
    -webkit-text-fill-color: transparent;
    background-clip: text;
  }

  .btn-primary {
    @apply bg-white text-black font-medium uppercase tracking-widest text-sm px-8 py-3 rounded-lg transition-all duration-300;
  }

  .btn-primary:hover {
    @apply bg-[#ff6b1a] text-white;
    box-shadow: 0 0 20px rgba(255, 107, 26, 0.3);
  }

  .btn-bordered {
    @apply bg-transparent text-white font-medium uppercase tracking-widest text-sm px-8 py-3 rounded-lg border border-white transition-all duration-300;
  }

  .btn-bordered:hover {
    @apply bg-[#ff6b1a] border-[#ff6b1a] text-white;
  }

  .btn-orange {
    @apply bg-[#ff6b1a] text-white font-medium uppercase tracking-widest text-sm px-8 py-3 rounded-lg transition-all duration-300;
  }

  .btn-orange:hover {
    @apply bg-white text-black;
  }

  .card-dark {
    @apply bg-[#1a1a1a] rounded-xl border border-[#2a2a2a] transition-all duration-300;
  }

  .card-dark:hover {
    transform: translateY(-4px);
    box-shadow: 0 8px 32px rgba(0, 0, 0, 0.4);
  }

  .caption {
    @apply text-[11px] font-medium uppercase tracking-[0.15em] text-[#a0a0a0];
  }

  .section-title {
    @apply text-[28px] font-bold text-white;
  }

  .stat-number {
    @apply text-[32px] font-bold font-mono text-white;
  }

  .stat-label {
    @apply text-[11px] font-medium uppercase tracking-[0.15em] text-[#a0a0a0];
  }
}

@layer utilities {
  .scrollbar-hide {
    -ms-overflow-style: none;
    scrollbar-width: none;
  }
  .scrollbar-hide::-webkit-scrollbar {
    display: none;
  }
}

@keyframes fadeInUp {
  from {
    opacity: 0;
    transform: translateY(30px);
  }
  to {
    opacity: 1;
    transform: translateY(0);
  }
}

@keyframes pulse-glow {
  0%, 100% {
    box-shadow: 0 0 5px rgba(255, 107, 26, 0.3);
  }
  50% {
    box-shadow: 0 0 20px rgba(255, 107, 26, 0.6);
  }
}

@keyframes skeleton-pulse {
  0%, 100% {
    background-color: #1a1a1a;
  }
  50% {
    background-color: #2a2a2a;
  }
}

.animate-fade-in-up {
  animation: fadeInUp 0.6s ease-out forwards;
}

.animate-pulse-glow {
  animation: pulse-glow 2s ease-in-out infinite;
}

.animate-skeleton {
  animation: skeleton-pulse 1.5s ease-in-out infinite;
}



================================================================================
FILE: app/src/main.tsx
================================================================================

import { StrictMode } from 'react'
import { createRoot } from 'react-dom/client'
import { BrowserRouter } from 'react-router-dom'
import './index.css'
import App from './App.tsx'

createRoot(document.getElementById('root')!).render(
  <StrictMode>
    <BrowserRouter>
      <App />
    </BrowserRouter>
  </StrictMode>,
)



================================================================================
FILE: app/src/pages/FlightLine.tsx
================================================================================

import { useNavigate } from 'react-router-dom';
import { useEffect, useRef, useState } from 'react';
import { useApp } from '@/context/AppContext';
import {
  Plane, Monitor, Smartphone, Check, Calendar, ArrowRight,
  Users, Route, CalendarDays, GraduationCap
} from 'lucide-react';
import gsap from 'gsap';

const simulators = [
  { id: 'msfs2020', name: 'MSFS 2020', subtitle: 'Microsoft Flight Simulator', icon: Monitor },
  { id: 'msfs2024', name: 'MSFS 2024', subtitle: 'Microsoft Flight Simulator', icon: Monitor },
  { id: 'xp12', name: 'X-Plane 12', subtitle: 'Laminar Research', icon: Monitor },
  { id: 'xp11', name: 'X-Plane 11', subtitle: 'Laminar Research', icon: Monitor },
  { id: 'infinite', name: 'Infinite Flight', subtitle: 'Mobile Flight Sim', icon: Smartphone },
  { id: 'other', name: 'Other Simulator', subtitle: 'Your choice', icon: Monitor },
];

const aircraftCategories = [
  'Commercial Airliners',
  'General Aviation',
  'Business Jets',
  'Helicopters',
  'Military',
  'Bush/STOL',
  'Gliders',
];

const upcomingEvents = [
  {
    day: '15',
    month: 'MAR',
    title: 'Cross-Country Group Flight',
    description: 'KSEA to KSFO — Join fellow pilots for a scenic west coast journey.',
  },
  {
    day: '18',
    month: 'MAR',
    title: 'Airbus A320 Tutorial Session',
    description: 'Learn the Airbus A320 systems with our certified flight instructors.',
  },
  {
    day: '22',
    month: 'MAR',
    title: 'Sunday Casual Fly-In',
    description: 'Relaxed group flight — all aircraft and skill levels welcome.',
  },
];

export default function FlightLine() {
  const navigate = useNavigate();
  const { state, setSelectedGame, toggleAircraft } = useApp();
  const [selectedSim, setSelectedSim] = useState<string | null>(state.selectedGame);
  const contentRef = useRef<HTMLDivElement>(null);

  useEffect(() => {
    const ctx = gsap.context(() => {
      gsap.from('.fl-section', {
        opacity: 0,
        y: 30,
        duration: 0.6,
        stagger: 0.1,
        ease: 'power3.out',
      });
    }, contentRef);
    return () => ctx.revert();
  }, []);

  const handleSimSelect = (simId: string) => {
    setSelectedSim(simId);
    setSelectedGame(simId);
  };

  return (
    <div className="min-h-screen bg-[#0a0a0a] pt-16">
      {/* Header Banner */}
      <div className="relative h-[200px] w-full overflow-hidden">
        <div
          className="absolute inset-0 bg-cover bg-center"
          style={{ backgroundImage: 'url(/images/flightline-banner.jpg)' }}
        />
        <div className="absolute inset-0 bg-gradient-to-t from-[#0a0a0a] via-[#0a0a0a]/60 to-transparent" />

        <div className="relative z-10 max-w-[1200px] mx-auto px-6 h-full flex items-end pb-6">
          <div className="flex items-end gap-4">
            <div className="w-20 h-20 rounded-full border-[3px] border-white bg-[#1a1a1a] flex items-center justify-center shadow-lg -mb-10">
              <Plane className="w-8 h-8 text-[#ff6b1a]" />
            </div>
            <div className="mb-2 ml-2">
              <h1 className="text-[36px] font-bold text-white">The FlightLine</h1>
              <div className="flex items-center gap-3 text-sm">
                <span className="text-[#a0a0a0]">2,400+ members</span>
                <span className="flex items-center gap-1.5 text-[#4ade80]">
                  <span className="w-2 h-2 rounded-full bg-[#4ade80]" />
                  342 online
                </span>
              </div>
            </div>
          </div>

          <div className="ml-auto flex gap-3 mb-4">
            <button className="btn-primary py-2 px-5 text-xs h-10">Join Server</button>
            <button className="btn-bordered py-2 px-5 text-xs h-10">View Schedule</button>
          </div>
        </div>
      </div>

      {/* Main Content */}
      <div ref={contentRef} className="max-w-[1200px] mx-auto px-6 py-12 space-y-12">
        {/* Welcome */}
        <div className="fl-section pt-6">
          <p className="caption mb-2">WELCOME TO THE FLIGHTLINE</p>
          <h2 className="text-[28px] font-bold text-white mb-3">Your Aviation Community</h2>
          <p className="text-[15px] text-[#a0a0a0] leading-relaxed max-w-[600px]">
            Connect with pilots from around the world. Share routes, join group flights, and improve your skills with our community of aviation enthusiasts.
          </p>
        </div>

        {/* Game Selection */}
        <div className="fl-section">
          <p className="caption mb-2">STEP 1</p>
          <h2 className="section-title mb-2">Select Your Simulator</h2>
          <p className="text-[15px] text-[#a0a0a0] mb-6">Choose your primary flight simulation platform</p>

          <div className="grid grid-cols-1 sm:grid-cols-2 lg:grid-cols-3 gap-4">
            {simulators.map((sim) => {
              const isSelected = selectedSim === sim.id;
              return (
                <button
                  key={sim.id}
                  onClick={() => handleSimSelect(sim.id)}
                  className={`relative text-left p-5 rounded-xl border transition-all duration-300 hover:scale-[1.02] ${
                    isSelected
                      ? 'border-[#ff6b1a] bg-[rgba(255,107,26,0.05)]'
                      : 'border-[#2a2a2a] bg-[#1a1a1a] hover:border-[#4a4a4a]'
                  }`}
                >
                  {isSelected && (
                    <div className="absolute top-3 right-3 w-5 h-5 rounded-full bg-[#ff6b1a] flex items-center justify-center">
                      <Check className="w-3 h-3 text-white" />
                    </div>
                  )}
                  <sim.icon className={`w-10 h-10 mb-3 ${isSelected ? 'text-[#ff6b1a]' : 'text-[#a0a0a0]'}`} />
                  <h3 className="text-base font-semibold text-white">{sim.name}</h3>
                  <p className="text-xs text-[#a0a0a0] mt-1">{sim.subtitle}</p>
                </button>
              );
            })}
          </div>
        </div>

        {/* Aircraft Type Selector */}
        <div className="fl-section">
          <p className="caption mb-2">STEP 2</p>
          <h2 className="section-title mb-2">Aircraft Type</h2>
          <p className="text-[15px] text-[#a0a0a0] mb-6">What do you primarily fly? (Select all that apply)</p>

          <div className="flex flex-wrap gap-3">
            {aircraftCategories.map((cat) => {
              const isSelected = state.selectedAircraft.includes(cat);
              return (
                <button
                  key={cat}
                  onClick={() => toggleAircraft(cat)}
                  className={`px-5 py-2.5 rounded-xl text-sm font-medium transition-all duration-300 ${
                    isSelected
                      ? 'bg-[#ff6b1a] text-white'
                      : 'bg-[#2a2a2a] text-[#a0a0a0] hover:bg-[#3a3a3a]'
                  }`}
                >
                  {cat}
                </button>
              );
            })}
          </div>
        </div>

        {/* Selected Summary */}
        {(selectedSim || state.selectedAircraft.length > 0) && (
          <div className="fl-section bg-[#1a1a1a] rounded-xl p-6 border border-[#2a2a2a]">
            <h3 className="text-lg font-semibold text-white mb-4">Your Selection</h3>
            <div className="flex flex-wrap gap-4">
              {selectedSim && (
                <div className="flex items-center gap-2">
                  <span className="text-xs text-[#a0a0a0] uppercase tracking-wider">Simulator:</span>
                  <span className="text-sm text-[#ff6b1a] font-medium">
                    {simulators.find(s => s.id === selectedSim)?.name}
                  </span>
                </div>
              )}
              {state.selectedAircraft.length > 0 && (
                <div className="flex items-center gap-2">
                  <span className="text-xs text-[#a0a0a0] uppercase tracking-wider">Aircraft:</span>
                  <span className="text-sm text-[#ff6b1a] font-medium">
                    {state.selectedAircraft.join(', ')}
                  </span>
                </div>
              )}
            </div>
          </div>
        )}

        {/* Upcoming Events */}
        <div className="fl-section">
          <div className="flex items-center justify-between mb-6">
            <div>
              <p className="caption mb-2">COMMUNITY</p>
              <h2 className="section-title">Upcoming Events</h2>
            </div>
            <button className="text-sm text-[#ff6b1a] hover:text-white transition-colors flex items-center gap-1">
              View All <ArrowRight className="w-4 h-4" />
            </button>
          </div>

          <div className="space-y-3">
            {upcomingEvents.map((event, i) => (
              <div
                key={i}
                className="flex items-center gap-5 p-5 bg-[#1a1a1a] rounded-xl border border-[#2a2a2a] hover:border-[#4a4a4a] transition-colors"
              >
                <div className="text-center min-w-[60px]">
                  <span className="block text-[28px] font-bold font-mono text-white leading-none">{event.day}</span>
                  <span className="block text-[11px] uppercase tracking-wider text-[#a0a0a0] mt-1">{event.month}</span>
                </div>
                <div className="flex-1 border-l border-[#2a2a2a] pl-5">
                  <h3 className="text-lg font-semibold text-white mb-1">{event.title}</h3>
                  <p className="text-sm text-[#a0a0a0]">{event.description}</p>
                </div>
                <button className="text-sm text-[#ff6b1a] hover:text-white transition-colors flex items-center gap-1">
                  Details <Calendar className="w-4 h-4" />
                </button>
              </div>
            ))}
          </div>
        </div>

        {/* Community Stats */}
        <div className="fl-section">
          <div className="grid grid-cols-2 md:grid-cols-4 gap-0 bg-[#1a1a1a] rounded-xl border border-[#2a2a2a] overflow-hidden">
            {[
              { value: '2,400+', label: 'Pilots', icon: Users },
              { value: '120+', label: 'Shared Routes', icon: Route },
              { value: '48', label: 'Weekly Events', icon: CalendarDays },
              { value: '15', label: 'Certified Instructors', icon: GraduationCap },
            ].map((stat, i) => (
              <div
                key={i}
                className={`flex flex-col items-center justify-center py-8 px-4 ${
                  i < 3 ? 'border-r border-[#2a2a2a]' : ''
                }`}
              >
                <stat.icon className="w-5 h-5 text-[#ff6b1a] mb-2" />
                <span className="stat-number">{stat.value}</span>
                <span className="stat-label mt-1">{stat.label}</span>
              </div>
            ))}
          </div>
        </div>

        {/* Quick Access to Tower8 */}
        <div className="fl-section bg-[#1a1a1a] rounded-xl p-8 border border-[#2a2a2a] flex flex-col md:flex-row items-center justify-between gap-6">
          <div>
            <h3 className="text-xl font-semibold text-white mb-2">Looking for ATC Training?</h3>
            <p className="text-[15px] text-[#a0a0a0]">
              Head over to Tower8 for Roblox flight simulator ATC training and certification.
            </p>
          </div>
          <button
            onClick={() => navigate('/tower8')}
            className="btn-orange whitespace-nowrap flex items-center gap-2"
          >
            Go to Tower8
            <ArrowRight className="w-4 h-4" />
          </button>
        </div>
      </div>

      {/* Footer */}
      <footer className="bg-[#1a1a1a] py-12 px-6 mt-12">
        <div className="max-w-[1200px] mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
          <div className="flex items-center gap-2">
            <Plane className="w-5 h-5 text-[#ff6b1a]" />
            <span className="text-white font-semibold tracking-[0.08em]">FLIGHT PLATFORM</span>
          </div>
          <div className="flex gap-6">
            <button onClick={() => navigate('/')} className="text-sm text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors">Home</button>
            <button onClick={() => navigate('/flightline')} className="text-sm text-[#ff6b1a]">The FlightLine</button>
            <button onClick={() => navigate('/tower8')} className="text-sm text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors">Tower8</button>
          </div>
          <p className="text-sm text-[#4a4a4a]">&copy; 2025 Flight Platform</p>
        </div>
      </footer>
    </div>
  );
}



================================================================================
FILE: app/src/pages/Home.tsx
================================================================================

import { useState } from 'react'
import '../App.css'

export default function Home() {
  const [count, setCount] = useState(0)

  return (
    <>
      <h1>Vite + React</h1>
      <div className="card">
        <button onClick={() => setCount((count) => count + 1)}>
          count is {count}
        </button>
        <p>
          Edit <code>src/App.tsx</code> and save to test HMR
        </p>
      </div>
    </>
  )
}



================================================================================
FILE: app/src/pages/ServerHub.tsx
================================================================================

import { useNavigate } from 'react-router-dom';
import { useEffect, useRef } from 'react';
import InstrumentPanel from '@/components/InstrumentPanel';
import { Plane, TowerControl, Users, Route, Radio, GraduationCap } from 'lucide-react';
import gsap from 'gsap';

export default function ServerHub() {
  const navigate = useNavigate();
  const heroRef = useRef<HTMLDivElement>(null);
  const cardsRef = useRef<HTMLDivElement>(null);

  useEffect(() => {
    // Entrance animations
    const ctx = gsap.context(() => {
      gsap.from('.hero-caption', { opacity: 0, y: 20, duration: 0.8, delay: 0.3, ease: 'power3.out' });
      gsap.from('.hero-title', { opacity: 0, y: 30, duration: 0.8, delay: 0.5, ease: 'power3.out' });
      gsap.from('.hero-body', { opacity: 0, y: 30, duration: 0.8, delay: 0.7, ease: 'power3.out' });
      gsap.from('.hero-buttons', { opacity: 0, y: 30, duration: 0.8, delay: 0.9, ease: 'power3.out' });

      if (cardsRef.current) {
        gsap.from('.server-card', {
          opacity: 0,
          y: 40,
          duration: 0.6,
          stagger: 0.15,
          ease: 'power3.out',
          scrollTrigger: {
            trigger: cardsRef.current,
            start: 'top 80%',
          },
        });
      }
    });

    return () => ctx.revert();
  }, []);

  return (
    <div className="min-h-screen bg-[#0a0a0a]">
      {/* Hero Section with 3D Instrument */}
      <div ref={heroRef} className="relative h-screen w-full overflow-hidden">
        {/* 3D Instrument Background */}
        <InstrumentPanel />

        {/* Left gradient overlay for text readability */}
        <div
          className="absolute inset-0 z-[1] pointer-events-none"
          style={{
            background: 'linear-gradient(to right, rgba(0,0,0,0.85) 0%, rgba(0,0,0,0.4) 35%, transparent 60%)',
          }}
        />

        {/* Hero Content */}
        <div className="relative z-[2] h-full flex items-center">
          <div className="max-w-[1200px] mx-auto w-full px-6">
            <div className="max-w-[480px]">
              <p className="hero-caption caption mb-4">AVIATION TRAINING PLATFORM</p>
              <h1 className="hero-title text-[56px] md:text-[64px] font-extrabold text-white leading-[1.0] tracking-[-0.02em] mb-6">
                Choose Your<br />Flight Path
              </h1>
              <p className="hero-body text-[15px] text-[#a0a0a0] leading-[1.7] tracking-[0.01em] mb-8 max-w-[380px]">
                Join The FlightLine for general aviation simulation, or Tower8 for ATC training on Roblox. Your journey starts here.
              </p>
              <div className="hero-buttons flex gap-4 flex-wrap">
                <button
                  onClick={() => navigate('/flightline')}
                  className="btn-primary h-12 w-[180px] flex items-center justify-center gap-2"
                >
                  <Plane className="w-4 h-4" />
                  The FlightLine
                </button>
                <button
                  onClick={() => navigate('/tower8')}
                  className="btn-bordered h-12 w-[180px] flex items-center justify-center gap-2"
                >
                  <TowerControl className="w-4 h-4" />
                  Tower8
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>

      {/* Server Cards Section */}
      <div ref={cardsRef} className="py-20 px-6 bg-[#0a0a0a]">
        <div className="max-w-[1200px] mx-auto">
          <div className="text-center mb-12">
            <p className="caption mb-3">SELECT A SERVER</p>
            <h2 className="text-[36px] md:text-[48px] font-bold text-white leading-[1.1] tracking-[-0.01em]">
              Two Communities.<br />One Passion.
            </h2>
          </div>

          <div className="grid grid-cols-1 lg:grid-cols-2 gap-4">
            {/* The FlightLine Card */}
            <div
              className="server-card group relative overflow-hidden rounded-xl cursor-pointer"
              style={{ height: '400px' }}
              onClick={() => navigate('/flightline')}
            >
              <div
                className="absolute inset-0 bg-cover bg-center transition-transform duration-500 group-hover:scale-105"
                style={{ backgroundImage: 'url(/images/flightline-server.jpg)' }}
              />
              <div className="absolute inset-0 bg-gradient-to-r from-black/90 via-black/60 to-transparent" />

              <div className="relative z-10 h-full flex flex-col justify-between p-6 md:p-8">
                <div className="flex-1">
                  <div className="flex items-center gap-3 mb-4">
                    <div className="w-12 h-12 rounded-full border-2 border-white flex items-center justify-center bg-[#1a1a1a]">
                      <Plane className="w-5 h-5 text-[#ff6b1a]" />
                    </div>
                    <div>
                      <h3 className="text-[28px] font-bold text-white leading-tight">The FlightLine</h3>
                      <p className="text-sm text-[#a0a0a0]">General Aviation Community</p>
                    </div>
                  </div>

                  <p className="text-[15px] text-[#a0a0a0] leading-relaxed max-w-[320px] mb-4">
                    For MSFS 2020/2024, X-Plane, Infinite Flight, and all major flight simulators. Connect with fellow pilots, share routes, and explore the skies together.
                  </p>

                  <div className="flex flex-wrap gap-2 mb-4">
                    {['MSFS', 'X-Plane 12', 'Infinite Flight'].map(tag => (
                      <span key={tag} className="px-3 py-1 bg-[#2a2a2a] rounded text-[11px] uppercase tracking-wider text-[#a0a0a0]">
                        {tag}
                      </span>
                    ))}
                  </div>

                  <div className="flex gap-6">
                    <div>
                      <span className="stat-number text-[24px]">2,400+</span>
                      <span className="stat-label block mt-1">Pilots</span>
                    </div>
                    <div>
                      <span className="stat-number text-[24px]">120+</span>
                      <span className="stat-label block mt-1">Routes</span>
                    </div>
                  </div>
                </div>

                <button className="btn-bordered w-fit mt-4 flex items-center gap-2">
                  Join Server
                  <Plane className="w-4 h-4" />
                </button>
              </div>
            </div>

            {/* Tower8 Card */}
            <div
              className="server-card group relative overflow-hidden rounded-xl cursor-pointer"
              style={{ height: '400px' }}
              onClick={() => navigate('/tower8')}
            >
              <div
                className="absolute inset-0 bg-cover bg-center transition-transform duration-500 group-hover:scale-105"
                style={{ backgroundImage: 'url(/images/tower8-server.jpg)' }}
              />
              <div className="absolute inset-0 bg-gradient-to-r from-black/90 via-black/60 to-transparent" />

              <div className="relative z-10 h-full flex flex-col justify-between p-6 md:p-8">
                <div className="flex-1">
                  <div className="flex items-center gap-3 mb-4">
                    <div className="w-12 h-12 rounded-full border-2 border-white flex items-center justify-center bg-[#1a1a1a]">
                      <TowerControl className="w-5 h-5 text-[#ff6b1a]" />
                    </div>
                    <div>
                      <h3 className="text-[28px] font-bold text-white leading-tight">Tower8</h3>
                      <p className="text-sm text-[#a0a0a0]">ATC Training & Roblox Flight Sims</p>
                    </div>
                  </div>

                  <p className="text-[15px] text-[#a0a0a0] leading-relaxed max-w-[320px] mb-4">
                    Master air traffic control on Pilot Training Flight Simulator and Project Flight. Learn proper phraseology, ATC procedures, and earn your controller rating.
                  </p>

                  <div className="flex flex-wrap gap-2 mb-4">
                    {['PTFS', 'Project Flight', 'ATC Training'].map(tag => (
                      <span key={tag} className="px-3 py-1 bg-[#2a2a2a] rounded text-[11px] uppercase tracking-wider text-[#a0a0a0]">
                        {tag}
                      </span>
                    ))}
                  </div>

                  <div className="flex gap-6">
                    <div>
                      <span className="stat-number text-[24px]">800+</span>
                      <span className="stat-label block mt-1">Controllers</span>
                    </div>
                    <div>
                      <span className="stat-number text-[24px]">50+</span>
                      <span className="stat-label block mt-1">Trainers</span>
                    </div>
                  </div>
                </div>

                <button className="btn-bordered w-fit mt-4 flex items-center gap-2">
                  Join Server
                  <TowerControl className="w-4 h-4" />
                </button>
              </div>
            </div>
          </div>
        </div>
      </div>

      {/* Features Overview */}
      <div className="py-20 px-6 bg-[#0a0a0a] border-t border-[#1a1a1a]">
        <div className="max-w-[1200px] mx-auto">
          <div className="text-center mb-12">
            <p className="caption mb-3">PLATFORM FEATURES</p>
            <h2 className="text-[36px] font-bold text-white leading-[1.1]">
              Everything You Need
            </h2>
          </div>

          <div className="grid grid-cols-1 md:grid-cols-2 lg:grid-cols-4 gap-4">
            {[
              { icon: Users, title: 'Community', desc: 'Connect with thousands of aviation enthusiasts and professionals.' },
              { icon: Route, title: 'Route Sharing', desc: 'Share and discover flight routes across all major simulators.' },
              { icon: Radio, title: 'ATC Training', desc: 'Learn proper ATC phraseology and procedures from certified trainers.' },
              { icon: GraduationCap, title: 'Certifications', desc: 'Earn ratings and certifications as you progress through training.' },
            ].map((feature, i) => (
              <div key={i} className="card-dark p-6">
                <feature.icon className="w-8 h-8 text-[#ff6b1a] mb-4" />
                <h3 className="text-lg font-semibold text-white mb-2">{feature.title}</h3>
                <p className="text-sm text-[#a0a0a0] leading-relaxed">{feature.desc}</p>
              </div>
            ))}
          </div>
        </div>
      </div>

      {/* Footer */}
      <footer className="bg-[#1a1a1a] py-12 px-6">
        <div className="max-w-[1200px] mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
          <div className="flex items-center gap-2">
            <Plane className="w-5 h-5 text-[#ff6b1a]" />
            <span className="text-white font-semibold tracking-[0.08em]">FLIGHT PLATFORM</span>
          </div>
          <div className="flex gap-6">
            <button onClick={() => navigate('/')} className="text-sm text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors">Home</button>
            <button onClick={() => navigate('/flightline')} className="text-sm text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors">The FlightLine</button>
            <button onClick={() => navigate('/tower8')} className="text-sm text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors">Tower8</button>
            <span className="text-sm text-[#a0a0a0]">Discord</span>
          </div>
          <p className="text-sm text-[#4a4a4a]">&copy; 2025 Flight Platform</p>
        </div>
      </footer>
    </div>
  );
}



================================================================================
FILE: app/src/pages/Tower8.tsx
================================================================================

import { useNavigate } from 'react-router-dom';
import { useEffect, useRef, useState } from 'react';
import { useApp } from '@/context/AppContext';
import type { TimeSlot, Instructor } from '@/context/AppContext';
import {
  TowerControl, Gamepad2, Plane, Calendar, Star,
  ArrowRight, Check, ChevronDown, Shield, Trash2, Edit3,
  Clock, BookOpen, GraduationCap, BarChart3
} from 'lucide-react';
import gsap from 'gsap';

const sessionTypeColors: Record<string, string> = {
  tower: 'bg-[#ff6b1a]',
  approach: 'bg-[#3b82f6]',
  ground: 'bg-[#4ade80]',
  center: 'bg-[#a855f7]',
};

const sessionTypeLabels: Record<string, string> = {
  tower: 'Tower Training',
  approach: 'Approach Training',
  ground: 'Ground Training',
  center: 'Center/Enroute',
};

const weekDays = ['Mon', 'Tue', 'Wed', 'Thu', 'Fri', 'Sat', 'Sun'];
const weekDates = ['May 19', 'May 20', 'May 21', 'May 22', 'May 23', 'May 24', 'May 25'];

export default function Tower8() {
  const navigate = useNavigate();
  const { state, bookSlot, cancelBooking, addInstructor, removeInstructor, toggleInstructorStatus } = useApp();
  const contentRef = useRef<HTMLDivElement>(null);
  const [activeTab, setActiveTab] = useState<'book' | 'instructor'>('book');
  const [selectedDay, setSelectedDay] = useState(0);
  const [selectedGame, setSelectedGame] = useState<'PTFS' | 'Project Flight' | null>(null);
  const [showAddInstructor, setShowAddInstructor] = useState(false);
  const [newInstructorName, setNewInstructorName] = useState('');
  const [newInstructorRole, setNewInstructorRole] = useState('Tower Instructor');
  const [newInstructorGames, setNewInstructorGames] = useState<string[]>([]);

  useEffect(() => {
    const ctx = gsap.context(() => {
      gsap.from('.t8-section', {
        opacity: 0,
        y: 30,
        duration: 0.6,
        stagger: 0.1,
        ease: 'power3.out',
      });
    }, contentRef);
    return () => ctx.revert();
  }, []);

  const filteredSlots = state.timeSlots.filter(
    (slot: TimeSlot) => slot.day === weekDays[selectedDay] &&
    (!selectedGame || slot.game === selectedGame)
  );

  const myBookings = state.timeSlots.filter((slot: TimeSlot) => slot.trainee === 'You');
  const instructorBookings = state.timeSlots.filter(
    (slot: TimeSlot) => slot.status === 'booked' || slot.status === 'pending'
  );

  const handleAddInstructor = () => {
    if (!newInstructorName.trim()) return;
    const instructor: Instructor = {
      id: Date.now().toString(),
      name: newInstructorName,
      role: newInstructorRole,
      games: newInstructorGames.length > 0 ? newInstructorGames : ['PTFS'],
      sessions: 0,
      hours: 0,
      rating: 5.0,
      status: 'active',
    };
    addInstructor(instructor);
    setNewInstructorName('');
    setNewInstructorGames([]);
    setShowAddInstructor(false);
  };

  const toggleGame = (game: string) => {
    setNewInstructorGames(prev =>
      prev.includes(game) ? prev.filter(g => g !== game) : [...prev, game]
    );
  };

  return (
    <div className="min-h-screen bg-[#0a0a0a] pt-16">
      {/* Header Banner */}
      <div className="relative h-[200px] w-full overflow-hidden">
        <div
          className="absolute inset-0 bg-cover bg-center"
          style={{ backgroundImage: 'url(/images/tower8-banner.jpg)' }}
        />
        <div className="absolute inset-0 bg-gradient-to-t from-[#0a0a0a] via-[#0a0a0a]/60 to-transparent" />

        <div className="relative z-10 max-w-[1200px] mx-auto px-6 h-full flex items-end pb-6">
          <div className="flex items-end gap-4">
            <div className="w-20 h-20 rounded-full border-[3px] border-white bg-[#1a1a1a] flex items-center justify-center shadow-lg -mb-10">
              <TowerControl className="w-8 h-8 text-[#ff6b1a]" />
            </div>
            <div className="mb-2 ml-2">
              <h1 className="text-[36px] font-bold text-white">Tower8</h1>
              <div className="flex items-center gap-3 text-sm">
                <span className="text-[#a0a0a0]">ATC Training & Roblox Flight Simulation</span>
                <span className="flex items-center gap-1.5 text-[#4ade80]">
                  <span className="w-2 h-2 rounded-full bg-[#4ade80]" />
                  156 online
                </span>
              </div>
            </div>
          </div>

          <div className="ml-auto flex gap-3 mb-4">
            <button className="btn-primary py-2 px-5 text-xs h-10">Join Server</button>
            <button
              onClick={() => setActiveTab('book')}
              className="btn-orange py-2 px-5 text-xs h-10"
            >
              Book Training
            </button>
          </div>
        </div>
      </div>

      {/* Main Content */}
      <div ref={contentRef} className="max-w-[1200px] mx-auto px-6 py-12 space-y-12">
        {/* Welcome */}
        <div className="t8-section pt-6">
          <p className="caption mb-2">WELCOME TO TOWER8</p>
          <h2 className="text-[28px] font-bold text-white mb-3">ATC Training Portal</h2>
          <p className="text-[15px] text-[#a0a0a0] leading-relaxed max-w-[600px]">
            Master air traffic control procedures on Roblox flight simulators. Learn from certified instructors and earn your controller ratings.
          </p>
        </div>

        {/* How Training Works */}
        <div className="t8-section">
          <p className="caption mb-2">PROCESS</p>
          <h2 className="section-title mb-8">How Training Works</h2>

          <div className="grid grid-cols-1 md:grid-cols-3 gap-4 relative">
            {/* Connecting line */}
            <div className="hidden md:block absolute top-[60px] left-[20%] right-[20%] h-px bg-[#2a2a2a]" />

            {[
              {
                icon: Gamepad2,
                title: 'Select Your Game',
                description: 'Choose between Pilot Training Flight Simulator or Project Flight on Roblox.',
              },
              {
                icon: Plane,
                title: 'Choose Aircraft Type',
                description: 'Select the aircraft category you want training for.',
              },
              {
                icon: Calendar,
                title: 'Book Your Session',
                description: 'Pick a time slot that works for you. Our certified instructors will guide you.',
              },
            ].map((step, i) => (
              <div key={i} className="card-dark p-6 relative z-10">
                <div className="w-10 h-10 rounded-full bg-[#ff6b1a]/10 flex items-center justify-center mb-4">
                  <step.icon className="w-5 h-5 text-[#ff6b1a]" />
                </div>
                <div className="text-[11px] uppercase tracking-wider text-[#ff6b1a] mb-2">Step {i + 1}</div>
                <h3 className="text-lg font-semibold text-white mb-2">{step.title}</h3>
                <p className="text-sm text-[#a0a0a0] leading-relaxed">{step.description}</p>
              </div>
            ))}
          </div>
        </div>

        {/* Roblox Game Selector */}
        <div className="t8-section">
          <p className="caption mb-2">PLATFORM</p>
          <h2 className="section-title mb-6">Select Your Platform</h2>

          <div className="grid grid-cols-1 md:grid-cols-2 gap-4">
            {/* PTFS Card */}
            <button
              onClick={() => setSelectedGame(selectedGame === 'PTFS' ? null : 'PTFS')}
              className={`relative overflow-hidden rounded-xl text-left transition-all duration-300 hover:scale-[1.02] ${
                selectedGame === 'PTFS' ? 'ring-2 ring-[#ff6b1a]' : ''
              }`}
              style={{ height: '280px' }}
            >
              <div
                className="absolute inset-0 bg-cover bg-center"
                style={{ backgroundImage: 'url(/images/ptfs-card.jpg)' }}
              />
              <div className="absolute inset-0 bg-gradient-to-t from-black via-black/70 to-transparent" />
              <div className="relative z-10 h-full flex flex-col justify-end p-6">
                <h3 className="text-xl font-semibold text-white mb-2">Pilot Training Flight Simulator</h3>
                <p className="text-sm text-[#a0a0a0] mb-3">
                  The most popular Roblox flight simulator. Train with realistic ATC procedures.
                </p>
                <div className="flex flex-wrap gap-2 mb-3">
                  {['Beginner Friendly', 'ATC', 'Multiplayer'].map(tag => (
                    <span key={tag} className="px-2 py-0.5 bg-white/10 rounded text-[10px] uppercase tracking-wider text-white/80">
                      {tag}
                    </span>
                  ))}
                </div>
                <span className={`text-sm font-medium ${selectedGame === 'PTFS' ? 'text-[#ff6b1a]' : 'text-white'}`}>
                  {selectedGame === 'PTFS' ? 'Selected' : 'Select PTFS'}
                </span>
              </div>
            </button>

            {/* Project Flight Card */}
            <button
              onClick={() => setSelectedGame(selectedGame === 'Project Flight' ? null : 'Project Flight')}
              className={`relative overflow-hidden rounded-xl text-left transition-all duration-300 hover:scale-[1.02] ${
                selectedGame === 'Project Flight' ? 'ring-2 ring-[#ff6b1a]' : ''
              }`}
              style={{ height: '280px' }}
            >
              <div
                className="absolute inset-0 bg-cover bg-center"
                style={{ backgroundImage: 'url(/images/project-flight-card.jpg)' }}
              />
              <div className="absolute inset-0 bg-gradient-to-t from-black via-black/70 to-transparent" />
              <div className="relative z-10 h-full flex flex-col justify-end p-6">
                <h3 className="text-xl font-semibold text-white mb-2">Project Flight</h3>
                <p className="text-sm text-[#a0a0a0] mb-3">
                  Next-gen Roblox aviation with advanced flight physics and detailed aircraft systems.
                </p>
                <div className="flex flex-wrap gap-2 mb-3">
                  {['Advanced', 'Realistic', 'Study Level'].map(tag => (
                    <span key={tag} className="px-2 py-0.5 bg-white/10 rounded text-[10px] uppercase tracking-wider text-white/80">
                      {tag}
                    </span>
                  ))}
                </div>
                <span className={`text-sm font-medium ${selectedGame === 'Project Flight' ? 'text-[#ff6b1a]' : 'text-white'}`}>
                  {selectedGame === 'Project Flight' ? 'Selected' : 'Select Project Flight'}
                </span>
              </div>
            </button>
          </div>
        </div>

        {/* Training Schedule / Availability System */}
        <div className="t8-section">
          <p className="caption mb-2">SCHEDULING</p>
          <h2 className="section-title mb-6">Training Availability</h2>

          {/* Tab Switcher */}
          <div className="flex bg-[#1a1a1a] rounded-xl p-1 w-fit mb-8">
            <button
              onClick={() => setActiveTab('book')}
              className={`px-6 py-2.5 rounded-lg text-sm font-medium transition-all ${
                activeTab === 'book'
                  ? 'bg-[#ff6b1a] text-white'
                  : 'text-[#a0a0a0] hover:text-white'
              }`}
            >
              Book a Session
            </button>
            <button
              onClick={() => setActiveTab('instructor')}
              className={`px-6 py-2.5 rounded-lg text-sm font-medium transition-all ${
                activeTab === 'instructor'
                  ? 'bg-[#ff6b1a] text-white'
                  : 'text-[#a0a0a0] hover:text-white'
              }`}
            >
              Instructor Dashboard
            </button>
          </div>

          {activeTab === 'book' ? (
            /* Book a Session View */
            <div>
              {/* Week Navigator */}
              <div className="flex gap-2 mb-6 overflow-x-auto pb-2 scrollbar-hide">
                {weekDays.map((day, i) => (
                  <button
                    key={day}
                    onClick={() => setSelectedDay(i)}
                    className={`flex flex-col items-center min-w-[70px] py-3 px-4 rounded-xl border transition-all ${
                      selectedDay === i
                        ? 'border-[#ff6b1a] bg-[rgba(255,107,26,0.05)]'
                        : 'border-[#2a2a2a] bg-[#1a1a1a] hover:border-[#4a4a4a]'
                    }`}
                  >
                    <span className="text-[11px] uppercase tracking-wider text-[#a0a0a0]">{day}</span>
                    <span className={`text-[20px] font-bold font-mono mt-1 ${selectedDay === i ? 'text-[#ff6b1a]' : 'text-white'}`}>
                      {weekDates[i].split(' ')[1]}
                    </span>
                  </button>
                ))}
              </div>

              {/* My Bookings */}
              {myBookings.length > 0 && (
                <div className="mb-6">
                  <h3 className="text-sm font-medium text-white mb-3 flex items-center gap-2">
                    <Check className="w-4 h-4 text-[#4ade80]" />
                    My Bookings
                  </h3>
                  <div className="space-y-2">
                    {myBookings.map((slot: TimeSlot) => (
                      <div key={slot.id} className="flex items-center gap-4 p-4 bg-[#1a1a1a] rounded-xl border border-[#4ade80]/30">
                        <div className="text-center min-w-[80px]">
                          <span className="block text-lg font-bold font-mono text-white">{slot.time}</span>
                          <span className="text-[11px] uppercase text-[#a0a0a0]">{slot.day} {slot.date}</span>
                        </div>
                        <div className="flex-1">
                          <div className="flex items-center gap-2 mb-1">
                            <span className={`px-2 py-0.5 rounded text-[10px] uppercase text-white ${sessionTypeColors[slot.sessionType]}`}>
                              {sessionTypeLabels[slot.sessionType]}
                            </span>
                            <span className="text-xs text-[#a0a0a0]">{slot.game}</span>
                          </div>
                          <span className="text-sm text-white">Instructor: {slot.instructor}</span>
                        </div>
                        <button
                          onClick={() => cancelBooking(slot.id)}
                          className="px-3 py-1.5 rounded-lg border border-red-500/50 text-red-400 text-xs hover:bg-red-500/10 transition-colors"
                        >
                          Cancel
                        </button>
                      </div>
                    ))}
                  </div>
                </div>
              )}

              {/* Time Slots Grid */}
              <h3 className="text-sm font-medium text-white mb-3 flex items-center gap-2">
                <Clock className="w-4 h-4 text-[#ff6b1a]" />
                Available Slots — {weekDays[selectedDay]} {weekDates[selectedDay]}
              </h3>

              {filteredSlots.length > 0 ? (
                <div className="grid grid-cols-1 md:grid-cols-2 gap-3">
                  {filteredSlots.map((slot: TimeSlot) => (
                    <div
                      key={slot.id}
                      className={`p-4 rounded-xl border transition-all ${
                        slot.status === 'booked'
                          ? 'bg-[#1a1a1a]/50 border-[#2a2a2a] opacity-60'
                          : 'bg-[#1a1a1a] border-[#2a2a2a] hover:border-[#4a4a4a]'
                      }`}
                    >
                      <div className="flex items-center justify-between mb-2">
                        <span className="text-lg font-bold font-mono text-white">{slot.time}</span>
                        {slot.status === 'booked' ? (
                          <span className="px-2 py-0.5 bg-[#4a4a4a] rounded text-[10px] uppercase text-[#a0a0a0]">
                            Booked
                          </span>
                        ) : (
                          <span className="px-2 py-0.5 bg-[#4ade80]/10 rounded text-[10px] uppercase text-[#4ade80]">
                            Available
                          </span>
                        )}
                      </div>
                      <div className="flex items-center gap-2 mb-2">
                        <span className={`px-2 py-0.5 rounded text-[10px] uppercase text-white ${sessionTypeColors[slot.sessionType]}`}>
                          {sessionTypeLabels[slot.sessionType]}
                        </span>
                        <span className="text-xs text-[#a0a0a0]">{slot.game}</span>
                      </div>
                      <div className="flex items-center justify-between">
                        <span className="text-sm text-[#a0a0a0]">Instructor: {slot.instructor}</span>
                        {slot.status === 'available' ? (
                          <button
                            onClick={() => bookSlot(slot.id)}
                            className="px-4 py-1.5 rounded-lg border border-[#ff6b1a] text-[#ff6b1a] text-xs hover:bg-[#ff6b1a] hover:text-white transition-all"
                          >
                            Book
                          </button>
                        ) : (
                          <span className="text-xs text-[#4a4a4a]">{slot.trainee}</span>
                        )}
                      </div>
                    </div>
                  ))}
                </div>
              ) : (
                <div className="text-center py-12 bg-[#1a1a1a] rounded-xl border border-[#2a2a2a]">
                  <Calendar className="w-8 h-8 text-[#4a4a4a] mx-auto mb-3" />
                  <p className="text-[#a0a0a0]">No available slots for this day</p>
                </div>
              )}
            </div>
          ) : (
            /* Instructor Dashboard View */
            <div className="space-y-8">
              {/* Instructor Stats */}
              <div className="grid grid-cols-2 md:grid-cols-4 gap-4">
                {[
                  { value: '12', label: 'Sessions This Month', icon: BookOpen },
                  { value: '48', label: 'Total Hours', icon: Clock },
                  { value: '4.9', label: 'Rating', icon: Star },
                  { value: '156', label: 'Students Trained', icon: GraduationCap },
                ].map((stat, i) => (
                  <div key={i} className="card-dark p-5 flex flex-col items-center text-center">
                    <stat.icon className="w-5 h-5 text-[#ff6b1a] mb-2" />
                    <span className="stat-number text-[24px]">{stat.value}</span>
                    <span className="stat-label mt-1">{stat.label}</span>
                  </div>
                ))}
              </div>

              {/* My Bookings Table */}
              <div>
                <h3 className="text-lg font-semibold text-white mb-4 flex items-center gap-2">
                  <BookOpen className="w-5 h-5 text-[#ff6b1a]" />
                  My Bookings
                </h3>
                <div className="bg-[#1a1a1a] rounded-xl border border-[#2a2a2a] overflow-hidden">
                  <div className="overflow-x-auto">
                    <table className="w-full text-sm">
                      <thead>
                        <tr className="border-b border-[#2a2a2a]">
                          <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Date</th>
                          <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Time</th>
                          <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Trainee</th>
                          <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Game</th>
                          <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Type</th>
                          <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Status</th>
                          <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Actions</th>
                        </tr>
                      </thead>
                      <tbody>
                        {instructorBookings.map((slot: TimeSlot, i: number) => (
                          <tr
                            key={slot.id}
                            className={`border-b border-[#2a2a2a] ${i % 2 === 0 ? 'bg-[#1a1a1a]' : 'bg-[#0a0a0a]'}`}
                          >
                            <td className="px-4 py-3 text-white">{slot.day} {slot.date}</td>
                            <td className="px-4 py-3 text-white font-mono">{slot.time}</td>
                            <td className="px-4 py-3 text-white">{slot.trainee}</td>
                            <td className="px-4 py-3 text-[#a0a0a0]">{slot.game}</td>
                            <td className="px-4 py-3">
                              <span className={`px-2 py-0.5 rounded text-[10px] uppercase text-white ${sessionTypeColors[slot.sessionType]}`}>
                                {sessionTypeLabels[slot.sessionType]}
                              </span>
                            </td>
                            <td className="px-4 py-3">
                              <span className={`px-2 py-0.5 rounded text-[10px] uppercase ${
                                slot.status === 'booked'
                                  ? 'bg-[#4ade80]/10 text-[#4ade80]'
                                  : slot.status === 'pending'
                                  ? 'bg-[#ff6b1a]/10 text-[#ff6b1a]'
                                  : 'bg-[#4a4a4a]/30 text-[#a0a0a0]'
                              }`}>
                                {slot.status}
                              </span>
                            </td>
                            <td className="px-4 py-3">
                              <div className="flex gap-2">
                                <button className="text-[#ff6b1a] hover:text-white transition-colors text-xs">
                                  Join
                                </button>
                                <button className="text-red-400 hover:text-red-300 transition-colors text-xs">
                                  Cancel
                                </button>
                              </div>
                            </td>
                          </tr>
                        ))}
                      </tbody>
                    </table>
                  </div>
                </div>
              </div>
            </div>
          )}
        </div>

        {/* Instructor Role Management — Admin Only */}
        {state.userRole === 'admin' && (
          <div className="t8-section">
            <div className="flex items-center justify-between mb-6">
              <div>
                <p className="caption mb-2">ADMIN</p>
                <h2 className="section-title flex items-center gap-2">
                  <Shield className="w-6 h-6 text-[#ff6b1a]" />
                  Instructor Management
                </h2>
              </div>
              <button
                onClick={() => setShowAddInstructor(!showAddInstructor)}
                className="btn-orange text-xs py-2 px-4"
              >
                {showAddInstructor ? 'Cancel' : 'Add Instructor'}
              </button>
            </div>

            {/* Add Instructor Form */}
            {showAddInstructor && (
              <div className="bg-[#1a1a1a] rounded-xl p-6 border border-[#2a2a2a] mb-6">
                <h3 className="text-lg font-semibold text-white mb-4">Add New Instructor</h3>
                <div className="grid grid-cols-1 md:grid-cols-2 gap-4 mb-4">
                  <div>
                    <label className="caption block mb-2">Discord Username</label>
                    <input
                      type="text"
                      value={newInstructorName}
                      onChange={(e) => setNewInstructorName(e.target.value)}
                      placeholder="e.g. ATC_Master"
                      className="w-full h-11 px-4 bg-[#0a0a0a] border border-[#2a2a2a] rounded-lg text-white text-sm focus:border-[#ff6b1a] focus:outline-none transition-colors"
                    />
                  </div>
                  <div>
                    <label className="caption block mb-2">Role</label>
                    <div className="relative">
                      <select
                        value={newInstructorRole}
                        onChange={(e) => setNewInstructorRole(e.target.value)}
                        className="w-full h-11 px-4 pr-10 bg-[#0a0a0a] border border-[#2a2a2a] rounded-lg text-white text-sm appearance-none focus:border-[#ff6b1a] focus:outline-none transition-colors"
                      >
                        <option>Tower Instructor</option>
                        <option>Approach Instructor</option>
                        <option>Ground Instructor</option>
                        <option>Center Instructor</option>
                        <option>Admin</option>
                      </select>
                      <ChevronDown className="absolute right-3 top-1/2 -translate-y-1/2 w-4 h-4 text-[#a0a0a0] pointer-events-none" />
                    </div>
                  </div>
                </div>
                <div className="mb-4">
                  <label className="caption block mb-2">Games They Can Teach</label>
                  <div className="flex gap-3">
                    {['PTFS', 'Project Flight'].map(game => (
                      <button
                        key={game}
                        onClick={() => toggleGame(game)}
                        className={`px-4 py-2 rounded-lg text-sm border transition-all ${
                          newInstructorGames.includes(game)
                            ? 'border-[#ff6b1a] bg-[rgba(255,107,26,0.1)] text-[#ff6b1a]'
                            : 'border-[#2a2a2a] text-[#a0a0a0] hover:border-[#4a4a4a]'
                        }`}
                      >
                        {newInstructorGames.includes(game) && <Check className="w-3 h-3 inline mr-1" />}
                        {game}
                      </button>
                    ))}
                  </div>
                </div>
                <button
                  onClick={handleAddInstructor}
                  className="btn-orange text-xs py-2 px-6"
                >
                  Add Instructor
                </button>
              </div>
            )}

            {/* Instructor List */}
            <div className="bg-[#1a1a1a] rounded-xl border border-[#2a2a2a] overflow-hidden">
              <div className="overflow-x-auto">
                <table className="w-full text-sm">
                  <thead>
                    <tr className="border-b border-[#2a2a2a]">
                      <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Name</th>
                      <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Role</th>
                      <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Games</th>
                      <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Sessions</th>
                      <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Rating</th>
                      <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Status</th>
                      <th className="text-left px-4 py-3 text-[#a0a0a0] font-medium">Actions</th>
                    </tr>
                  </thead>
                  <tbody>
                    {state.instructors.map((instructor: Instructor, i: number) => (
                      <tr
                        key={instructor.id}
                        className={`border-b border-[#2a2a2a] ${i % 2 === 0 ? 'bg-[#1a1a1a]' : 'bg-[#0a0a0a]'}`}
                      >
                        <td className="px-4 py-3 text-white font-medium">{instructor.name}</td>
                        <td className="px-4 py-3 text-[#a0a0a0]">{instructor.role}</td>
                        <td className="px-4 py-3">
                          <div className="flex gap-1">
                            {instructor.games.map(g => (
                              <span key={g} className="px-1.5 py-0.5 bg-[#2a2a2a] rounded text-[10px] text-[#a0a0a0]">
                                {g}
                              </span>
                            ))}
                          </div>
                        </td>
                        <td className="px-4 py-3 text-white font-mono">{instructor.sessions}</td>
                        <td className="px-4 py-3">
                          <div className="flex items-center gap-1">
                            <Star className="w-3 h-3 text-[#ff6b1a] fill-[#ff6b1a]" />
                            <span className="text-white">{instructor.rating}</span>
                          </div>
                        </td>
                        <td className="px-4 py-3">
                          <button
                            onClick={() => toggleInstructorStatus(instructor.id)}
                            className={`px-2 py-0.5 rounded text-[10px] uppercase transition-colors ${
                              instructor.status === 'active'
                                ? 'bg-[#4ade80]/10 text-[#4ade80] hover:bg-[#4ade80]/20'
                                : 'bg-[#4a4a4a]/30 text-[#a0a0a0] hover:bg-[#4a4a4a]/50'
                            }`}
                          >
                            {instructor.status}
                          </button>
                        </td>
                        <td className="px-4 py-3">
                          <div className="flex gap-2">
                            <button className="text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors">
                              <Edit3 className="w-4 h-4" />
                            </button>
                            <button
                              onClick={() => removeInstructor(instructor.id)}
                              className="text-[#a0a0a0] hover:text-red-400 transition-colors"
                            >
                              <Trash2 className="w-4 h-4" />
                            </button>
                          </div>
                        </td>
                      </tr>
                    ))}
                  </tbody>
                </table>
              </div>
            </div>
          </div>
        )}

        {/* Stats Overview */}
        <div className="t8-section">
          <div className="grid grid-cols-2 md:grid-cols-4 gap-0 bg-[#1a1a1a] rounded-xl border border-[#2a2a2a] overflow-hidden">
            {[
              { value: '800+', label: 'Controllers', icon: TowerControl },
              { value: '50+', label: 'Trainers', icon: GraduationCap },
              { value: '200+', label: 'Sessions/Month', icon: BarChart3 },
              { value: '95%', label: 'Pass Rate', icon: Check },
            ].map((stat, i) => (
              <div
                key={i}
                className={`flex flex-col items-center justify-center py-8 px-4 ${
                  i < 3 ? 'border-r border-[#2a2a2a]' : ''
                }`}
              >
                <stat.icon className="w-5 h-5 text-[#ff6b1a] mb-2" />
                <span className="stat-number text-[24px]">{stat.value}</span>
                <span className="stat-label mt-1">{stat.label}</span>
              </div>
            ))}
          </div>
        </div>

        {/* Quick Access to FlightLine */}
        <div className="t8-section bg-[#1a1a1a] rounded-xl p-8 border border-[#2a2a2a] flex flex-col md:flex-row items-center justify-between gap-6">
          <div>
            <h3 className="text-xl font-semibold text-white mb-2">General Aviation Community?</h3>
            <p className="text-[15px] text-[#a0a0a0]">
              Join The FlightLine for MSFS, X-Plane, and Infinite Flight community events.
            </p>
          </div>
          <button
            onClick={() => navigate('/flightline')}
            className="btn-orange whitespace-nowrap flex items-center gap-2"
          >
            Go to The FlightLine
            <ArrowRight className="w-4 h-4" />
          </button>
        </div>
      </div>

      {/* Footer */}
      <footer className="bg-[#1a1a1a] py-12 px-6 mt-12">
        <div className="max-w-[1200px] mx-auto flex flex-col md:flex-row items-center justify-between gap-6">
          <div className="flex items-center gap-2">
            <Plane className="w-5 h-5 text-[#ff6b1a]" />
            <span className="text-white font-semibold tracking-[0.08em]">FLIGHT PLATFORM</span>
          </div>
          <div className="flex gap-6">
            <button onClick={() => navigate('/')} className="text-sm text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors">Home</button>
            <button onClick={() => navigate('/flightline')} className="text-sm text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors">The FlightLine</button>
            <button onClick={() => navigate('/tower8')} className="text-sm text-[#ff6b1a]">Tower8</button>
          </div>
          <p className="text-sm text-[#4a4a4a]">&copy; 2025 Flight Platform</p>
        </div>
      </footer>
    </div>
  );
}



================================================================================
FILE: app/src/lib/utils.ts
================================================================================

import { clsx, type ClassValue } from "clsx"
import { twMerge } from "tailwind-merge"

export function cn(...inputs: ClassValue[]) {
  return twMerge(clsx(inputs))
}



================================================================================
FILE: app/src/hooks/use-mobile.ts
================================================================================

import * as React from "react"

const MOBILE_BREAKPOINT = 768

export function useIsMobile() {
  const [isMobile, setIsMobile] = React.useState<boolean | undefined>(undefined)

  React.useEffect(() => {
    const mql = window.matchMedia(`(max-width: ${MOBILE_BREAKPOINT - 1}px)`)
    const onChange = () => {
      setIsMobile(window.innerWidth < MOBILE_BREAKPOINT)
    }
    mql.addEventListener("change", onChange)
    setIsMobile(window.innerWidth < MOBILE_BREAKPOINT)
    return () => mql.removeEventListener("change", onChange)
  }, [])

  return !!isMobile
}



================================================================================
FILE: app/src/context/AppContext.tsx
================================================================================

import React, { createContext, useContext, useState, useCallback } from 'react';

export interface TimeSlot {
  id: string;
  day: string;
  date: string;
  time: string;
  instructor: string;
  game: string;
  sessionType: 'tower' | 'approach' | 'ground' | 'center';
  status: 'available' | 'booked' | 'pending';
  trainee?: string;
}

export interface Instructor {
  id: string;
  name: string;
  role: string;
  games: string[];
  sessions: number;
  hours: number;
  rating: number;
  status: 'active' | 'inactive';
}

export interface AppState {
  selectedServer: 'flightline' | 'tower8' | null;
  selectedGame: string | null;
  selectedAircraft: string[];
  userRole: 'trainee' | 'instructor' | 'admin';
  instructors: Instructor[];
  timeSlots: TimeSlot[];
  bookings: TimeSlot[];
}

interface AppContextType {
  state: AppState;
  setSelectedServer: (server: 'flightline' | 'tower8' | null) => void;
  setSelectedGame: (game: string | null) => void;
  toggleAircraft: (aircraft: string) => void;
  setUserRole: (role: 'trainee' | 'instructor' | 'admin') => void;
  addInstructor: (instructor: Instructor) => void;
  removeInstructor: (id: string) => void;
  toggleInstructorStatus: (id: string) => void;
  bookSlot: (slotId: string) => void;
  cancelBooking: (slotId: string) => void;
  addTimeSlots: (slots: TimeSlot[]) => void;
}

const initialState: AppState = {
  selectedServer: null,
  selectedGame: null,
  selectedAircraft: [],
  userRole: 'trainee',
  instructors: [
    { id: '1', name: 'ATC_Master', role: 'Tower Instructor', games: ['PTFS', 'Project Flight'], sessions: 48, hours: 120, rating: 4.9, status: 'active' },
    { id: '2', name: 'SkyGuide', role: 'Approach Instructor', games: ['PTFS'], sessions: 32, hours: 85, rating: 4.8, status: 'active' },
    { id: '3', name: 'TowerPro', role: 'Ground Instructor', games: ['Project Flight'], sessions: 24, hours: 60, rating: 4.7, status: 'active' },
    { id: '4', name: 'RadarOps', role: 'Center Instructor', games: ['PTFS', 'Project Flight'], sessions: 56, hours: 140, rating: 5.0, status: 'active' },
  ],
  timeSlots: [
    { id: '1', day: 'Mon', date: 'May 19', time: '14:00 - 15:00', instructor: 'ATC_Master', game: 'PTFS', sessionType: 'tower', status: 'available' },
    { id: '2', day: 'Mon', date: 'May 19', time: '16:00 - 17:00', instructor: 'SkyGuide', game: 'PTFS', sessionType: 'approach', status: 'available' },
    { id: '3', day: 'Mon', date: 'May 19', time: '18:00 - 19:00', instructor: 'TowerPro', game: 'Project Flight', sessionType: 'ground', status: 'booked', trainee: 'Pilot123' },
    { id: '4', day: 'Tue', date: 'May 20', time: '14:00 - 15:00', instructor: 'RadarOps', game: 'PTFS', sessionType: 'center', status: 'available' },
    { id: '5', day: 'Tue', date: 'May 20', time: '16:00 - 17:00', instructor: 'ATC_Master', game: 'Project Flight', sessionType: 'tower', status: 'available' },
    { id: '6', day: 'Tue', date: 'May 20', time: '19:00 - 20:00', instructor: 'SkyGuide', game: 'PTFS', sessionType: 'approach', status: 'available' },
    { id: '7', day: 'Wed', date: 'May 21', time: '15:00 - 16:00', instructor: 'TowerPro', game: 'PTFS', sessionType: 'ground', status: 'available' },
    { id: '8', day: 'Wed', date: 'May 21', time: '17:00 - 18:00', instructor: 'RadarOps', game: 'Project Flight', sessionType: 'center', status: 'available' },
    { id: '9', day: 'Thu', date: 'May 22', time: '14:00 - 15:00', instructor: 'ATC_Master', game: 'PTFS', sessionType: 'tower', status: 'available' },
    { id: '10', day: 'Thu', date: 'May 22', time: '16:00 - 17:00', instructor: 'SkyGuide', game: 'Project Flight', sessionType: 'approach', status: 'booked', trainee: 'Aviator_X' },
    { id: '11', day: 'Fri', date: 'May 23', time: '15:00 - 16:00', instructor: 'TowerPro', game: 'PTFS', sessionType: 'ground', status: 'available' },
    { id: '12', day: 'Fri', date: 'May 23', time: '18:00 - 19:00', instructor: 'RadarOps', game: 'Project Flight', sessionType: 'center', status: 'available' },
  ],
  bookings: [],
};

const AppContext = createContext<AppContextType | undefined>(undefined);

export function AppProvider({ children }: { children: React.ReactNode }) {
  const [state, setState] = useState<AppState>(initialState);

  const setSelectedServer = useCallback((server: 'flightline' | 'tower8' | null) => {
    setState(prev => ({ ...prev, selectedServer: server }));
  }, []);

  const setSelectedGame = useCallback((game: string | null) => {
    setState(prev => ({ ...prev, selectedGame: game }));
  }, []);

  const toggleAircraft = useCallback((aircraft: string) => {
    setState(prev => ({
      ...prev,
      selectedAircraft: prev.selectedAircraft.includes(aircraft)
        ? prev.selectedAircraft.filter(a => a !== aircraft)
        : [...prev.selectedAircraft, aircraft],
    }));
  }, []);

  const setUserRole = useCallback((role: 'trainee' | 'instructor' | 'admin') => {
    setState(prev => ({ ...prev, userRole: role }));
  }, []);

  const addInstructor = useCallback((instructor: Instructor) => {
    setState(prev => ({
      ...prev,
      instructors: [...prev.instructors, instructor],
    }));
  }, []);

  const removeInstructor = useCallback((id: string) => {
    setState(prev => ({
      ...prev,
      instructors: prev.instructors.filter(i => i.id !== id),
    }));
  }, []);

  const toggleInstructorStatus = useCallback((id: string) => {
    setState(prev => ({
      ...prev,
      instructors: prev.instructors.map(i =>
        i.id === id ? { ...i, status: i.status === 'active' ? 'inactive' : 'active' } : i
      ),
    }));
  }, []);

  const bookSlot = useCallback((slotId: string) => {
    setState(prev => ({
      ...prev,
      timeSlots: prev.timeSlots.map(s =>
        s.id === slotId ? { ...s, status: 'booked' as const, trainee: 'You' } : s
      ),
      bookings: [...prev.bookings, prev.timeSlots.find(s => s.id === slotId)!].filter(Boolean),
    }));
  }, []);

  const cancelBooking = useCallback((slotId: string) => {
    setState(prev => ({
      ...prev,
      timeSlots: prev.timeSlots.map(s =>
        s.id === slotId ? { ...s, status: 'available' as const, trainee: undefined } : s
      ),
      bookings: prev.bookings.filter(b => b.id !== slotId),
    }));
  }, []);

  const addTimeSlots = useCallback((slots: TimeSlot[]) => {
    setState(prev => ({
      ...prev,
      timeSlots: [...prev.timeSlots, ...slots],
    }));
  }, []);

  return (
    <AppContext.Provider
      value={{
        state,
        setSelectedServer,
        setSelectedGame,
        toggleAircraft,
        setUserRole,
        addInstructor,
        removeInstructor,
        toggleInstructorStatus,
        bookSlot,
        cancelBooking,
        addTimeSlots,
      }}
    >
      {children}
    </AppContext.Provider>
  );
}

export function useApp() {
  const context = useContext(AppContext);
  if (context === undefined) {
    throw new Error('useApp must be used within an AppProvider');
  }
  return context;
}



================================================================================
FILE: app/src/components/InstrumentPanel.tsx
================================================================================

import { useEffect, useRef } from 'react';
import * as THREE from 'three';
import gsap from 'gsap';

export default function InstrumentPanel() {
  const containerRef = useRef<HTMLDivElement>(null);
  const rendererRef = useRef<THREE.WebGLRenderer | null>(null);

  useEffect(() => {
    if (!containerRef.current) return;
    const container = containerRef.current;

    // Scene setup
    const scene = new THREE.Scene();
    scene.background = new THREE.Color(0x0a0a0a);
    scene.fog = new THREE.Fog(0x0a0a0a, 10, 50);

    const camera = new THREE.PerspectiveCamera(
      45,
      container.clientWidth / container.clientHeight,
      0.1,
      100
    );
    camera.position.set(2, 1, 6);

    const renderer = new THREE.WebGLRenderer({ antialias: true, alpha: true });
    renderer.setSize(container.clientWidth, container.clientHeight);
    renderer.setPixelRatio(Math.min(window.devicePixelRatio, 2));
    renderer.shadowMap.enabled = true;
    renderer.shadowMap.type = THREE.PCFSoftShadowMap;
    renderer.toneMapping = THREE.ACESFilmicToneMapping;
    renderer.toneMappingExposure = 1.0;
    renderer.domElement.style.width = '100%';
    renderer.domElement.style.height = '100%';
    renderer.domElement.style.display = 'block';
    container.appendChild(renderer.domElement);
    rendererRef.current = renderer;

    // Mouse interaction
    let mouseX = 0;
    let mouseY = 0;

    const handleMouseMove = (e: MouseEvent) => {
      mouseX = (e.clientX - window.innerWidth / 2) * 0.0005;
      mouseY = (e.clientY - window.innerHeight / 2) * 0.0005;
    };
    document.addEventListener('mousemove', handleMouseMove);

    // Instrument group
    const instrumentGroup = new THREE.Group();
    scene.add(instrumentGroup);

    // Materials
    const casingMaterial = new THREE.MeshStandardMaterial({
      color: 0x1a1a1a,
      metalness: 0.9,
      roughness: 0.2,
    });
    const bezelMaterial = new THREE.MeshStandardMaterial({
      color: 0x2a2a2a,
      metalness: 0.95,
      roughness: 0.1,
    });
    const glassMaterial = new THREE.MeshPhysicalMaterial({
      color: 0xffffff,
      metalness: 0,
      roughness: 0,
      transmission: 0.95,
      thickness: 0.1,
      transparent: true,
      opacity: 0.3,
    });
    const faceMaterial = new THREE.MeshStandardMaterial({
      color: 0x050505,
      roughness: 0.8,
    });
    const tickMaterial = new THREE.MeshBasicMaterial({ color: 0xe0e0e0 });
    const drumMaterial = new THREE.MeshStandardMaterial({
      color: 0x0a0a0a,
      roughness: 0.5,
    });
    const needleMaterial = new THREE.MeshStandardMaterial({
      color: 0xff6b1a,
      metalness: 0.5,
      roughness: 0.3,
    });
    const hubMaterial = new THREE.MeshStandardMaterial({
      color: 0x2a2a2a,
      metalness: 0.9,
      roughness: 0.1,
    });
    const screwMaterial = new THREE.MeshStandardMaterial({
      color: 0x888888,
      metalness: 0.9,
      roughness: 0.2,
    });

    // 1. Outer Casing
    const casing = new THREE.Mesh(
      new THREE.CylinderGeometry(1.4, 1.4, 0.4, 64),
      casingMaterial
    );
    casing.rotation.x = Math.PI / 2;
    casing.castShadow = true;
    casing.receiveShadow = true;
    instrumentGroup.add(casing);

    // 2. Bezel Ring
    const bezel = new THREE.Mesh(
      new THREE.TorusGeometry(1.4, 0.08, 16, 100),
      bezelMaterial
    );
    instrumentGroup.add(bezel);

    // 3. Glass Cover
    const glass = new THREE.Mesh(
      new THREE.CircleGeometry(1.35, 64),
      glassMaterial
    );
    glass.position.z = 0.21;
    instrumentGroup.add(glass);

    // 4. Face Background
    const face = new THREE.Mesh(
      new THREE.CircleGeometry(1.3, 64),
      faceMaterial
    );
    face.position.z = 0.15;
    instrumentGroup.add(face);

    // 5. Tick Marks
    for (let tick = 0; tick < 360; tick += 5) {
      const angle = (tick * Math.PI) / 180;
      const isMajor = tick % 30 === 0;
      const length = isMajor ? 0.15 : 0.08;
      const width = isMajor ? 0.03 : 0.01;
      const tickMesh = new THREE.Mesh(
        new THREE.BoxGeometry(width, length, 0.01),
        tickMaterial
      );
      tickMesh.position.set(Math.cos(angle) * 1.1, Math.sin(angle) * 1.1, 0.16);
      tickMesh.rotation.z = angle;
      instrumentGroup.add(tickMesh);
    }

    // 6. Drum Counter Assembly (simplified without font)
    const drumGroup = new THREE.Group();
    drumGroup.position.set(0, -0.4, 0.18);
    instrumentGroup.add(drumGroup);

    const drums: { mesh: THREE.Mesh; update: (value: number) => void }[] = [];

    for (let d = 0; d < 3; d++) {
      const drumMesh = new THREE.Mesh(
        new THREE.CylinderGeometry(0.2, 0.2, 0.1, 32),
        drumMaterial
      );
      drumMesh.rotation.x = Math.PI / 2;
      drumMesh.position.set((d - 1) * 0.55, 0, 0);
      drumGroup.add(drumMesh);

      drums.push({
        mesh: drumMesh,
        update: (value: number) => {
          const displayValue = Math.floor(value) % 10;
          drumMesh.rotation.x = Math.PI / 2 + (displayValue / 10) * Math.PI * 2;
        },
      });
    }

    // 7. Drum Background
    const drumBg = new THREE.Mesh(
      new THREE.BoxGeometry(1.4, 0.5, 0.02),
      new THREE.MeshStandardMaterial({ color: 0x1a1a1a, metalness: 0.8, roughness: 0.3 })
    );
    drumBg.position.set(0, -0.4, 0.17);
    instrumentGroup.add(drumBg);

    // 8. Needle
    const needleGroup = new THREE.Group();
    needleGroup.position.z = 0.18;

    const needleBody = new THREE.Mesh(
      new THREE.BoxGeometry(0.04, 0.9, 0.02),
      needleMaterial
    );
    needleBody.position.y = 0.3;
    needleGroup.add(needleBody);

    const needleTail = new THREE.Mesh(
      new THREE.BoxGeometry(0.04, 0.3, 0.02),
      needleMaterial
    );
    needleTail.position.y = -0.15;
    needleGroup.add(needleTail);

    const hub = new THREE.Mesh(
      new THREE.SphereGeometry(0.08, 16, 16),
      hubMaterial
    );
    needleGroup.add(hub);

    instrumentGroup.add(needleGroup);

    // 9. Hub Cap
    const hubCap = new THREE.Mesh(
      new THREE.SphereGeometry(0.06, 16, 16),
      new THREE.MeshStandardMaterial({ color: 0x1a1a1a, metalness: 0.9, roughness: 0.1 })
    );
    hubCap.position.z = 0.22;
    instrumentGroup.add(hubCap);

    // 10. Screws
    const screwPositions = [
      [0.9, 0.9], [-0.9, 0.9], [0.9, -0.9], [-0.9, -0.9],
    ];
    screwPositions.forEach(([x, y]) => {
      const screw = new THREE.Mesh(
        new THREE.CylinderGeometry(0.04, 0.04, 0.02, 8),
        screwMaterial
      );
      screw.rotation.x = Math.PI / 2;
      screw.position.set(x, y, 0.22);
      instrumentGroup.add(screw);
    });

    // Lighting
    const ambientLight = new THREE.AmbientLight(0xffffff, 0.3);
    scene.add(ambientLight);

    const mainLight = new THREE.DirectionalLight(0xffffff, 1);
    mainLight.position.set(5, 5, 5);
    mainLight.castShadow = true;
    mainLight.shadow.mapSize.width = 1024;
    mainLight.shadow.mapSize.height = 1024;
    scene.add(mainLight);

    const orangeLight = new THREE.PointLight(0xff6b1a, 2, 10);
    orangeLight.position.set(-2, 1, 3);
    scene.add(orangeLight);

    const blueLight = new THREE.PointLight(0x4488ff, 0.5, 10);
    blueLight.position.set(2, -1, 2);
    scene.add(blueLight);

    const backLight = new THREE.DirectionalLight(0x445566, 0.5);
    backLight.position.set(-3, 2, -2);
    scene.add(backLight);

    // Camera animation
    gsap.from(camera.position, {
      z: 10,
      y: 3,
      x: 4,
      duration: 2.5,
      ease: 'power3.out',
    });

    gsap.from(instrumentGroup.rotation, {
      y: Math.PI,
      z: 0.2,
      duration: 3,
      ease: 'power2.out',
      delay: 0.2,
    });

    // Animation loop
    let time = 0;
    let altitude = 0;
    let targetAltitude = 0;
    let animationId: number;

    const animate = () => {
      animationId = requestAnimationFrame(animate);
      time += 0.01;

      targetAltitude = 5000 + Math.sin(time * 0.5) * 3000 + Math.sin(time * 0.1) * 1000;
      altitude += (targetAltitude - altitude) * 0.02;

      const altitudeInThousands = Math.floor(altitude / 1000);
      const digit1 = Math.floor(altitudeInThousands / 100) % 10;
      const digit2 = Math.floor(altitudeInThousands / 10) % 10;
      const digit3 = altitudeInThousands % 10;

      if (drums[0]) drums[0].update(digit1);
      if (drums[1]) drums[1].update(digit2);
      if (drums[2]) drums[2].update(digit3);

      needleGroup.rotation.z = -(altitude / 1000) * ((Math.PI * 2) / 10);

      // Mouse tilt
      instrumentGroup.rotation.y += (mouseX - instrumentGroup.rotation.y) * 0.05;
      instrumentGroup.rotation.x += (mouseY - instrumentGroup.rotation.x) * 0.05;

      renderer.render(scene, camera);
    };

    animate();

    // Resize handler
    const handleResize = () => {
      if (!container) return;
      camera.aspect = container.clientWidth / container.clientHeight;
      camera.updateProjectionMatrix();
      renderer.setSize(container.clientWidth, container.clientHeight);
    };
    window.addEventListener('resize', handleResize);

    return () => {
      cancelAnimationFrame(animationId);
      document.removeEventListener('mousemove', handleMouseMove);
      window.removeEventListener('resize', handleResize);
      renderer.dispose();
      if (container.contains(renderer.domElement)) {
        container.removeChild(renderer.domElement);
      }
    };
  }, []);

  return (
    <div
      ref={containerRef}
      style={{
        position: 'absolute',
        inset: 0,
        zIndex: 0,
      }}
    />
  );
}



================================================================================
FILE: app/src/components/Navbar.tsx
================================================================================

import { useNavigate, useLocation } from 'react-router-dom';
import { useApp } from '@/context/AppContext';
import { Plane, TowerControl, Menu, X, Shield } from 'lucide-react';
import { useState } from 'react';

export default function Navbar() {
  const navigate = useNavigate();
  const location = useLocation();
  const { state, setUserRole } = useApp();
  const [mobileOpen, setMobileOpen] = useState(false);
  const [roleMenuOpen, setRoleMenuOpen] = useState(false);

  const isHub = location.pathname === '/';

  return (
    <nav className="fixed top-0 left-0 right-0 z-50 h-16 flex items-center px-6"
      style={{ background: 'rgba(10, 10, 10, 0.9)', backdropFilter: 'blur(12px)' }}>
      <div className="max-w-[1200px] mx-auto w-full flex items-center justify-between">
        {/* Logo */}
        <button
          onClick={() => navigate('/')}
          className="flex items-center gap-2 group"
        >
          <Plane className="w-5 h-5 text-[#ff6b1a] transition-transform group-hover:rotate-12" />
          <span className="text-white font-semibold text-lg tracking-[0.08em]">
            FLIGHT PLATFORM
          </span>
        </button>

        {/* Center nav links */}
        <div className="hidden md:flex items-center gap-8">
          <button
            onClick={() => navigate('/')}
            className={`text-sm font-medium transition-colors hover:text-[#ff6b1a] ${isHub ? 'text-[#ff6b1a]' : 'text-[#a0a0a0]'}`}
          >
            Home
          </button>
          <button
            onClick={() => navigate('/flightline')}
            className={`text-sm font-medium transition-colors hover:text-[#ff6b1a] flex items-center gap-1.5 ${location.pathname === '/flightline' ? 'text-[#ff6b1a]' : 'text-[#a0a0a0]'}`}
          >
            <Plane className="w-3.5 h-3.5" />
            The FlightLine
          </button>
          <button
            onClick={() => navigate('/tower8')}
            className={`text-sm font-medium transition-colors hover:text-[#ff6b1a] flex items-center gap-1.5 ${location.pathname === '/tower8' ? 'text-[#ff6b1a]' : 'text-[#a0a0a0]'}`}
          >
            <TowerControl className="w-3.5 h-3.5" />
            Tower8
          </button>
        </div>

        {/* Right side */}
        <div className="hidden md:flex items-center gap-4">
          {/* Role switcher */}
          <div className="relative">
            <button
              onClick={() => setRoleMenuOpen(!roleMenuOpen)}
              className="flex items-center gap-2 text-sm text-[#a0a0a0] hover:text-[#ff6b1a] transition-colors"
            >
              <Shield className="w-4 h-4" />
              <span className="capitalize">{state.userRole}</span>
            </button>
            {roleMenuOpen && (
              <div className="absolute right-0 top-full mt-2 bg-[#1a1a1a] border border-[#2a2a2a] rounded-lg py-1 min-w-[140px] shadow-xl">
                {(['trainee', 'instructor', 'admin'] as const).map(role => (
                  <button
                    key={role}
                    onClick={() => { setUserRole(role); setRoleMenuOpen(false); }}
                    className={`w-full text-left px-4 py-2 text-sm capitalize transition-colors hover:bg-[#2a2a2a] ${state.userRole === role ? 'text-[#ff6b1a]' : 'text-[#a0a0a0]'}`}
                  >
                    {role}
                  </button>
                ))}
              </div>
            )}
          </div>

          <button className="btn-bordered py-2 px-5 text-xs h-9">
            Discord Login
          </button>
        </div>

        {/* Mobile hamburger */}
        <button
          onClick={() => setMobileOpen(!mobileOpen)}
          className="md:hidden text-white"
        >
          {mobileOpen ? <X className="w-6 h-6" /> : <Menu className="w-6 h-6" />}
        </button>
      </div>

      {/* Mobile drawer */}
      {mobileOpen && (
        <div className="fixed inset-0 top-16 bg-[#0a0a0a] z-40 md:hidden p-6">
          <div className="flex flex-col gap-6">
            <button
              onClick={() => { navigate('/'); setMobileOpen(false); }}
              className="text-left text-lg text-white"
            >
              Home
            </button>
            <button
              onClick={() => { navigate('/flightline'); setMobileOpen(false); }}
              className="text-left text-lg text-white flex items-center gap-2"
            >
              <Plane className="w-5 h-5 text-[#ff6b1a]" />
              The FlightLine
            </button>
            <button
              onClick={() => { navigate('/tower8'); setMobileOpen(false); }}
              className="text-left text-lg text-white flex items-center gap-2"
            >
              <TowerControl className="w-5 h-5 text-[#ff6b1a]" />
              Tower8
            </button>
            <div className="pt-4 border-t border-[#2a2a2a]">
              <p className="caption mb-3">Role</p>
              <div className="flex gap-2 flex-wrap">
                {(['trainee', 'instructor', 'admin'] as const).map(role => (
                  <button
                    key={role}
                    onClick={() => { setUserRole(role); }}
                    className={`px-4 py-2 rounded-lg text-sm capitalize border ${state.userRole === role ? 'border-[#ff6b1a] text-[#ff6b1a]' : 'border-[#2a2a2a] text-[#a0a0a0]'}`}
                  >
                    {role}
                  </button>
                ))}
              </div>
            </div>
            <button className="btn-bordered mt-4">Discord Login</button>
          </div>
        </div>
      )}
    </nav>
  );
}



================================================================================
FILE: app/src/components/ui/accordion.tsx
================================================================================

import * as React from "react"
import * as AccordionPrimitive from "@radix-ui/react-accordion"
import { ChevronDownIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function Accordion({
  ...props
}: React.ComponentProps<typeof AccordionPrimitive.Root>) {
  return <AccordionPrimitive.Root data-slot="accordion" {...props} />
}

function AccordionItem({
  className,
  ...props
}: React.ComponentProps<typeof AccordionPrimitive.Item>) {
  return (
    <AccordionPrimitive.Item
      data-slot="accordion-item"
      className={cn("border-b last:border-b-0", className)}
      {...props}
    />
  )
}

function AccordionTrigger({
  className,
  children,
  ...props
}: React.ComponentProps<typeof AccordionPrimitive.Trigger>) {
  return (
    <AccordionPrimitive.Header className="flex">
      <AccordionPrimitive.Trigger
        data-slot="accordion-trigger"
        className={cn(
          "focus-visible:border-ring focus-visible:ring-ring/50 flex flex-1 items-start justify-between gap-4 rounded-md py-4 text-left text-sm font-medium transition-all outline-none hover:underline focus-visible:ring-[3px] disabled:pointer-events-none disabled:opacity-50 [&[data-state=open]>svg]:rotate-180",
          className
        )}
        {...props}
      >
        {children}
        <ChevronDownIcon className="text-muted-foreground pointer-events-none size-4 shrink-0 translate-y-0.5 transition-transform duration-200" />
      </AccordionPrimitive.Trigger>
    </AccordionPrimitive.Header>
  )
}

function AccordionContent({
  className,
  children,
  ...props
}: React.ComponentProps<typeof AccordionPrimitive.Content>) {
  return (
    <AccordionPrimitive.Content
      data-slot="accordion-content"
      className="data-[state=closed]:animate-accordion-up data-[state=open]:animate-accordion-down overflow-hidden text-sm"
      {...props}
    >
      <div className={cn("pt-0 pb-4", className)}>{children}</div>
    </AccordionPrimitive.Content>
  )
}

export { Accordion, AccordionItem, AccordionTrigger, AccordionContent }



================================================================================
FILE: app/src/components/ui/alert-dialog.tsx
================================================================================

import * as React from "react"
import * as AlertDialogPrimitive from "@radix-ui/react-alert-dialog"

import { cn } from "@/lib/utils"
import { buttonVariants } from "@/components/ui/button"

function AlertDialog({
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Root>) {
  return <AlertDialogPrimitive.Root data-slot="alert-dialog" {...props} />
}

function AlertDialogTrigger({
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Trigger>) {
  return (
    <AlertDialogPrimitive.Trigger data-slot="alert-dialog-trigger" {...props} />
  )
}

function AlertDialogPortal({
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Portal>) {
  return (
    <AlertDialogPrimitive.Portal data-slot="alert-dialog-portal" {...props} />
  )
}

function AlertDialogOverlay({
  className,
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Overlay>) {
  return (
    <AlertDialogPrimitive.Overlay
      data-slot="alert-dialog-overlay"
      className={cn(
        "data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 fixed inset-0 z-50 bg-black/50",
        className
      )}
      {...props}
    />
  )
}

function AlertDialogContent({
  className,
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Content>) {
  return (
    <AlertDialogPortal>
      <AlertDialogOverlay />
      <AlertDialogPrimitive.Content
        data-slot="alert-dialog-content"
        className={cn(
          "bg-background data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 fixed top-[50%] left-[50%] z-50 grid w-full max-w-[calc(100%-2rem)] translate-x-[-50%] translate-y-[-50%] gap-4 rounded-lg border p-6 shadow-lg duration-200 sm:max-w-lg",
          className
        )}
        {...props}
      />
    </AlertDialogPortal>
  )
}

function AlertDialogHeader({
  className,
  ...props
}: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="alert-dialog-header"
      className={cn("flex flex-col gap-2 text-center sm:text-left", className)}
      {...props}
    />
  )
}

function AlertDialogFooter({
  className,
  ...props
}: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="alert-dialog-footer"
      className={cn(
        "flex flex-col-reverse gap-2 sm:flex-row sm:justify-end",
        className
      )}
      {...props}
    />
  )
}

function AlertDialogTitle({
  className,
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Title>) {
  return (
    <AlertDialogPrimitive.Title
      data-slot="alert-dialog-title"
      className={cn("text-lg font-semibold", className)}
      {...props}
    />
  )
}

function AlertDialogDescription({
  className,
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Description>) {
  return (
    <AlertDialogPrimitive.Description
      data-slot="alert-dialog-description"
      className={cn("text-muted-foreground text-sm", className)}
      {...props}
    />
  )
}

function AlertDialogAction({
  className,
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Action>) {
  return (
    <AlertDialogPrimitive.Action
      className={cn(buttonVariants(), className)}
      {...props}
    />
  )
}

function AlertDialogCancel({
  className,
  ...props
}: React.ComponentProps<typeof AlertDialogPrimitive.Cancel>) {
  return (
    <AlertDialogPrimitive.Cancel
      className={cn(buttonVariants({ variant: "outline" }), className)}
      {...props}
    />
  )
}

export {
  AlertDialog,
  AlertDialogPortal,
  AlertDialogOverlay,
  AlertDialogTrigger,
  AlertDialogContent,
  AlertDialogHeader,
  AlertDialogFooter,
  AlertDialogTitle,
  AlertDialogDescription,
  AlertDialogAction,
  AlertDialogCancel,
}



================================================================================
FILE: app/src/components/ui/alert.tsx
================================================================================

import * as React from "react"
import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"

const alertVariants = cva(
  "relative w-full rounded-lg border px-4 py-3 text-sm grid has-[>svg]:grid-cols-[calc(var(--spacing)*4)_1fr] grid-cols-[0_1fr] has-[>svg]:gap-x-3 gap-y-0.5 items-start [&>svg]:size-4 [&>svg]:translate-y-0.5 [&>svg]:text-current",
  {
    variants: {
      variant: {
        default: "bg-card text-card-foreground",
        destructive:
          "text-destructive bg-card [&>svg]:text-current *:data-[slot=alert-description]:text-destructive/90",
      },
    },
    defaultVariants: {
      variant: "default",
    },
  }
)

function Alert({
  className,
  variant,
  ...props
}: React.ComponentProps<"div"> & VariantProps<typeof alertVariants>) {
  return (
    <div
      data-slot="alert"
      role="alert"
      className={cn(alertVariants({ variant }), className)}
      {...props}
    />
  )
}

function AlertTitle({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="alert-title"
      className={cn(
        "col-start-2 line-clamp-1 min-h-4 font-medium tracking-tight",
        className
      )}
      {...props}
    />
  )
}

function AlertDescription({
  className,
  ...props
}: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="alert-description"
      className={cn(
        "text-muted-foreground col-start-2 grid justify-items-start gap-1 text-sm [&_p]:leading-relaxed",
        className
      )}
      {...props}
    />
  )
}

export { Alert, AlertTitle, AlertDescription }



================================================================================
FILE: app/src/components/ui/aspect-ratio.tsx
================================================================================

"use client"

import * as AspectRatioPrimitive from "@radix-ui/react-aspect-ratio"

function AspectRatio({
  ...props
}: React.ComponentProps<typeof AspectRatioPrimitive.Root>) {
  return <AspectRatioPrimitive.Root data-slot="aspect-ratio" {...props} />
}

export { AspectRatio }



================================================================================
FILE: app/src/components/ui/avatar.tsx
================================================================================

import * as React from "react"
import * as AvatarPrimitive from "@radix-ui/react-avatar"

import { cn } from "@/lib/utils"

function Avatar({
  className,
  ...props
}: React.ComponentProps<typeof AvatarPrimitive.Root>) {
  return (
    <AvatarPrimitive.Root
      data-slot="avatar"
      className={cn(
        "relative flex size-8 shrink-0 overflow-hidden rounded-full",
        className
      )}
      {...props}
    />
  )
}

function AvatarImage({
  className,
  ...props
}: React.ComponentProps<typeof AvatarPrimitive.Image>) {
  return (
    <AvatarPrimitive.Image
      data-slot="avatar-image"
      className={cn("aspect-square size-full", className)}
      {...props}
    />
  )
}

function AvatarFallback({
  className,
  ...props
}: React.ComponentProps<typeof AvatarPrimitive.Fallback>) {
  return (
    <AvatarPrimitive.Fallback
      data-slot="avatar-fallback"
      className={cn(
        "bg-muted flex size-full items-center justify-center rounded-full",
        className
      )}
      {...props}
    />
  )
}

export { Avatar, AvatarImage, AvatarFallback }



================================================================================
FILE: app/src/components/ui/badge.tsx
================================================================================

import * as React from "react"
import { Slot } from "@radix-ui/react-slot"
import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"

const badgeVariants = cva(
  "inline-flex items-center justify-center rounded-full border px-2 py-0.5 text-xs font-medium w-fit whitespace-nowrap shrink-0 [&>svg]:size-3 gap-1 [&>svg]:pointer-events-none focus-visible:border-ring focus-visible:ring-ring/50 focus-visible:ring-[3px] aria-invalid:ring-destructive/20 dark:aria-invalid:ring-destructive/40 aria-invalid:border-destructive transition-[color,box-shadow] overflow-hidden",
  {
    variants: {
      variant: {
        default:
          "border-transparent bg-primary text-primary-foreground [a&]:hover:bg-primary/90",
        secondary:
          "border-transparent bg-secondary text-secondary-foreground [a&]:hover:bg-secondary/90",
        destructive:
          "border-transparent bg-destructive text-white [a&]:hover:bg-destructive/90 focus-visible:ring-destructive/20 dark:focus-visible:ring-destructive/40 dark:bg-destructive/60",
        outline:
          "text-foreground [a&]:hover:bg-accent [a&]:hover:text-accent-foreground",
      },
    },
    defaultVariants: {
      variant: "default",
    },
  }
)

function Badge({
  className,
  variant,
  asChild = false,
  ...props
}: React.ComponentProps<"span"> &
  VariantProps<typeof badgeVariants> & { asChild?: boolean }) {
  const Comp = asChild ? Slot : "span"

  return (
    <Comp
      data-slot="badge"
      className={cn(badgeVariants({ variant }), className)}
      {...props}
    />
  )
}

export { Badge, badgeVariants }



================================================================================
FILE: app/src/components/ui/breadcrumb.tsx
================================================================================

import * as React from "react"
import { Slot } from "@radix-ui/react-slot"
import { ChevronRight, MoreHorizontal } from "lucide-react"

import { cn } from "@/lib/utils"

function Breadcrumb({ ...props }: React.ComponentProps<"nav">) {
  return <nav aria-label="breadcrumb" data-slot="breadcrumb" {...props} />
}

function BreadcrumbList({ className, ...props }: React.ComponentProps<"ol">) {
  return (
    <ol
      data-slot="breadcrumb-list"
      className={cn(
        "text-muted-foreground flex flex-wrap items-center gap-1.5 text-sm break-words sm:gap-2.5",
        className
      )}
      {...props}
    />
  )
}

function BreadcrumbItem({ className, ...props }: React.ComponentProps<"li">) {
  return (
    <li
      data-slot="breadcrumb-item"
      className={cn("inline-flex items-center gap-1.5", className)}
      {...props}
    />
  )
}

function BreadcrumbLink({
  asChild,
  className,
  ...props
}: React.ComponentProps<"a"> & {
  asChild?: boolean
}) {
  const Comp = asChild ? Slot : "a"

  return (
    <Comp
      data-slot="breadcrumb-link"
      className={cn("hover:text-foreground transition-colors", className)}
      {...props}
    />
  )
}

function BreadcrumbPage({ className, ...props }: React.ComponentProps<"span">) {
  return (
    <span
      data-slot="breadcrumb-page"
      role="link"
      aria-disabled="true"
      aria-current="page"
      className={cn("text-foreground font-normal", className)}
      {...props}
    />
  )
}

function BreadcrumbSeparator({
  children,
  className,
  ...props
}: React.ComponentProps<"li">) {
  return (
    <li
      data-slot="breadcrumb-separator"
      role="presentation"
      aria-hidden="true"
      className={cn("[&>svg]:size-3.5", className)}
      {...props}
    >
      {children ?? <ChevronRight />}
    </li>
  )
}

function BreadcrumbEllipsis({
  className,
  ...props
}: React.ComponentProps<"span">) {
  return (
    <span
      data-slot="breadcrumb-ellipsis"
      role="presentation"
      aria-hidden="true"
      className={cn("flex size-9 items-center justify-center", className)}
      {...props}
    >
      <MoreHorizontal className="size-4" />
      <span className="sr-only">More</span>
    </span>
  )
}

export {
  Breadcrumb,
  BreadcrumbList,
  BreadcrumbItem,
  BreadcrumbLink,
  BreadcrumbPage,
  BreadcrumbSeparator,
  BreadcrumbEllipsis,
}



================================================================================
FILE: app/src/components/ui/button-group.tsx
================================================================================

import { Slot } from "@radix-ui/react-slot"
import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"
import { Separator } from "@/components/ui/separator"

const buttonGroupVariants = cva(
  "flex w-fit items-stretch [&>*]:focus-visible:z-10 [&>*]:focus-visible:relative [&>[data-slot=select-trigger]:not([class*='w-'])]:w-fit [&>input]:flex-1 has-[select[aria-hidden=true]:last-child]:[&>[data-slot=select-trigger]:last-of-type]:rounded-r-md has-[>[data-slot=button-group]]:gap-2",
  {
    variants: {
      orientation: {
        horizontal:
          "[&>*:not(:first-child)]:rounded-l-none [&>*:not(:first-child)]:border-l-0 [&>*:not(:last-child)]:rounded-r-none",
        vertical:
          "flex-col [&>*:not(:first-child)]:rounded-t-none [&>*:not(:first-child)]:border-t-0 [&>*:not(:last-child)]:rounded-b-none",
      },
    },
    defaultVariants: {
      orientation: "horizontal",
    },
  }
)

function ButtonGroup({
  className,
  orientation,
  ...props
}: React.ComponentProps<"div"> & VariantProps<typeof buttonGroupVariants>) {
  return (
    <div
      role="group"
      data-slot="button-group"
      data-orientation={orientation}
      className={cn(buttonGroupVariants({ orientation }), className)}
      {...props}
    />
  )
}

function ButtonGroupText({
  className,
  asChild = false,
  ...props
}: React.ComponentProps<"div"> & {
  asChild?: boolean
}) {
  const Comp = asChild ? Slot : "div"

  return (
    <Comp
      className={cn(
        "bg-muted flex items-center gap-2 rounded-md border px-4 text-sm font-medium shadow-xs [&_svg]:pointer-events-none [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    />
  )
}

function ButtonGroupSeparator({
  className,
  orientation = "vertical",
  ...props
}: React.ComponentProps<typeof Separator>) {
  return (
    <Separator
      data-slot="button-group-separator"
      orientation={orientation}
      className={cn(
        "bg-input relative !m-0 self-stretch data-[orientation=vertical]:h-auto",
        className
      )}
      {...props}
    />
  )
}

export {
  ButtonGroup,
  ButtonGroupSeparator,
  ButtonGroupText,
  buttonGroupVariants,
}



================================================================================
FILE: app/src/components/ui/button.tsx
================================================================================

import * as React from "react"
import { Slot } from "@radix-ui/react-slot"
import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"

const buttonVariants = cva(
  "inline-flex items-center justify-center gap-2 whitespace-nowrap rounded-md text-sm font-medium transition-all disabled:pointer-events-none disabled:opacity-50 [&_svg]:pointer-events-none [&_svg:not([class*='size-'])]:size-4 shrink-0 [&_svg]:shrink-0 outline-none focus-visible:border-ring focus-visible:ring-ring/50 focus-visible:ring-[3px] aria-invalid:ring-destructive/20 dark:aria-invalid:ring-destructive/40 aria-invalid:border-destructive",
  {
    variants: {
      variant: {
        default: "bg-primary text-primary-foreground hover:bg-primary/90",
        destructive:
          "bg-destructive text-white hover:bg-destructive/90 focus-visible:ring-destructive/20 dark:focus-visible:ring-destructive/40 dark:bg-destructive/60",
        outline:
          "border bg-background shadow-xs hover:bg-accent hover:text-accent-foreground dark:bg-input/30 dark:border-input dark:hover:bg-input/50",
        secondary:
          "bg-secondary text-secondary-foreground hover:bg-secondary/80",
        ghost:
          "hover:bg-accent hover:text-accent-foreground dark:hover:bg-accent/50",
        link: "text-primary underline-offset-4 hover:underline",
      },
      size: {
        default: "h-9 px-4 py-2 has-[>svg]:px-3",
        sm: "h-8 rounded-md gap-1.5 px-3 has-[>svg]:px-2.5",
        lg: "h-10 rounded-md px-6 has-[>svg]:px-4",
        icon: "size-9",
        "icon-sm": "size-8",
        "icon-lg": "size-10",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
)

function Button({
  className,
  variant = "default",
  size = "default",
  asChild = false,
  ...props
}: React.ComponentProps<"button"> &
  VariantProps<typeof buttonVariants> & {
    asChild?: boolean
  }) {
  const Comp = asChild ? Slot : "button"

  return (
    <Comp
      data-slot="button"
      data-variant={variant}
      data-size={size}
      className={cn(buttonVariants({ variant, size, className }))}
      {...props}
    />
  )
}

export { Button, buttonVariants }



================================================================================
FILE: app/src/components/ui/calendar.tsx
================================================================================

"use client"

import * as React from "react"
import {
  ChevronDownIcon,
  ChevronLeftIcon,
  ChevronRightIcon,
} from "lucide-react"
import {
  DayPicker,
  getDefaultClassNames,
  type DayButton,
} from "react-day-picker"

import { cn } from "@/lib/utils"
import { Button, buttonVariants } from "@/components/ui/button"

function Calendar({
  className,
  classNames,
  showOutsideDays = true,
  captionLayout = "label",
  buttonVariant = "ghost",
  formatters,
  components,
  ...props
}: React.ComponentProps<typeof DayPicker> & {
  buttonVariant?: React.ComponentProps<typeof Button>["variant"]
}) {
  const defaultClassNames = getDefaultClassNames()

  return (
    <DayPicker
      showOutsideDays={showOutsideDays}
      className={cn(
        "bg-background group/calendar p-3 [--cell-size:--spacing(8)] [[data-slot=card-content]_&]:bg-transparent [[data-slot=popover-content]_&]:bg-transparent",
        String.raw`rtl:**:[.rdp-button\_next>svg]:rotate-180`,
        String.raw`rtl:**:[.rdp-button\_previous>svg]:rotate-180`,
        className
      )}
      captionLayout={captionLayout}
      formatters={{
        formatMonthDropdown: (date) =>
          date.toLocaleString("default", { month: "short" }),
        ...formatters,
      }}
      classNames={{
        root: cn("w-fit", defaultClassNames.root),
        months: cn(
          "flex gap-4 flex-col md:flex-row relative",
          defaultClassNames.months
        ),
        month: cn("flex flex-col w-full gap-4", defaultClassNames.month),
        nav: cn(
          "flex items-center gap-1 w-full absolute top-0 inset-x-0 justify-between",
          defaultClassNames.nav
        ),
        button_previous: cn(
          buttonVariants({ variant: buttonVariant }),
          "size-(--cell-size) aria-disabled:opacity-50 p-0 select-none",
          defaultClassNames.button_previous
        ),
        button_next: cn(
          buttonVariants({ variant: buttonVariant }),
          "size-(--cell-size) aria-disabled:opacity-50 p-0 select-none",
          defaultClassNames.button_next
        ),
        month_caption: cn(
          "flex items-center justify-center h-(--cell-size) w-full px-(--cell-size)",
          defaultClassNames.month_caption
        ),
        dropdowns: cn(
          "w-full flex items-center text-sm font-medium justify-center h-(--cell-size) gap-1.5",
          defaultClassNames.dropdowns
        ),
        dropdown_root: cn(
          "relative has-focus:border-ring border border-input shadow-xs has-focus:ring-ring/50 has-focus:ring-[3px] rounded-md",
          defaultClassNames.dropdown_root
        ),
        dropdown: cn(
          "absolute bg-popover inset-0 opacity-0",
          defaultClassNames.dropdown
        ),
        caption_label: cn(
          "select-none font-medium",
          captionLayout === "label"
            ? "text-sm"
            : "rounded-md pl-2 pr-1 flex items-center gap-1 text-sm h-8 [&>svg]:text-muted-foreground [&>svg]:size-3.5",
          defaultClassNames.caption_label
        ),
        table: "w-full border-collapse",
        weekdays: cn("flex", defaultClassNames.weekdays),
        weekday: cn(
          "text-muted-foreground rounded-md flex-1 font-normal text-[0.8rem] select-none",
          defaultClassNames.weekday
        ),
        week: cn("flex w-full mt-2", defaultClassNames.week),
        week_number_header: cn(
          "select-none w-(--cell-size)",
          defaultClassNames.week_number_header
        ),
        week_number: cn(
          "text-[0.8rem] select-none text-muted-foreground",
          defaultClassNames.week_number
        ),
        day: cn(
          "relative w-full h-full p-0 text-center [&:last-child[data-selected=true]_button]:rounded-r-md group/day aspect-square select-none",
          props.showWeekNumber
            ? "[&:nth-child(2)[data-selected=true]_button]:rounded-l-md"
            : "[&:first-child[data-selected=true]_button]:rounded-l-md",
          defaultClassNames.day
        ),
        range_start: cn(
          "rounded-l-md bg-accent",
          defaultClassNames.range_start
        ),
        range_middle: cn("rounded-none", defaultClassNames.range_middle),
        range_end: cn("rounded-r-md bg-accent", defaultClassNames.range_end),
        today: cn(
          "bg-accent text-accent-foreground rounded-md data-[selected=true]:rounded-none",
          defaultClassNames.today
        ),
        outside: cn(
          "text-muted-foreground aria-selected:text-muted-foreground",
          defaultClassNames.outside
        ),
        disabled: cn(
          "text-muted-foreground opacity-50",
          defaultClassNames.disabled
        ),
        hidden: cn("invisible", defaultClassNames.hidden),
        ...classNames,
      }}
      components={{
        Root: ({ className, rootRef, ...props }) => {
          return (
            <div
              data-slot="calendar"
              ref={rootRef}
              className={cn(className)}
              {...props}
            />
          )
        },
        Chevron: ({ className, orientation, ...props }) => {
          if (orientation === "left") {
            return (
              <ChevronLeftIcon className={cn("size-4", className)} {...props} />
            )
          }

          if (orientation === "right") {
            return (
              <ChevronRightIcon
                className={cn("size-4", className)}
                {...props}
              />
            )
          }

          return (
            <ChevronDownIcon className={cn("size-4", className)} {...props} />
          )
        },
        DayButton: CalendarDayButton,
        WeekNumber: ({ children, ...props }) => {
          return (
            <td {...props}>
              <div className="flex size-(--cell-size) items-center justify-center text-center">
                {children}
              </div>
            </td>
          )
        },
        ...components,
      }}
      {...props}
    />
  )
}

function CalendarDayButton({
  className,
  day,
  modifiers,
  ...props
}: React.ComponentProps<typeof DayButton>) {
  const defaultClassNames = getDefaultClassNames()

  const ref = React.useRef<HTMLButtonElement>(null)
  React.useEffect(() => {
    if (modifiers.focused) ref.current?.focus()
  }, [modifiers.focused])

  return (
    <Button
      ref={ref}
      variant="ghost"
      size="icon"
      data-day={day.date.toLocaleDateString()}
      data-selected-single={
        modifiers.selected &&
        !modifiers.range_start &&
        !modifiers.range_end &&
        !modifiers.range_middle
      }
      data-range-start={modifiers.range_start}
      data-range-end={modifiers.range_end}
      data-range-middle={modifiers.range_middle}
      className={cn(
        "data-[selected-single=true]:bg-primary data-[selected-single=true]:text-primary-foreground data-[range-middle=true]:bg-accent data-[range-middle=true]:text-accent-foreground data-[range-start=true]:bg-primary data-[range-start=true]:text-primary-foreground data-[range-end=true]:bg-primary data-[range-end=true]:text-primary-foreground group-data-[focused=true]/day:border-ring group-data-[focused=true]/day:ring-ring/50 dark:hover:text-accent-foreground flex aspect-square size-auto w-full min-w-(--cell-size) flex-col gap-1 leading-none font-normal group-data-[focused=true]/day:relative group-data-[focused=true]/day:z-10 group-data-[focused=true]/day:ring-[3px] data-[range-end=true]:rounded-md data-[range-end=true]:rounded-r-md data-[range-middle=true]:rounded-none data-[range-start=true]:rounded-md data-[range-start=true]:rounded-l-md [&>span]:text-xs [&>span]:opacity-70",
        defaultClassNames.day,
        className
      )}
      {...props}
    />
  )
}

export { Calendar, CalendarDayButton }



================================================================================
FILE: app/src/components/ui/card.tsx
================================================================================

import * as React from "react"

import { cn } from "@/lib/utils"

function Card({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="card"
      className={cn(
        "bg-card text-card-foreground flex flex-col gap-6 rounded-xl border py-6 shadow-sm",
        className
      )}
      {...props}
    />
  )
}

function CardHeader({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="card-header"
      className={cn(
        "@container/card-header grid auto-rows-min grid-rows-[auto_auto] items-start gap-2 px-6 has-data-[slot=card-action]:grid-cols-[1fr_auto] [.border-b]:pb-6",
        className
      )}
      {...props}
    />
  )
}

function CardTitle({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="card-title"
      className={cn("leading-none font-semibold", className)}
      {...props}
    />
  )
}

function CardDescription({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="card-description"
      className={cn("text-muted-foreground text-sm", className)}
      {...props}
    />
  )
}

function CardAction({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="card-action"
      className={cn(
        "col-start-2 row-span-2 row-start-1 self-start justify-self-end",
        className
      )}
      {...props}
    />
  )
}

function CardContent({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="card-content"
      className={cn("px-6", className)}
      {...props}
    />
  )
}

function CardFooter({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="card-footer"
      className={cn("flex items-center px-6 [.border-t]:pt-6", className)}
      {...props}
    />
  )
}

export {
  Card,
  CardHeader,
  CardFooter,
  CardTitle,
  CardAction,
  CardDescription,
  CardContent,
}



================================================================================
FILE: app/src/components/ui/carousel.tsx
================================================================================

import * as React from "react"
import useEmblaCarousel, {
  type UseEmblaCarouselType,
} from "embla-carousel-react"
import { ArrowLeft, ArrowRight } from "lucide-react"

import { cn } from "@/lib/utils"
import { Button } from "@/components/ui/button"

type CarouselApi = UseEmblaCarouselType[1]
type UseCarouselParameters = Parameters<typeof useEmblaCarousel>
type CarouselOptions = UseCarouselParameters[0]
type CarouselPlugin = UseCarouselParameters[1]

type CarouselProps = {
  opts?: CarouselOptions
  plugins?: CarouselPlugin
  orientation?: "horizontal" | "vertical"
  setApi?: (api: CarouselApi) => void
}

type CarouselContextProps = {
  carouselRef: ReturnType<typeof useEmblaCarousel>[0]
  api: ReturnType<typeof useEmblaCarousel>[1]
  scrollPrev: () => void
  scrollNext: () => void
  canScrollPrev: boolean
  canScrollNext: boolean
} & CarouselProps

const CarouselContext = React.createContext<CarouselContextProps | null>(null)

function useCarousel() {
  const context = React.useContext(CarouselContext)

  if (!context) {
    throw new Error("useCarousel must be used within a <Carousel />")
  }

  return context
}

function Carousel({
  orientation = "horizontal",
  opts,
  setApi,
  plugins,
  className,
  children,
  ...props
}: React.ComponentProps<"div"> & CarouselProps) {
  const [carouselRef, api] = useEmblaCarousel(
    {
      ...opts,
      axis: orientation === "horizontal" ? "x" : "y",
    },
    plugins
  )
  const [canScrollPrev, setCanScrollPrev] = React.useState(false)
  const [canScrollNext, setCanScrollNext] = React.useState(false)

  const onSelect = React.useCallback((api: CarouselApi) => {
    if (!api) return
    setCanScrollPrev(api.canScrollPrev())
    setCanScrollNext(api.canScrollNext())
  }, [])

  const scrollPrev = React.useCallback(() => {
    api?.scrollPrev()
  }, [api])

  const scrollNext = React.useCallback(() => {
    api?.scrollNext()
  }, [api])

  const handleKeyDown = React.useCallback(
    (event: React.KeyboardEvent<HTMLDivElement>) => {
      if (event.key === "ArrowLeft") {
        event.preventDefault()
        scrollPrev()
      } else if (event.key === "ArrowRight") {
        event.preventDefault()
        scrollNext()
      }
    },
    [scrollPrev, scrollNext]
  )

  React.useEffect(() => {
    if (!api || !setApi) return
    setApi(api)
  }, [api, setApi])

  React.useEffect(() => {
    if (!api) return
    onSelect(api)
    api.on("reInit", onSelect)
    api.on("select", onSelect)

    return () => {
      api?.off("select", onSelect)
    }
  }, [api, onSelect])

  return (
    <CarouselContext.Provider
      value={{
        carouselRef,
        api: api,
        opts,
        orientation:
          orientation || (opts?.axis === "y" ? "vertical" : "horizontal"),
        scrollPrev,
        scrollNext,
        canScrollPrev,
        canScrollNext,
      }}
    >
      <div
        onKeyDownCapture={handleKeyDown}
        className={cn("relative", className)}
        role="region"
        aria-roledescription="carousel"
        data-slot="carousel"
        {...props}
      >
        {children}
      </div>
    </CarouselContext.Provider>
  )
}

function CarouselContent({ className, ...props }: React.ComponentProps<"div">) {
  const { carouselRef, orientation } = useCarousel()

  return (
    <div
      ref={carouselRef}
      className="overflow-hidden"
      data-slot="carousel-content"
    >
      <div
        className={cn(
          "flex",
          orientation === "horizontal" ? "-ml-4" : "-mt-4 flex-col",
          className
        )}
        {...props}
      />
    </div>
  )
}

function CarouselItem({ className, ...props }: React.ComponentProps<"div">) {
  const { orientation } = useCarousel()

  return (
    <div
      role="group"
      aria-roledescription="slide"
      data-slot="carousel-item"
      className={cn(
        "min-w-0 shrink-0 grow-0 basis-full",
        orientation === "horizontal" ? "pl-4" : "pt-4",
        className
      )}
      {...props}
    />
  )
}

function CarouselPrevious({
  className,
  variant = "outline",
  size = "icon",
  ...props
}: React.ComponentProps<typeof Button>) {
  const { orientation, scrollPrev, canScrollPrev } = useCarousel()

  return (
    <Button
      data-slot="carousel-previous"
      variant={variant}
      size={size}
      className={cn(
        "absolute size-8 rounded-full",
        orientation === "horizontal"
          ? "top-1/2 -left-12 -translate-y-1/2"
          : "-top-12 left-1/2 -translate-x-1/2 rotate-90",
        className
      )}
      disabled={!canScrollPrev}
      onClick={scrollPrev}
      {...props}
    >
      <ArrowLeft />
      <span className="sr-only">Previous slide</span>
    </Button>
  )
}

function CarouselNext({
  className,
  variant = "outline",
  size = "icon",
  ...props
}: React.ComponentProps<typeof Button>) {
  const { orientation, scrollNext, canScrollNext } = useCarousel()

  return (
    <Button
      data-slot="carousel-next"
      variant={variant}
      size={size}
      className={cn(
        "absolute size-8 rounded-full",
        orientation === "horizontal"
          ? "top-1/2 -right-12 -translate-y-1/2"
          : "-bottom-12 left-1/2 -translate-x-1/2 rotate-90",
        className
      )}
      disabled={!canScrollNext}
      onClick={scrollNext}
      {...props}
    >
      <ArrowRight />
      <span className="sr-only">Next slide</span>
    </Button>
  )
}

export {
  type CarouselApi,
  Carousel,
  CarouselContent,
  CarouselItem,
  CarouselPrevious,
  CarouselNext,
}



================================================================================
FILE: app/src/components/ui/chart.tsx
================================================================================

"use client"

import * as React from "react"
import * as RechartsPrimitive from "recharts"

import { cn } from "@/lib/utils"

// Format: { THEME_NAME: CSS_SELECTOR }
const THEMES = { light: "", dark: ".dark" } as const

export type ChartConfig = {
  [k in string]: {
    label?: React.ReactNode
    icon?: React.ComponentType
  } & (
    | { color?: string; theme?: never }
    | { color?: never; theme: Record<keyof typeof THEMES, string> }
  )
}

type ChartContextProps = {
  config: ChartConfig
}

const ChartContext = React.createContext<ChartContextProps | null>(null)

function useChart() {
  const context = React.useContext(ChartContext)

  if (!context) {
    throw new Error("useChart must be used within a <ChartContainer />")
  }

  return context
}

function ChartContainer({
  id,
  className,
  children,
  config,
  ...props
}: React.ComponentProps<"div"> & {
  config: ChartConfig
  children: React.ComponentProps<
    typeof RechartsPrimitive.ResponsiveContainer
  >["children"]
}) {
  const uniqueId = React.useId()
  const chartId = `chart-${id || uniqueId.replace(/:/g, "")}`

  return (
    <ChartContext.Provider value={{ config }}>
      <div
        data-slot="chart"
        data-chart={chartId}
        className={cn(
          "[&_.recharts-cartesian-axis-tick_text]:fill-muted-foreground [&_.recharts-cartesian-grid_line[stroke='#ccc']]:stroke-border/50 [&_.recharts-curve.recharts-tooltip-cursor]:stroke-border [&_.recharts-polar-grid_[stroke='#ccc']]:stroke-border [&_.recharts-radial-bar-background-sector]:fill-muted [&_.recharts-rectangle.recharts-tooltip-cursor]:fill-muted [&_.recharts-reference-line_[stroke='#ccc']]:stroke-border flex aspect-video justify-center text-xs [&_.recharts-dot[stroke='#fff']]:stroke-transparent [&_.recharts-layer]:outline-hidden [&_.recharts-sector]:outline-hidden [&_.recharts-sector[stroke='#fff']]:stroke-transparent [&_.recharts-surface]:outline-hidden",
          className
        )}
        {...props}
      >
        <ChartStyle id={chartId} config={config} />
        <RechartsPrimitive.ResponsiveContainer>
          {children}
        </RechartsPrimitive.ResponsiveContainer>
      </div>
    </ChartContext.Provider>
  )
}

const ChartStyle = ({ id, config }: { id: string; config: ChartConfig }) => {
  const colorConfig = Object.entries(config).filter(
    ([, config]) => config.theme || config.color
  )

  if (!colorConfig.length) {
    return null
  }

  return (
    <style
      dangerouslySetInnerHTML={{
        __html: Object.entries(THEMES)
          .map(
            ([theme, prefix]) => `
${prefix} [data-chart=${id}] {
${colorConfig
  .map(([key, itemConfig]) => {
    const color =
      itemConfig.theme?.[theme as keyof typeof itemConfig.theme] ||
      itemConfig.color
    return color ? `  --color-${key}: ${color};` : null
  })
  .join("\n")}
}
`
          )
          .join("\n"),
      }}
    />
  )
}

const ChartTooltip = RechartsPrimitive.Tooltip

function ChartTooltipContent({
  active,
  payload,
  className,
  indicator = "dot",
  hideLabel = false,
  hideIndicator = false,
  label,
  labelFormatter,
  labelClassName,
  formatter,
  color,
  nameKey,
  labelKey,
}: React.ComponentProps<typeof RechartsPrimitive.Tooltip> &
  React.ComponentProps<"div"> & {
    hideLabel?: boolean
    hideIndicator?: boolean
    indicator?: "line" | "dot" | "dashed"
    nameKey?: string
    labelKey?: string
  }) {
  const { config } = useChart()

  const tooltipLabel = React.useMemo(() => {
    if (hideLabel || !payload?.length) {
      return null
    }

    const [item] = payload
    const key = `${labelKey || item?.dataKey || item?.name || "value"}`
    const itemConfig = getPayloadConfigFromPayload(config, item, key)
    const value =
      !labelKey && typeof label === "string"
        ? config[label as keyof typeof config]?.label || label
        : itemConfig?.label

    if (labelFormatter) {
      return (
        <div className={cn("font-medium", labelClassName)}>
          {labelFormatter(value, payload)}
        </div>
      )
    }

    if (!value) {
      return null
    }

    return <div className={cn("font-medium", labelClassName)}>{value}</div>
  }, [
    label,
    labelFormatter,
    payload,
    hideLabel,
    labelClassName,
    config,
    labelKey,
  ])

  if (!active || !payload?.length) {
    return null
  }

  const nestLabel = payload.length === 1 && indicator !== "dot"

  return (
    <div
      className={cn(
        "border-border/50 bg-background grid min-w-[8rem] items-start gap-1.5 rounded-lg border px-2.5 py-1.5 text-xs shadow-xl",
        className
      )}
    >
      {!nestLabel ? tooltipLabel : null}
      <div className="grid gap-1.5">
        {payload
          .filter((item) => item.type !== "none")
          .map((item, index) => {
            const key = `${nameKey || item.name || item.dataKey || "value"}`
            const itemConfig = getPayloadConfigFromPayload(config, item, key)
            const indicatorColor = color || item.payload.fill || item.color

            return (
              <div
                key={item.dataKey}
                className={cn(
                  "[&>svg]:text-muted-foreground flex w-full flex-wrap items-stretch gap-2 [&>svg]:h-2.5 [&>svg]:w-2.5",
                  indicator === "dot" && "items-center"
                )}
              >
                {formatter && item?.value !== undefined && item.name ? (
                  formatter(item.value, item.name, item, index, item.payload)
                ) : (
                  <>
                    {itemConfig?.icon ? (
                      <itemConfig.icon />
                    ) : (
                      !hideIndicator && (
                        <div
                          className={cn(
                            "shrink-0 rounded-[2px] border-(--color-border) bg-(--color-bg)",
                            {
                              "h-2.5 w-2.5": indicator === "dot",
                              "w-1": indicator === "line",
                              "w-0 border-[1.5px] border-dashed bg-transparent":
                                indicator === "dashed",
                              "my-0.5": nestLabel && indicator === "dashed",
                            }
                          )}
                          style={
                            {
                              "--color-bg": indicatorColor,
                              "--color-border": indicatorColor,
                            } as React.CSSProperties
                          }
                        />
                      )
                    )}
                    <div
                      className={cn(
                        "flex flex-1 justify-between leading-none",
                        nestLabel ? "items-end" : "items-center"
                      )}
                    >
                      <div className="grid gap-1.5">
                        {nestLabel ? tooltipLabel : null}
                        <span className="text-muted-foreground">
                          {itemConfig?.label || item.name}
                        </span>
                      </div>
                      {item.value && (
                        <span className="text-foreground font-mono font-medium tabular-nums">
                          {item.value.toLocaleString()}
                        </span>
                      )}
                    </div>
                  </>
                )}
              </div>
            )
          })}
      </div>
    </div>
  )
}

const ChartLegend = RechartsPrimitive.Legend

function ChartLegendContent({
  className,
  hideIcon = false,
  payload,
  verticalAlign = "bottom",
  nameKey,
}: React.ComponentProps<"div"> &
  Pick<RechartsPrimitive.LegendProps, "payload" | "verticalAlign"> & {
    hideIcon?: boolean
    nameKey?: string
  }) {
  const { config } = useChart()

  if (!payload?.length) {
    return null
  }

  return (
    <div
      className={cn(
        "flex items-center justify-center gap-4",
        verticalAlign === "top" ? "pb-3" : "pt-3",
        className
      )}
    >
      {payload
        .filter((item) => item.type !== "none")
        .map((item) => {
          const key = `${nameKey || item.dataKey || "value"}`
          const itemConfig = getPayloadConfigFromPayload(config, item, key)

          return (
            <div
              key={item.value}
              className={cn(
                "[&>svg]:text-muted-foreground flex items-center gap-1.5 [&>svg]:h-3 [&>svg]:w-3"
              )}
            >
              {itemConfig?.icon && !hideIcon ? (
                <itemConfig.icon />
              ) : (
                <div
                  className="h-2 w-2 shrink-0 rounded-[2px]"
                  style={{
                    backgroundColor: item.color,
                  }}
                />
              )}
              {itemConfig?.label}
            </div>
          )
        })}
    </div>
  )
}

// Helper to extract item config from a payload.
function getPayloadConfigFromPayload(
  config: ChartConfig,
  payload: unknown,
  key: string
) {
  if (typeof payload !== "object" || payload === null) {
    return undefined
  }

  const payloadPayload =
    "payload" in payload &&
    typeof payload.payload === "object" &&
    payload.payload !== null
      ? payload.payload
      : undefined

  let configLabelKey: string = key

  if (
    key in payload &&
    typeof payload[key as keyof typeof payload] === "string"
  ) {
    configLabelKey = payload[key as keyof typeof payload] as string
  } else if (
    payloadPayload &&
    key in payloadPayload &&
    typeof payloadPayload[key as keyof typeof payloadPayload] === "string"
  ) {
    configLabelKey = payloadPayload[
      key as keyof typeof payloadPayload
    ] as string
  }

  return configLabelKey in config
    ? config[configLabelKey]
    : config[key as keyof typeof config]
}

export {
  ChartContainer,
  ChartTooltip,
  ChartTooltipContent,
  ChartLegend,
  ChartLegendContent,
  ChartStyle,
}



================================================================================
FILE: app/src/components/ui/checkbox.tsx
================================================================================

"use client"

import * as React from "react"
import * as CheckboxPrimitive from "@radix-ui/react-checkbox"
import { CheckIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function Checkbox({
  className,
  ...props
}: React.ComponentProps<typeof CheckboxPrimitive.Root>) {
  return (
    <CheckboxPrimitive.Root
      data-slot="checkbox"
      className={cn(
        "peer border-input dark:bg-input/30 data-[state=checked]:bg-primary data-[state=checked]:text-primary-foreground dark:data-[state=checked]:bg-primary data-[state=checked]:border-primary focus-visible:border-ring focus-visible:ring-ring/50 aria-invalid:ring-destructive/20 dark:aria-invalid:ring-destructive/40 aria-invalid:border-destructive size-4 shrink-0 rounded-[4px] border shadow-xs transition-shadow outline-none focus-visible:ring-[3px] disabled:cursor-not-allowed disabled:opacity-50",
        className
      )}
      {...props}
    >
      <CheckboxPrimitive.Indicator
        data-slot="checkbox-indicator"
        className="grid place-content-center text-current transition-none"
      >
        <CheckIcon className="size-3.5" />
      </CheckboxPrimitive.Indicator>
    </CheckboxPrimitive.Root>
  )
}

export { Checkbox }



================================================================================
FILE: app/src/components/ui/collapsible.tsx
================================================================================

import * as CollapsiblePrimitive from "@radix-ui/react-collapsible"

function Collapsible({
  ...props
}: React.ComponentProps<typeof CollapsiblePrimitive.Root>) {
  return <CollapsiblePrimitive.Root data-slot="collapsible" {...props} />
}

function CollapsibleTrigger({
  ...props
}: React.ComponentProps<typeof CollapsiblePrimitive.CollapsibleTrigger>) {
  return (
    <CollapsiblePrimitive.CollapsibleTrigger
      data-slot="collapsible-trigger"
      {...props}
    />
  )
}

function CollapsibleContent({
  ...props
}: React.ComponentProps<typeof CollapsiblePrimitive.CollapsibleContent>) {
  return (
    <CollapsiblePrimitive.CollapsibleContent
      data-slot="collapsible-content"
      {...props}
    />
  )
}

export { Collapsible, CollapsibleTrigger, CollapsibleContent }



================================================================================
FILE: app/src/components/ui/command.tsx
================================================================================

import * as React from "react"
import { Command as CommandPrimitive } from "cmdk"
import { SearchIcon } from "lucide-react"

import { cn } from "@/lib/utils"
import {
  Dialog,
  DialogContent,
  DialogDescription,
  DialogHeader,
  DialogTitle,
} from "@/components/ui/dialog"

function Command({
  className,
  ...props
}: React.ComponentProps<typeof CommandPrimitive>) {
  return (
    <CommandPrimitive
      data-slot="command"
      className={cn(
        "bg-popover text-popover-foreground flex h-full w-full flex-col overflow-hidden rounded-md",
        className
      )}
      {...props}
    />
  )
}

function CommandDialog({
  title = "Command Palette",
  description = "Search for a command to run...",
  children,
  className,
  showCloseButton = true,
  ...props
}: React.ComponentProps<typeof Dialog> & {
  title?: string
  description?: string
  className?: string
  showCloseButton?: boolean
}) {
  return (
    <Dialog {...props}>
      <DialogHeader className="sr-only">
        <DialogTitle>{title}</DialogTitle>
        <DialogDescription>{description}</DialogDescription>
      </DialogHeader>
      <DialogContent
        className={cn("overflow-hidden p-0", className)}
        showCloseButton={showCloseButton}
      >
        <Command className="[&_[cmdk-group-heading]]:text-muted-foreground **:data-[slot=command-input-wrapper]:h-12 [&_[cmdk-group-heading]]:px-2 [&_[cmdk-group-heading]]:font-medium [&_[cmdk-group]]:px-2 [&_[cmdk-group]:not([hidden])_~[cmdk-group]]:pt-0 [&_[cmdk-input-wrapper]_svg]:h-5 [&_[cmdk-input-wrapper]_svg]:w-5 [&_[cmdk-input]]:h-12 [&_[cmdk-item]]:px-2 [&_[cmdk-item]]:py-3 [&_[cmdk-item]_svg]:h-5 [&_[cmdk-item]_svg]:w-5">
          {children}
        </Command>
      </DialogContent>
    </Dialog>
  )
}

function CommandInput({
  className,
  ...props
}: React.ComponentProps<typeof CommandPrimitive.Input>) {
  return (
    <div
      data-slot="command-input-wrapper"
      className="flex h-9 items-center gap-2 border-b px-3"
    >
      <SearchIcon className="size-4 shrink-0 opacity-50" />
      <CommandPrimitive.Input
        data-slot="command-input"
        className={cn(
          "placeholder:text-muted-foreground flex h-10 w-full rounded-md bg-transparent py-3 text-sm outline-hidden disabled:cursor-not-allowed disabled:opacity-50",
          className
        )}
        {...props}
      />
    </div>
  )
}

function CommandList({
  className,
  ...props
}: React.ComponentProps<typeof CommandPrimitive.List>) {
  return (
    <CommandPrimitive.List
      data-slot="command-list"
      className={cn(
        "max-h-[300px] scroll-py-1 overflow-x-hidden overflow-y-auto",
        className
      )}
      {...props}
    />
  )
}

function CommandEmpty({
  ...props
}: React.ComponentProps<typeof CommandPrimitive.Empty>) {
  return (
    <CommandPrimitive.Empty
      data-slot="command-empty"
      className="py-6 text-center text-sm"
      {...props}
    />
  )
}

function CommandGroup({
  className,
  ...props
}: React.ComponentProps<typeof CommandPrimitive.Group>) {
  return (
    <CommandPrimitive.Group
      data-slot="command-group"
      className={cn(
        "text-foreground [&_[cmdk-group-heading]]:text-muted-foreground overflow-hidden p-1 [&_[cmdk-group-heading]]:px-2 [&_[cmdk-group-heading]]:py-1.5 [&_[cmdk-group-heading]]:text-xs [&_[cmdk-group-heading]]:font-medium",
        className
      )}
      {...props}
    />
  )
}

function CommandSeparator({
  className,
  ...props
}: React.ComponentProps<typeof CommandPrimitive.Separator>) {
  return (
    <CommandPrimitive.Separator
      data-slot="command-separator"
      className={cn("bg-border -mx-1 h-px", className)}
      {...props}
    />
  )
}

function CommandItem({
  className,
  ...props
}: React.ComponentProps<typeof CommandPrimitive.Item>) {
  return (
    <CommandPrimitive.Item
      data-slot="command-item"
      className={cn(
        "data-[selected=true]:bg-accent data-[selected=true]:text-accent-foreground [&_svg:not([class*='text-'])]:text-muted-foreground relative flex cursor-default items-center gap-2 rounded-sm px-2 py-1.5 text-sm outline-hidden select-none data-[disabled=true]:pointer-events-none data-[disabled=true]:opacity-50 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    />
  )
}

function CommandShortcut({
  className,
  ...props
}: React.ComponentProps<"span">) {
  return (
    <span
      data-slot="command-shortcut"
      className={cn(
        "text-muted-foreground ml-auto text-xs tracking-widest",
        className
      )}
      {...props}
    />
  )
}

export {
  Command,
  CommandDialog,
  CommandInput,
  CommandList,
  CommandEmpty,
  CommandGroup,
  CommandItem,
  CommandShortcut,
  CommandSeparator,
}



================================================================================
FILE: app/src/components/ui/context-menu.tsx
================================================================================

"use client"

import * as React from "react"
import * as ContextMenuPrimitive from "@radix-ui/react-context-menu"
import { CheckIcon, ChevronRightIcon, CircleIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function ContextMenu({
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Root>) {
  return <ContextMenuPrimitive.Root data-slot="context-menu" {...props} />
}

function ContextMenuTrigger({
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Trigger>) {
  return (
    <ContextMenuPrimitive.Trigger data-slot="context-menu-trigger" {...props} />
  )
}

function ContextMenuGroup({
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Group>) {
  return (
    <ContextMenuPrimitive.Group data-slot="context-menu-group" {...props} />
  )
}

function ContextMenuPortal({
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Portal>) {
  return (
    <ContextMenuPrimitive.Portal data-slot="context-menu-portal" {...props} />
  )
}

function ContextMenuSub({
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Sub>) {
  return <ContextMenuPrimitive.Sub data-slot="context-menu-sub" {...props} />
}

function ContextMenuRadioGroup({
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.RadioGroup>) {
  return (
    <ContextMenuPrimitive.RadioGroup
      data-slot="context-menu-radio-group"
      {...props}
    />
  )
}

function ContextMenuSubTrigger({
  className,
  inset,
  children,
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.SubTrigger> & {
  inset?: boolean
}) {
  return (
    <ContextMenuPrimitive.SubTrigger
      data-slot="context-menu-sub-trigger"
      data-inset={inset}
      className={cn(
        "focus:bg-accent focus:text-accent-foreground data-[state=open]:bg-accent data-[state=open]:text-accent-foreground [&_svg:not([class*='text-'])]:text-muted-foreground flex cursor-default items-center rounded-sm px-2 py-1.5 text-sm outline-hidden select-none data-[inset]:pl-8 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    >
      {children}
      <ChevronRightIcon className="ml-auto" />
    </ContextMenuPrimitive.SubTrigger>
  )
}

function ContextMenuSubContent({
  className,
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.SubContent>) {
  return (
    <ContextMenuPrimitive.SubContent
      data-slot="context-menu-sub-content"
      className={cn(
        "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 min-w-[8rem] origin-(--radix-context-menu-content-transform-origin) overflow-hidden rounded-md border p-1 shadow-lg",
        className
      )}
      {...props}
    />
  )
}

function ContextMenuContent({
  className,
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Content>) {
  return (
    <ContextMenuPrimitive.Portal>
      <ContextMenuPrimitive.Content
        data-slot="context-menu-content"
        className={cn(
          "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 max-h-(--radix-context-menu-content-available-height) min-w-[8rem] origin-(--radix-context-menu-content-transform-origin) overflow-x-hidden overflow-y-auto rounded-md border p-1 shadow-md",
          className
        )}
        {...props}
      />
    </ContextMenuPrimitive.Portal>
  )
}

function ContextMenuItem({
  className,
  inset,
  variant = "default",
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Item> & {
  inset?: boolean
  variant?: "default" | "destructive"
}) {
  return (
    <ContextMenuPrimitive.Item
      data-slot="context-menu-item"
      data-inset={inset}
      data-variant={variant}
      className={cn(
        "focus:bg-accent focus:text-accent-foreground data-[variant=destructive]:text-destructive data-[variant=destructive]:focus:bg-destructive/10 dark:data-[variant=destructive]:focus:bg-destructive/20 data-[variant=destructive]:focus:text-destructive data-[variant=destructive]:*:[svg]:!text-destructive [&_svg:not([class*='text-'])]:text-muted-foreground relative flex cursor-default items-center gap-2 rounded-sm px-2 py-1.5 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 data-[inset]:pl-8 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    />
  )
}

function ContextMenuCheckboxItem({
  className,
  children,
  checked,
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.CheckboxItem>) {
  return (
    <ContextMenuPrimitive.CheckboxItem
      data-slot="context-menu-checkbox-item"
      className={cn(
        "focus:bg-accent focus:text-accent-foreground relative flex cursor-default items-center gap-2 rounded-sm py-1.5 pr-2 pl-8 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      checked={checked}
      {...props}
    >
      <span className="pointer-events-none absolute left-2 flex size-3.5 items-center justify-center">
        <ContextMenuPrimitive.ItemIndicator>
          <CheckIcon className="size-4" />
        </ContextMenuPrimitive.ItemIndicator>
      </span>
      {children}
    </ContextMenuPrimitive.CheckboxItem>
  )
}

function ContextMenuRadioItem({
  className,
  children,
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.RadioItem>) {
  return (
    <ContextMenuPrimitive.RadioItem
      data-slot="context-menu-radio-item"
      className={cn(
        "focus:bg-accent focus:text-accent-foreground relative flex cursor-default items-center gap-2 rounded-sm py-1.5 pr-2 pl-8 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    >
      <span className="pointer-events-none absolute left-2 flex size-3.5 items-center justify-center">
        <ContextMenuPrimitive.ItemIndicator>
          <CircleIcon className="size-2 fill-current" />
        </ContextMenuPrimitive.ItemIndicator>
      </span>
      {children}
    </ContextMenuPrimitive.RadioItem>
  )
}

function ContextMenuLabel({
  className,
  inset,
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Label> & {
  inset?: boolean
}) {
  return (
    <ContextMenuPrimitive.Label
      data-slot="context-menu-label"
      data-inset={inset}
      className={cn(
        "text-foreground px-2 py-1.5 text-sm font-medium data-[inset]:pl-8",
        className
      )}
      {...props}
    />
  )
}

function ContextMenuSeparator({
  className,
  ...props
}: React.ComponentProps<typeof ContextMenuPrimitive.Separator>) {
  return (
    <ContextMenuPrimitive.Separator
      data-slot="context-menu-separator"
      className={cn("bg-border -mx-1 my-1 h-px", className)}
      {...props}
    />
  )
}

function ContextMenuShortcut({
  className,
  ...props
}: React.ComponentProps<"span">) {
  return (
    <span
      data-slot="context-menu-shortcut"
      className={cn(
        "text-muted-foreground ml-auto text-xs tracking-widest",
        className
      )}
      {...props}
    />
  )
}

export {
  ContextMenu,
  ContextMenuTrigger,
  ContextMenuContent,
  ContextMenuItem,
  ContextMenuCheckboxItem,
  ContextMenuRadioItem,
  ContextMenuLabel,
  ContextMenuSeparator,
  ContextMenuShortcut,
  ContextMenuGroup,
  ContextMenuPortal,
  ContextMenuSub,
  ContextMenuSubContent,
  ContextMenuSubTrigger,
  ContextMenuRadioGroup,
}



================================================================================
FILE: app/src/components/ui/dialog.tsx
================================================================================

import * as React from "react"
import * as DialogPrimitive from "@radix-ui/react-dialog"
import { XIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function Dialog({
  ...props
}: React.ComponentProps<typeof DialogPrimitive.Root>) {
  return <DialogPrimitive.Root data-slot="dialog" {...props} />
}

function DialogTrigger({
  ...props
}: React.ComponentProps<typeof DialogPrimitive.Trigger>) {
  return <DialogPrimitive.Trigger data-slot="dialog-trigger" {...props} />
}

function DialogPortal({
  ...props
}: React.ComponentProps<typeof DialogPrimitive.Portal>) {
  return <DialogPrimitive.Portal data-slot="dialog-portal" {...props} />
}

function DialogClose({
  ...props
}: React.ComponentProps<typeof DialogPrimitive.Close>) {
  return <DialogPrimitive.Close data-slot="dialog-close" {...props} />
}

function DialogOverlay({
  className,
  ...props
}: React.ComponentProps<typeof DialogPrimitive.Overlay>) {
  return (
    <DialogPrimitive.Overlay
      data-slot="dialog-overlay"
      className={cn(
        "data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 fixed inset-0 z-50 bg-black/50",
        className
      )}
      {...props}
    />
  )
}

function DialogContent({
  className,
  children,
  showCloseButton = true,
  ...props
}: React.ComponentProps<typeof DialogPrimitive.Content> & {
  showCloseButton?: boolean
}) {
  return (
    <DialogPortal data-slot="dialog-portal">
      <DialogOverlay />
      <DialogPrimitive.Content
        data-slot="dialog-content"
        className={cn(
          "bg-background data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 fixed top-[50%] left-[50%] z-50 grid w-full max-w-[calc(100%-2rem)] translate-x-[-50%] translate-y-[-50%] gap-4 rounded-lg border p-6 shadow-lg duration-200 outline-none sm:max-w-lg",
          className
        )}
        {...props}
      >
        {children}
        {showCloseButton && (
          <DialogPrimitive.Close
            data-slot="dialog-close"
            className="ring-offset-background focus:ring-ring data-[state=open]:bg-accent data-[state=open]:text-muted-foreground absolute top-4 right-4 rounded-xs opacity-70 transition-opacity hover:opacity-100 focus:ring-2 focus:ring-offset-2 focus:outline-hidden disabled:pointer-events-none [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4"
          >
            <XIcon />
            <span className="sr-only">Close</span>
          </DialogPrimitive.Close>
        )}
      </DialogPrimitive.Content>
    </DialogPortal>
  )
}

function DialogHeader({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="dialog-header"
      className={cn("flex flex-col gap-2 text-center sm:text-left", className)}
      {...props}
    />
  )
}

function DialogFooter({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="dialog-footer"
      className={cn(
        "flex flex-col-reverse gap-2 sm:flex-row sm:justify-end",
        className
      )}
      {...props}
    />
  )
}

function DialogTitle({
  className,
  ...props
}: React.ComponentProps<typeof DialogPrimitive.Title>) {
  return (
    <DialogPrimitive.Title
      data-slot="dialog-title"
      className={cn("text-lg leading-none font-semibold", className)}
      {...props}
    />
  )
}

function DialogDescription({
  className,
  ...props
}: React.ComponentProps<typeof DialogPrimitive.Description>) {
  return (
    <DialogPrimitive.Description
      data-slot="dialog-description"
      className={cn("text-muted-foreground text-sm", className)}
      {...props}
    />
  )
}

export {
  Dialog,
  DialogClose,
  DialogContent,
  DialogDescription,
  DialogFooter,
  DialogHeader,
  DialogOverlay,
  DialogPortal,
  DialogTitle,
  DialogTrigger,
}



================================================================================
FILE: app/src/components/ui/drawer.tsx
================================================================================

"use client"

import * as React from "react"
import { Drawer as DrawerPrimitive } from "vaul"

import { cn } from "@/lib/utils"

function Drawer({
  ...props
}: React.ComponentProps<typeof DrawerPrimitive.Root>) {
  return <DrawerPrimitive.Root data-slot="drawer" {...props} />
}

function DrawerTrigger({
  ...props
}: React.ComponentProps<typeof DrawerPrimitive.Trigger>) {
  return <DrawerPrimitive.Trigger data-slot="drawer-trigger" {...props} />
}

function DrawerPortal({
  ...props
}: React.ComponentProps<typeof DrawerPrimitive.Portal>) {
  return <DrawerPrimitive.Portal data-slot="drawer-portal" {...props} />
}

function DrawerClose({
  ...props
}: React.ComponentProps<typeof DrawerPrimitive.Close>) {
  return <DrawerPrimitive.Close data-slot="drawer-close" {...props} />
}

function DrawerOverlay({
  className,
  ...props
}: React.ComponentProps<typeof DrawerPrimitive.Overlay>) {
  return (
    <DrawerPrimitive.Overlay
      data-slot="drawer-overlay"
      className={cn(
        "data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 fixed inset-0 z-50 bg-black/50",
        className
      )}
      {...props}
    />
  )
}

function DrawerContent({
  className,
  children,
  ...props
}: React.ComponentProps<typeof DrawerPrimitive.Content>) {
  return (
    <DrawerPortal data-slot="drawer-portal">
      <DrawerOverlay />
      <DrawerPrimitive.Content
        data-slot="drawer-content"
        className={cn(
          "group/drawer-content bg-background fixed z-50 flex h-auto flex-col",
          "data-[vaul-drawer-direction=top]:inset-x-0 data-[vaul-drawer-direction=top]:top-0 data-[vaul-drawer-direction=top]:mb-24 data-[vaul-drawer-direction=top]:max-h-[80vh] data-[vaul-drawer-direction=top]:rounded-b-lg data-[vaul-drawer-direction=top]:border-b",
          "data-[vaul-drawer-direction=bottom]:inset-x-0 data-[vaul-drawer-direction=bottom]:bottom-0 data-[vaul-drawer-direction=bottom]:mt-24 data-[vaul-drawer-direction=bottom]:max-h-[80vh] data-[vaul-drawer-direction=bottom]:rounded-t-lg data-[vaul-drawer-direction=bottom]:border-t",
          "data-[vaul-drawer-direction=right]:inset-y-0 data-[vaul-drawer-direction=right]:right-0 data-[vaul-drawer-direction=right]:w-3/4 data-[vaul-drawer-direction=right]:border-l data-[vaul-drawer-direction=right]:sm:max-w-sm",
          "data-[vaul-drawer-direction=left]:inset-y-0 data-[vaul-drawer-direction=left]:left-0 data-[vaul-drawer-direction=left]:w-3/4 data-[vaul-drawer-direction=left]:border-r data-[vaul-drawer-direction=left]:sm:max-w-sm",
          className
        )}
        {...props}
      >
        <div className="bg-muted mx-auto mt-4 hidden h-2 w-[100px] shrink-0 rounded-full group-data-[vaul-drawer-direction=bottom]/drawer-content:block" />
        {children}
      </DrawerPrimitive.Content>
    </DrawerPortal>
  )
}

function DrawerHeader({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="drawer-header"
      className={cn(
        "flex flex-col gap-0.5 p-4 group-data-[vaul-drawer-direction=bottom]/drawer-content:text-center group-data-[vaul-drawer-direction=top]/drawer-content:text-center md:gap-1.5 md:text-left",
        className
      )}
      {...props}
    />
  )
}

function DrawerFooter({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="drawer-footer"
      className={cn("mt-auto flex flex-col gap-2 p-4", className)}
      {...props}
    />
  )
}

function DrawerTitle({
  className,
  ...props
}: React.ComponentProps<typeof DrawerPrimitive.Title>) {
  return (
    <DrawerPrimitive.Title
      data-slot="drawer-title"
      className={cn("text-foreground font-semibold", className)}
      {...props}
    />
  )
}

function DrawerDescription({
  className,
  ...props
}: React.ComponentProps<typeof DrawerPrimitive.Description>) {
  return (
    <DrawerPrimitive.Description
      data-slot="drawer-description"
      className={cn("text-muted-foreground text-sm", className)}
      {...props}
    />
  )
}

export {
  Drawer,
  DrawerPortal,
  DrawerOverlay,
  DrawerTrigger,
  DrawerClose,
  DrawerContent,
  DrawerHeader,
  DrawerFooter,
  DrawerTitle,
  DrawerDescription,
}



================================================================================
FILE: app/src/components/ui/dropdown-menu.tsx
================================================================================

import * as React from "react"
import * as DropdownMenuPrimitive from "@radix-ui/react-dropdown-menu"
import { CheckIcon, ChevronRightIcon, CircleIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function DropdownMenu({
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Root>) {
  return <DropdownMenuPrimitive.Root data-slot="dropdown-menu" {...props} />
}

function DropdownMenuPortal({
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Portal>) {
  return (
    <DropdownMenuPrimitive.Portal data-slot="dropdown-menu-portal" {...props} />
  )
}

function DropdownMenuTrigger({
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Trigger>) {
  return (
    <DropdownMenuPrimitive.Trigger
      data-slot="dropdown-menu-trigger"
      {...props}
    />
  )
}

function DropdownMenuContent({
  className,
  sideOffset = 4,
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Content>) {
  return (
    <DropdownMenuPrimitive.Portal>
      <DropdownMenuPrimitive.Content
        data-slot="dropdown-menu-content"
        sideOffset={sideOffset}
        className={cn(
          "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 max-h-(--radix-dropdown-menu-content-available-height) min-w-[8rem] origin-(--radix-dropdown-menu-content-transform-origin) overflow-x-hidden overflow-y-auto rounded-md border p-1 shadow-md",
          className
        )}
        {...props}
      />
    </DropdownMenuPrimitive.Portal>
  )
}

function DropdownMenuGroup({
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Group>) {
  return (
    <DropdownMenuPrimitive.Group data-slot="dropdown-menu-group" {...props} />
  )
}

function DropdownMenuItem({
  className,
  inset,
  variant = "default",
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Item> & {
  inset?: boolean
  variant?: "default" | "destructive"
}) {
  return (
    <DropdownMenuPrimitive.Item
      data-slot="dropdown-menu-item"
      data-inset={inset}
      data-variant={variant}
      className={cn(
        "focus:bg-accent focus:text-accent-foreground data-[variant=destructive]:text-destructive data-[variant=destructive]:focus:bg-destructive/10 dark:data-[variant=destructive]:focus:bg-destructive/20 data-[variant=destructive]:focus:text-destructive data-[variant=destructive]:*:[svg]:!text-destructive [&_svg:not([class*='text-'])]:text-muted-foreground relative flex cursor-default items-center gap-2 rounded-sm px-2 py-1.5 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 data-[inset]:pl-8 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    />
  )
}

function DropdownMenuCheckboxItem({
  className,
  children,
  checked,
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.CheckboxItem>) {
  return (
    <DropdownMenuPrimitive.CheckboxItem
      data-slot="dropdown-menu-checkbox-item"
      className={cn(
        "focus:bg-accent focus:text-accent-foreground relative flex cursor-default items-center gap-2 rounded-sm py-1.5 pr-2 pl-8 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      checked={checked}
      {...props}
    >
      <span className="pointer-events-none absolute left-2 flex size-3.5 items-center justify-center">
        <DropdownMenuPrimitive.ItemIndicator>
          <CheckIcon className="size-4" />
        </DropdownMenuPrimitive.ItemIndicator>
      </span>
      {children}
    </DropdownMenuPrimitive.CheckboxItem>
  )
}

function DropdownMenuRadioGroup({
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.RadioGroup>) {
  return (
    <DropdownMenuPrimitive.RadioGroup
      data-slot="dropdown-menu-radio-group"
      {...props}
    />
  )
}

function DropdownMenuRadioItem({
  className,
  children,
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.RadioItem>) {
  return (
    <DropdownMenuPrimitive.RadioItem
      data-slot="dropdown-menu-radio-item"
      className={cn(
        "focus:bg-accent focus:text-accent-foreground relative flex cursor-default items-center gap-2 rounded-sm py-1.5 pr-2 pl-8 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    >
      <span className="pointer-events-none absolute left-2 flex size-3.5 items-center justify-center">
        <DropdownMenuPrimitive.ItemIndicator>
          <CircleIcon className="size-2 fill-current" />
        </DropdownMenuPrimitive.ItemIndicator>
      </span>
      {children}
    </DropdownMenuPrimitive.RadioItem>
  )
}

function DropdownMenuLabel({
  className,
  inset,
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Label> & {
  inset?: boolean
}) {
  return (
    <DropdownMenuPrimitive.Label
      data-slot="dropdown-menu-label"
      data-inset={inset}
      className={cn(
        "px-2 py-1.5 text-sm font-medium data-[inset]:pl-8",
        className
      )}
      {...props}
    />
  )
}

function DropdownMenuSeparator({
  className,
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Separator>) {
  return (
    <DropdownMenuPrimitive.Separator
      data-slot="dropdown-menu-separator"
      className={cn("bg-border -mx-1 my-1 h-px", className)}
      {...props}
    />
  )
}

function DropdownMenuShortcut({
  className,
  ...props
}: React.ComponentProps<"span">) {
  return (
    <span
      data-slot="dropdown-menu-shortcut"
      className={cn(
        "text-muted-foreground ml-auto text-xs tracking-widest",
        className
      )}
      {...props}
    />
  )
}

function DropdownMenuSub({
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.Sub>) {
  return <DropdownMenuPrimitive.Sub data-slot="dropdown-menu-sub" {...props} />
}

function DropdownMenuSubTrigger({
  className,
  inset,
  children,
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.SubTrigger> & {
  inset?: boolean
}) {
  return (
    <DropdownMenuPrimitive.SubTrigger
      data-slot="dropdown-menu-sub-trigger"
      data-inset={inset}
      className={cn(
        "focus:bg-accent focus:text-accent-foreground data-[state=open]:bg-accent data-[state=open]:text-accent-foreground [&_svg:not([class*='text-'])]:text-muted-foreground flex cursor-default items-center gap-2 rounded-sm px-2 py-1.5 text-sm outline-hidden select-none data-[inset]:pl-8 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    >
      {children}
      <ChevronRightIcon className="ml-auto size-4" />
    </DropdownMenuPrimitive.SubTrigger>
  )
}

function DropdownMenuSubContent({
  className,
  ...props
}: React.ComponentProps<typeof DropdownMenuPrimitive.SubContent>) {
  return (
    <DropdownMenuPrimitive.SubContent
      data-slot="dropdown-menu-sub-content"
      className={cn(
        "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 min-w-[8rem] origin-(--radix-dropdown-menu-content-transform-origin) overflow-hidden rounded-md border p-1 shadow-lg",
        className
      )}
      {...props}
    />
  )
}

export {
  DropdownMenu,
  DropdownMenuPortal,
  DropdownMenuTrigger,
  DropdownMenuContent,
  DropdownMenuGroup,
  DropdownMenuLabel,
  DropdownMenuItem,
  DropdownMenuCheckboxItem,
  DropdownMenuRadioGroup,
  DropdownMenuRadioItem,
  DropdownMenuSeparator,
  DropdownMenuShortcut,
  DropdownMenuSub,
  DropdownMenuSubTrigger,
  DropdownMenuSubContent,
}



================================================================================
FILE: app/src/components/ui/empty.tsx
================================================================================

import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"

function Empty({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="empty"
      className={cn(
        "flex min-w-0 flex-1 flex-col items-center justify-center gap-6 rounded-lg border-dashed p-6 text-center text-balance md:p-12",
        className
      )}
      {...props}
    />
  )
}

function EmptyHeader({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="empty-header"
      className={cn(
        "flex max-w-sm flex-col items-center gap-2 text-center",
        className
      )}
      {...props}
    />
  )
}

const emptyMediaVariants = cva(
  "flex shrink-0 items-center justify-center mb-2 [&_svg]:pointer-events-none [&_svg]:shrink-0",
  {
    variants: {
      variant: {
        default: "bg-transparent",
        icon: "bg-muted text-foreground flex size-10 shrink-0 items-center justify-center rounded-lg [&_svg:not([class*='size-'])]:size-6",
      },
    },
    defaultVariants: {
      variant: "default",
    },
  }
)

function EmptyMedia({
  className,
  variant = "default",
  ...props
}: React.ComponentProps<"div"> & VariantProps<typeof emptyMediaVariants>) {
  return (
    <div
      data-slot="empty-icon"
      data-variant={variant}
      className={cn(emptyMediaVariants({ variant, className }))}
      {...props}
    />
  )
}

function EmptyTitle({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="empty-title"
      className={cn("text-lg font-medium tracking-tight", className)}
      {...props}
    />
  )
}

function EmptyDescription({ className, ...props }: React.ComponentProps<"p">) {
  return (
    <div
      data-slot="empty-description"
      className={cn(
        "text-muted-foreground [&>a:hover]:text-primary text-sm/relaxed [&>a]:underline [&>a]:underline-offset-4",
        className
      )}
      {...props}
    />
  )
}

function EmptyContent({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="empty-content"
      className={cn(
        "flex w-full max-w-sm min-w-0 flex-col items-center gap-4 text-sm text-balance",
        className
      )}
      {...props}
    />
  )
}

export {
  Empty,
  EmptyHeader,
  EmptyTitle,
  EmptyDescription,
  EmptyContent,
  EmptyMedia,
}



================================================================================
FILE: app/src/components/ui/field.tsx
================================================================================

import { useMemo } from "react"
import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"
import { Label } from "@/components/ui/label"
import { Separator } from "@/components/ui/separator"

function FieldSet({ className, ...props }: React.ComponentProps<"fieldset">) {
  return (
    <fieldset
      data-slot="field-set"
      className={cn(
        "flex flex-col gap-6",
        "has-[>[data-slot=checkbox-group]]:gap-3 has-[>[data-slot=radio-group]]:gap-3",
        className
      )}
      {...props}
    />
  )
}

function FieldLegend({
  className,
  variant = "legend",
  ...props
}: React.ComponentProps<"legend"> & { variant?: "legend" | "label" }) {
  return (
    <legend
      data-slot="field-legend"
      data-variant={variant}
      className={cn(
        "mb-3 font-medium",
        "data-[variant=legend]:text-base",
        "data-[variant=label]:text-sm",
        className
      )}
      {...props}
    />
  )
}

function FieldGroup({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="field-group"
      className={cn(
        "group/field-group @container/field-group flex w-full flex-col gap-7 data-[slot=checkbox-group]:gap-3 [&>[data-slot=field-group]]:gap-4",
        className
      )}
      {...props}
    />
  )
}

const fieldVariants = cva(
  "group/field flex w-full gap-3 data-[invalid=true]:text-destructive",
  {
    variants: {
      orientation: {
        vertical: ["flex-col [&>*]:w-full [&>.sr-only]:w-auto"],
        horizontal: [
          "flex-row items-center",
          "[&>[data-slot=field-label]]:flex-auto",
          "has-[>[data-slot=field-content]]:items-start has-[>[data-slot=field-content]]:[&>[role=checkbox],[role=radio]]:mt-px",
        ],
        responsive: [
          "flex-col [&>*]:w-full [&>.sr-only]:w-auto @md/field-group:flex-row @md/field-group:items-center @md/field-group:[&>*]:w-auto",
          "@md/field-group:[&>[data-slot=field-label]]:flex-auto",
          "@md/field-group:has-[>[data-slot=field-content]]:items-start @md/field-group:has-[>[data-slot=field-content]]:[&>[role=checkbox],[role=radio]]:mt-px",
        ],
      },
    },
    defaultVariants: {
      orientation: "vertical",
    },
  }
)

function Field({
  className,
  orientation = "vertical",
  ...props
}: React.ComponentProps<"div"> & VariantProps<typeof fieldVariants>) {
  return (
    <div
      role="group"
      data-slot="field"
      data-orientation={orientation}
      className={cn(fieldVariants({ orientation }), className)}
      {...props}
    />
  )
}

function FieldContent({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="field-content"
      className={cn(
        "group/field-content flex flex-1 flex-col gap-1.5 leading-snug",
        className
      )}
      {...props}
    />
  )
}

function FieldLabel({
  className,
  ...props
}: React.ComponentProps<typeof Label>) {
  return (
    <Label
      data-slot="field-label"
      className={cn(
        "group/field-label peer/field-label flex w-fit gap-2 leading-snug group-data-[disabled=true]/field:opacity-50",
        "has-[>[data-slot=field]]:w-full has-[>[data-slot=field]]:flex-col has-[>[data-slot=field]]:rounded-md has-[>[data-slot=field]]:border [&>*]:data-[slot=field]:p-4",
        "has-data-[state=checked]:bg-primary/5 has-data-[state=checked]:border-primary dark:has-data-[state=checked]:bg-primary/10",
        className
      )}
      {...props}
    />
  )
}

function FieldTitle({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="field-label"
      className={cn(
        "flex w-fit items-center gap-2 text-sm leading-snug font-medium group-data-[disabled=true]/field:opacity-50",
        className
      )}
      {...props}
    />
  )
}

function FieldDescription({ className, ...props }: React.ComponentProps<"p">) {
  return (
    <p
      data-slot="field-description"
      className={cn(
        "text-muted-foreground text-sm leading-normal font-normal group-has-[[data-orientation=horizontal]]/field:text-balance",
        "last:mt-0 nth-last-2:-mt-1 [[data-variant=legend]+&]:-mt-1.5",
        "[&>a:hover]:text-primary [&>a]:underline [&>a]:underline-offset-4",
        className
      )}
      {...props}
    />
  )
}

function FieldSeparator({
  children,
  className,
  ...props
}: React.ComponentProps<"div"> & {
  children?: React.ReactNode
}) {
  return (
    <div
      data-slot="field-separator"
      data-content={!!children}
      className={cn(
        "relative -my-2 h-5 text-sm group-data-[variant=outline]/field-group:-mb-2",
        className
      )}
      {...props}
    >
      <Separator className="absolute inset-0 top-1/2" />
      {children && (
        <span
          className="bg-background text-muted-foreground relative mx-auto block w-fit px-2"
          data-slot="field-separator-content"
        >
          {children}
        </span>
      )}
    </div>
  )
}

function FieldError({
  className,
  children,
  errors,
  ...props
}: React.ComponentProps<"div"> & {
  errors?: Array<{ message?: string } | undefined>
}) {
  const content = useMemo(() => {
    if (children) {
      return children
    }

    if (!errors?.length) {
      return null
    }

    const uniqueErrors = [
      ...new Map(errors.map((error) => [error?.message, error])).values(),
    ]

    if (uniqueErrors?.length == 1) {
      return uniqueErrors[0]?.message
    }

    return (
      <ul className="ml-4 flex list-disc flex-col gap-1">
        {uniqueErrors.map(
          (error, index) =>
            error?.message && <li key={index}>{error.message}</li>
        )}
      </ul>
    )
  }, [children, errors])

  if (!content) {
    return null
  }

  return (
    <div
      role="alert"
      data-slot="field-error"
      className={cn("text-destructive text-sm font-normal", className)}
      {...props}
    >
      {content}
    </div>
  )
}

export {
  Field,
  FieldLabel,
  FieldDescription,
  FieldError,
  FieldGroup,
  FieldLegend,
  FieldSeparator,
  FieldSet,
  FieldContent,
  FieldTitle,
}



================================================================================
FILE: app/src/components/ui/form.tsx
================================================================================

"use client"

import * as React from "react"
import type * as LabelPrimitive from "@radix-ui/react-label"
import { Slot } from "@radix-ui/react-slot"
import {
  Controller,
  FormProvider,
  useFormContext,
  useFormState,
  type ControllerProps,
  type FieldPath,
  type FieldValues,
} from "react-hook-form"

import { cn } from "@/lib/utils"
import { Label } from "@/components/ui/label"

const Form = FormProvider

type FormFieldContextValue<
  TFieldValues extends FieldValues = FieldValues,
  TName extends FieldPath<TFieldValues> = FieldPath<TFieldValues>,
> = {
  name: TName
}

const FormFieldContext = React.createContext<FormFieldContextValue>(
  {} as FormFieldContextValue
)

const FormField = <
  TFieldValues extends FieldValues = FieldValues,
  TName extends FieldPath<TFieldValues> = FieldPath<TFieldValues>,
>({
  ...props
}: ControllerProps<TFieldValues, TName>) => {
  return (
    <FormFieldContext.Provider value={{ name: props.name }}>
      <Controller {...props} />
    </FormFieldContext.Provider>
  )
}

const useFormField = () => {
  const fieldContext = React.useContext(FormFieldContext)
  const itemContext = React.useContext(FormItemContext)
  const { getFieldState } = useFormContext()
  const formState = useFormState({ name: fieldContext.name })
  const fieldState = getFieldState(fieldContext.name, formState)

  if (!fieldContext) {
    throw new Error("useFormField should be used within <FormField>")
  }

  const { id } = itemContext

  return {
    id,
    name: fieldContext.name,
    formItemId: `${id}-form-item`,
    formDescriptionId: `${id}-form-item-description`,
    formMessageId: `${id}-form-item-message`,
    ...fieldState,
  }
}

type FormItemContextValue = {
  id: string
}

const FormItemContext = React.createContext<FormItemContextValue>(
  {} as FormItemContextValue
)

function FormItem({ className, ...props }: React.ComponentProps<"div">) {
  const id = React.useId()

  return (
    <FormItemContext.Provider value={{ id }}>
      <div
        data-slot="form-item"
        className={cn("grid gap-2", className)}
        {...props}
      />
    </FormItemContext.Provider>
  )
}

function FormLabel({
  className,
  ...props
}: React.ComponentProps<typeof LabelPrimitive.Root>) {
  const { error, formItemId } = useFormField()

  return (
    <Label
      data-slot="form-label"
      data-error={!!error}
      className={cn("data-[error=true]:text-destructive", className)}
      htmlFor={formItemId}
      {...props}
    />
  )
}

function FormControl({ ...props }: React.ComponentProps<typeof Slot>) {
  const { error, formItemId, formDescriptionId, formMessageId } = useFormField()

  return (
    <Slot
      data-slot="form-control"
      id={formItemId}
      aria-describedby={
        !error
          ? `${formDescriptionId}`
          : `${formDescriptionId} ${formMessageId}`
      }
      aria-invalid={!!error}
      {...props}
    />
  )
}

function FormDescription({ className, ...props }: React.ComponentProps<"p">) {
  const { formDescriptionId } = useFormField()

  return (
    <p
      data-slot="form-description"
      id={formDescriptionId}
      className={cn("text-muted-foreground text-sm", className)}
      {...props}
    />
  )
}

function FormMessage({ className, ...props }: React.ComponentProps<"p">) {
  const { error, formMessageId } = useFormField()
  const body = error ? String(error?.message ?? "") : props.children

  if (!body) {
    return null
  }

  return (
    <p
      data-slot="form-message"
      id={formMessageId}
      className={cn("text-destructive text-sm", className)}
      {...props}
    >
      {body}
    </p>
  )
}

export {
  useFormField,
  Form,
  FormItem,
  FormLabel,
  FormControl,
  FormDescription,
  FormMessage,
  FormField,
}



================================================================================
FILE: app/src/components/ui/hover-card.tsx
================================================================================

"use client"

import * as React from "react"
import * as HoverCardPrimitive from "@radix-ui/react-hover-card"

import { cn } from "@/lib/utils"

function HoverCard({
  ...props
}: React.ComponentProps<typeof HoverCardPrimitive.Root>) {
  return <HoverCardPrimitive.Root data-slot="hover-card" {...props} />
}

function HoverCardTrigger({
  ...props
}: React.ComponentProps<typeof HoverCardPrimitive.Trigger>) {
  return (
    <HoverCardPrimitive.Trigger data-slot="hover-card-trigger" {...props} />
  )
}

function HoverCardContent({
  className,
  align = "center",
  sideOffset = 4,
  ...props
}: React.ComponentProps<typeof HoverCardPrimitive.Content>) {
  return (
    <HoverCardPrimitive.Portal data-slot="hover-card-portal">
      <HoverCardPrimitive.Content
        data-slot="hover-card-content"
        align={align}
        sideOffset={sideOffset}
        className={cn(
          "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 w-64 origin-(--radix-hover-card-content-transform-origin) rounded-md border p-4 shadow-md outline-hidden",
          className
        )}
        {...props}
      />
    </HoverCardPrimitive.Portal>
  )
}

export { HoverCard, HoverCardTrigger, HoverCardContent }



================================================================================
FILE: app/src/components/ui/input-group.tsx
================================================================================

"use client"

import * as React from "react"
import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"
import { Button } from "@/components/ui/button"
import { Input } from "@/components/ui/input"
import { Textarea } from "@/components/ui/textarea"

function InputGroup({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="input-group"
      role="group"
      className={cn(
        "group/input-group border-input dark:bg-input/30 relative flex w-full items-center rounded-md border shadow-xs transition-[color,box-shadow] outline-none",
        "h-9 min-w-0 has-[>textarea]:h-auto",

        // Variants based on alignment.
        "has-[>[data-align=inline-start]]:[&>input]:pl-2",
        "has-[>[data-align=inline-end]]:[&>input]:pr-2",
        "has-[>[data-align=block-start]]:h-auto has-[>[data-align=block-start]]:flex-col has-[>[data-align=block-start]]:[&>input]:pb-3",
        "has-[>[data-align=block-end]]:h-auto has-[>[data-align=block-end]]:flex-col has-[>[data-align=block-end]]:[&>input]:pt-3",

        // Focus state.
        "has-[[data-slot=input-group-control]:focus-visible]:border-ring has-[[data-slot=input-group-control]:focus-visible]:ring-ring/50 has-[[data-slot=input-group-control]:focus-visible]:ring-[3px]",

        // Error state.
        "has-[[data-slot][aria-invalid=true]]:ring-destructive/20 has-[[data-slot][aria-invalid=true]]:border-destructive dark:has-[[data-slot][aria-invalid=true]]:ring-destructive/40",

        className
      )}
      {...props}
    />
  )
}

const inputGroupAddonVariants = cva(
  "text-muted-foreground flex h-auto cursor-text items-center justify-center gap-2 py-1.5 text-sm font-medium select-none [&>svg:not([class*='size-'])]:size-4 [&>kbd]:rounded-[calc(var(--radius)-5px)] group-data-[disabled=true]/input-group:opacity-50",
  {
    variants: {
      align: {
        "inline-start":
          "order-first pl-3 has-[>button]:ml-[-0.45rem] has-[>kbd]:ml-[-0.35rem]",
        "inline-end":
          "order-last pr-3 has-[>button]:mr-[-0.45rem] has-[>kbd]:mr-[-0.35rem]",
        "block-start":
          "order-first w-full justify-start px-3 pt-3 [.border-b]:pb-3 group-has-[>input]/input-group:pt-2.5",
        "block-end":
          "order-last w-full justify-start px-3 pb-3 [.border-t]:pt-3 group-has-[>input]/input-group:pb-2.5",
      },
    },
    defaultVariants: {
      align: "inline-start",
    },
  }
)

function InputGroupAddon({
  className,
  align = "inline-start",
  ...props
}: React.ComponentProps<"div"> & VariantProps<typeof inputGroupAddonVariants>) {
  return (
    <div
      role="group"
      data-slot="input-group-addon"
      data-align={align}
      className={cn(inputGroupAddonVariants({ align }), className)}
      onClick={(e) => {
        if ((e.target as HTMLElement).closest("button")) {
          return
        }
        e.currentTarget.parentElement?.querySelector("input")?.focus()
      }}
      {...props}
    />
  )
}

const inputGroupButtonVariants = cva(
  "text-sm shadow-none flex gap-2 items-center",
  {
    variants: {
      size: {
        xs: "h-6 gap-1 px-2 rounded-[calc(var(--radius)-5px)] [&>svg:not([class*='size-'])]:size-3.5 has-[>svg]:px-2",
        sm: "h-8 px-2.5 gap-1.5 rounded-md has-[>svg]:px-2.5",
        "icon-xs":
          "size-6 rounded-[calc(var(--radius)-5px)] p-0 has-[>svg]:p-0",
        "icon-sm": "size-8 p-0 has-[>svg]:p-0",
      },
    },
    defaultVariants: {
      size: "xs",
    },
  }
)

function InputGroupButton({
  className,
  type = "button",
  variant = "ghost",
  size = "xs",
  ...props
}: Omit<React.ComponentProps<typeof Button>, "size"> &
  VariantProps<typeof inputGroupButtonVariants>) {
  return (
    <Button
      type={type}
      data-size={size}
      variant={variant}
      className={cn(inputGroupButtonVariants({ size }), className)}
      {...props}
    />
  )
}

function InputGroupText({ className, ...props }: React.ComponentProps<"span">) {
  return (
    <span
      className={cn(
        "text-muted-foreground flex items-center gap-2 text-sm [&_svg]:pointer-events-none [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    />
  )
}

function InputGroupInput({
  className,
  ...props
}: React.ComponentProps<"input">) {
  return (
    <Input
      data-slot="input-group-control"
      className={cn(
        "flex-1 rounded-none border-0 bg-transparent shadow-none focus-visible:ring-0 dark:bg-transparent",
        className
      )}
      {...props}
    />
  )
}

function InputGroupTextarea({
  className,
  ...props
}: React.ComponentProps<"textarea">) {
  return (
    <Textarea
      data-slot="input-group-control"
      className={cn(
        "flex-1 resize-none rounded-none border-0 bg-transparent py-3 shadow-none focus-visible:ring-0 dark:bg-transparent",
        className
      )}
      {...props}
    />
  )
}

export {
  InputGroup,
  InputGroupAddon,
  InputGroupButton,
  InputGroupText,
  InputGroupInput,
  InputGroupTextarea,
}



================================================================================
FILE: app/src/components/ui/input-otp.tsx
================================================================================

import * as React from "react"
import { OTPInput, OTPInputContext } from "input-otp"
import { MinusIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function InputOTP({
  className,
  containerClassName,
  ...props
}: React.ComponentProps<typeof OTPInput> & {
  containerClassName?: string
}) {
  return (
    <OTPInput
      data-slot="input-otp"
      containerClassName={cn(
        "flex items-center gap-2 has-disabled:opacity-50",
        containerClassName
      )}
      className={cn("disabled:cursor-not-allowed", className)}
      {...props}
    />
  )
}

function InputOTPGroup({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="input-otp-group"
      className={cn("flex items-center", className)}
      {...props}
    />
  )
}

function InputOTPSlot({
  index,
  className,
  ...props
}: React.ComponentProps<"div"> & {
  index: number
}) {
  const inputOTPContext = React.useContext(OTPInputContext)
  const { char, hasFakeCaret, isActive } = inputOTPContext?.slots[index] ?? {}

  return (
    <div
      data-slot="input-otp-slot"
      data-active={isActive}
      className={cn(
        "data-[active=true]:border-ring data-[active=true]:ring-ring/50 data-[active=true]:aria-invalid:ring-destructive/20 dark:data-[active=true]:aria-invalid:ring-destructive/40 aria-invalid:border-destructive data-[active=true]:aria-invalid:border-destructive dark:bg-input/30 border-input relative flex h-9 w-9 items-center justify-center border-y border-r text-sm shadow-xs transition-all outline-none first:rounded-l-md first:border-l last:rounded-r-md data-[active=true]:z-10 data-[active=true]:ring-[3px]",
        className
      )}
      {...props}
    >
      {char}
      {hasFakeCaret && (
        <div className="pointer-events-none absolute inset-0 flex items-center justify-center">
          <div className="animate-caret-blink bg-foreground h-4 w-px duration-1000" />
        </div>
      )}
    </div>
  )
}

function InputOTPSeparator({ ...props }: React.ComponentProps<"div">) {
  return (
    <div data-slot="input-otp-separator" role="separator" {...props}>
      <MinusIcon />
    </div>
  )
}

export { InputOTP, InputOTPGroup, InputOTPSlot, InputOTPSeparator }



================================================================================
FILE: app/src/components/ui/input.tsx
================================================================================

import * as React from "react"

import { cn } from "@/lib/utils"

function Input({ className, type, ...props }: React.ComponentProps<"input">) {
  return (
    <input
      type={type}
      data-slot="input"
      className={cn(
        "file:text-foreground placeholder:text-muted-foreground selection:bg-primary selection:text-primary-foreground dark:bg-input/30 border-input h-9 w-full min-w-0 rounded-md border bg-transparent px-3 py-1 text-base shadow-xs transition-[color,box-shadow] outline-none file:inline-flex file:h-7 file:border-0 file:bg-transparent file:text-sm file:font-medium disabled:pointer-events-none disabled:cursor-not-allowed disabled:opacity-50 md:text-sm",
        "focus-visible:border-ring focus-visible:ring-ring/50 focus-visible:ring-[3px]",
        "aria-invalid:ring-destructive/20 dark:aria-invalid:ring-destructive/40 aria-invalid:border-destructive",
        className
      )}
      {...props}
    />
  )
}

export { Input }



================================================================================
FILE: app/src/components/ui/item.tsx
================================================================================

import * as React from "react"
import { Slot } from "@radix-ui/react-slot"
import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"
import { Separator } from "@/components/ui/separator"

function ItemGroup({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      role="list"
      data-slot="item-group"
      className={cn("group/item-group flex flex-col", className)}
      {...props}
    />
  )
}

function ItemSeparator({
  className,
  ...props
}: React.ComponentProps<typeof Separator>) {
  return (
    <Separator
      data-slot="item-separator"
      orientation="horizontal"
      className={cn("my-0", className)}
      {...props}
    />
  )
}

const itemVariants = cva(
  "group/item flex items-center border border-transparent text-sm rounded-md transition-colors [a]:hover:bg-accent/50 [a]:transition-colors duration-100 flex-wrap outline-none focus-visible:border-ring focus-visible:ring-ring/50 focus-visible:ring-[3px]",
  {
    variants: {
      variant: {
        default: "bg-transparent",
        outline: "border-border",
        muted: "bg-muted/50",
      },
      size: {
        default: "p-4 gap-4 ",
        sm: "py-3 px-4 gap-2.5",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
)

function Item({
  className,
  variant = "default",
  size = "default",
  asChild = false,
  ...props
}: React.ComponentProps<"div"> &
  VariantProps<typeof itemVariants> & { asChild?: boolean }) {
  const Comp = asChild ? Slot : "div"
  return (
    <Comp
      data-slot="item"
      data-variant={variant}
      data-size={size}
      className={cn(itemVariants({ variant, size, className }))}
      {...props}
    />
  )
}

const itemMediaVariants = cva(
  "flex shrink-0 items-center justify-center gap-2 group-has-[[data-slot=item-description]]/item:self-start [&_svg]:pointer-events-none group-has-[[data-slot=item-description]]/item:translate-y-0.5",
  {
    variants: {
      variant: {
        default: "bg-transparent",
        icon: "size-8 border rounded-sm bg-muted [&_svg:not([class*='size-'])]:size-4",
        image:
          "size-10 rounded-sm overflow-hidden [&_img]:size-full [&_img]:object-cover",
      },
    },
    defaultVariants: {
      variant: "default",
    },
  }
)

function ItemMedia({
  className,
  variant = "default",
  ...props
}: React.ComponentProps<"div"> & VariantProps<typeof itemMediaVariants>) {
  return (
    <div
      data-slot="item-media"
      data-variant={variant}
      className={cn(itemMediaVariants({ variant, className }))}
      {...props}
    />
  )
}

function ItemContent({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="item-content"
      className={cn(
        "flex flex-1 flex-col gap-1 [&+[data-slot=item-content]]:flex-none",
        className
      )}
      {...props}
    />
  )
}

function ItemTitle({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="item-title"
      className={cn(
        "flex w-fit items-center gap-2 text-sm leading-snug font-medium",
        className
      )}
      {...props}
    />
  )
}

function ItemDescription({ className, ...props }: React.ComponentProps<"p">) {
  return (
    <p
      data-slot="item-description"
      className={cn(
        "text-muted-foreground line-clamp-2 text-sm leading-normal font-normal text-balance",
        "[&>a:hover]:text-primary [&>a]:underline [&>a]:underline-offset-4",
        className
      )}
      {...props}
    />
  )
}

function ItemActions({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="item-actions"
      className={cn("flex items-center gap-2", className)}
      {...props}
    />
  )
}

function ItemHeader({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="item-header"
      className={cn(
        "flex basis-full items-center justify-between gap-2",
        className
      )}
      {...props}
    />
  )
}

function ItemFooter({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="item-footer"
      className={cn(
        "flex basis-full items-center justify-between gap-2",
        className
      )}
      {...props}
    />
  )
}

export {
  Item,
  ItemMedia,
  ItemContent,
  ItemActions,
  ItemGroup,
  ItemSeparator,
  ItemTitle,
  ItemDescription,
  ItemHeader,
  ItemFooter,
}



================================================================================
FILE: app/src/components/ui/kbd.tsx
================================================================================

import { cn } from "@/lib/utils"

function Kbd({ className, ...props }: React.ComponentProps<"kbd">) {
  return (
    <kbd
      data-slot="kbd"
      className={cn(
        "bg-muted text-muted-foreground pointer-events-none inline-flex h-5 w-fit min-w-5 items-center justify-center gap-1 rounded-sm px-1 font-sans text-xs font-medium select-none",
        "[&_svg:not([class*='size-'])]:size-3",
        "[[data-slot=tooltip-content]_&]:bg-background/20 [[data-slot=tooltip-content]_&]:text-background dark:[[data-slot=tooltip-content]_&]:bg-background/10",
        className
      )}
      {...props}
    />
  )
}

function KbdGroup({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <kbd
      data-slot="kbd-group"
      className={cn("inline-flex items-center gap-1", className)}
      {...props}
    />
  )
}

export { Kbd, KbdGroup }



================================================================================
FILE: app/src/components/ui/label.tsx
================================================================================

"use client"

import * as React from "react"
import * as LabelPrimitive from "@radix-ui/react-label"

import { cn } from "@/lib/utils"

function Label({
  className,
  ...props
}: React.ComponentProps<typeof LabelPrimitive.Root>) {
  return (
    <LabelPrimitive.Root
      data-slot="label"
      className={cn(
        "flex items-center gap-2 text-sm leading-none font-medium select-none group-data-[disabled=true]:pointer-events-none group-data-[disabled=true]:opacity-50 peer-disabled:cursor-not-allowed peer-disabled:opacity-50",
        className
      )}
      {...props}
    />
  )
}

export { Label }



================================================================================
FILE: app/src/components/ui/menubar.tsx
================================================================================

import * as React from "react"
import * as MenubarPrimitive from "@radix-ui/react-menubar"
import { CheckIcon, ChevronRightIcon, CircleIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function Menubar({
  className,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Root>) {
  return (
    <MenubarPrimitive.Root
      data-slot="menubar"
      className={cn(
        "bg-background flex h-9 items-center gap-1 rounded-md border p-1 shadow-xs",
        className
      )}
      {...props}
    />
  )
}

function MenubarMenu({
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Menu>) {
  return <MenubarPrimitive.Menu data-slot="menubar-menu" {...props} />
}

function MenubarGroup({
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Group>) {
  return <MenubarPrimitive.Group data-slot="menubar-group" {...props} />
}

function MenubarPortal({
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Portal>) {
  return <MenubarPrimitive.Portal data-slot="menubar-portal" {...props} />
}

function MenubarRadioGroup({
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.RadioGroup>) {
  return (
    <MenubarPrimitive.RadioGroup data-slot="menubar-radio-group" {...props} />
  )
}

function MenubarTrigger({
  className,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Trigger>) {
  return (
    <MenubarPrimitive.Trigger
      data-slot="menubar-trigger"
      className={cn(
        "focus:bg-accent focus:text-accent-foreground data-[state=open]:bg-accent data-[state=open]:text-accent-foreground flex items-center rounded-sm px-2 py-1 text-sm font-medium outline-hidden select-none",
        className
      )}
      {...props}
    />
  )
}

function MenubarContent({
  className,
  align = "start",
  alignOffset = -4,
  sideOffset = 8,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Content>) {
  return (
    <MenubarPortal>
      <MenubarPrimitive.Content
        data-slot="menubar-content"
        align={align}
        alignOffset={alignOffset}
        sideOffset={sideOffset}
        className={cn(
          "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 min-w-[12rem] origin-(--radix-menubar-content-transform-origin) overflow-hidden rounded-md border p-1 shadow-md",
          className
        )}
        {...props}
      />
    </MenubarPortal>
  )
}

function MenubarItem({
  className,
  inset,
  variant = "default",
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Item> & {
  inset?: boolean
  variant?: "default" | "destructive"
}) {
  return (
    <MenubarPrimitive.Item
      data-slot="menubar-item"
      data-inset={inset}
      data-variant={variant}
      className={cn(
        "focus:bg-accent focus:text-accent-foreground data-[variant=destructive]:text-destructive data-[variant=destructive]:focus:bg-destructive/10 dark:data-[variant=destructive]:focus:bg-destructive/20 data-[variant=destructive]:focus:text-destructive data-[variant=destructive]:*:[svg]:!text-destructive [&_svg:not([class*='text-'])]:text-muted-foreground relative flex cursor-default items-center gap-2 rounded-sm px-2 py-1.5 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 data-[inset]:pl-8 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    />
  )
}

function MenubarCheckboxItem({
  className,
  children,
  checked,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.CheckboxItem>) {
  return (
    <MenubarPrimitive.CheckboxItem
      data-slot="menubar-checkbox-item"
      className={cn(
        "focus:bg-accent focus:text-accent-foreground relative flex cursor-default items-center gap-2 rounded-xs py-1.5 pr-2 pl-8 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      checked={checked}
      {...props}
    >
      <span className="pointer-events-none absolute left-2 flex size-3.5 items-center justify-center">
        <MenubarPrimitive.ItemIndicator>
          <CheckIcon className="size-4" />
        </MenubarPrimitive.ItemIndicator>
      </span>
      {children}
    </MenubarPrimitive.CheckboxItem>
  )
}

function MenubarRadioItem({
  className,
  children,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.RadioItem>) {
  return (
    <MenubarPrimitive.RadioItem
      data-slot="menubar-radio-item"
      className={cn(
        "focus:bg-accent focus:text-accent-foreground relative flex cursor-default items-center gap-2 rounded-xs py-1.5 pr-2 pl-8 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    >
      <span className="pointer-events-none absolute left-2 flex size-3.5 items-center justify-center">
        <MenubarPrimitive.ItemIndicator>
          <CircleIcon className="size-2 fill-current" />
        </MenubarPrimitive.ItemIndicator>
      </span>
      {children}
    </MenubarPrimitive.RadioItem>
  )
}

function MenubarLabel({
  className,
  inset,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Label> & {
  inset?: boolean
}) {
  return (
    <MenubarPrimitive.Label
      data-slot="menubar-label"
      data-inset={inset}
      className={cn(
        "px-2 py-1.5 text-sm font-medium data-[inset]:pl-8",
        className
      )}
      {...props}
    />
  )
}

function MenubarSeparator({
  className,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Separator>) {
  return (
    <MenubarPrimitive.Separator
      data-slot="menubar-separator"
      className={cn("bg-border -mx-1 my-1 h-px", className)}
      {...props}
    />
  )
}

function MenubarShortcut({
  className,
  ...props
}: React.ComponentProps<"span">) {
  return (
    <span
      data-slot="menubar-shortcut"
      className={cn(
        "text-muted-foreground ml-auto text-xs tracking-widest",
        className
      )}
      {...props}
    />
  )
}

function MenubarSub({
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.Sub>) {
  return <MenubarPrimitive.Sub data-slot="menubar-sub" {...props} />
}

function MenubarSubTrigger({
  className,
  inset,
  children,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.SubTrigger> & {
  inset?: boolean
}) {
  return (
    <MenubarPrimitive.SubTrigger
      data-slot="menubar-sub-trigger"
      data-inset={inset}
      className={cn(
        "focus:bg-accent focus:text-accent-foreground data-[state=open]:bg-accent data-[state=open]:text-accent-foreground flex cursor-default items-center rounded-sm px-2 py-1.5 text-sm outline-none select-none data-[inset]:pl-8",
        className
      )}
      {...props}
    >
      {children}
      <ChevronRightIcon className="ml-auto h-4 w-4" />
    </MenubarPrimitive.SubTrigger>
  )
}

function MenubarSubContent({
  className,
  ...props
}: React.ComponentProps<typeof MenubarPrimitive.SubContent>) {
  return (
    <MenubarPrimitive.SubContent
      data-slot="menubar-sub-content"
      className={cn(
        "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 min-w-[8rem] origin-(--radix-menubar-content-transform-origin) overflow-hidden rounded-md border p-1 shadow-lg",
        className
      )}
      {...props}
    />
  )
}

export {
  Menubar,
  MenubarPortal,
  MenubarMenu,
  MenubarTrigger,
  MenubarContent,
  MenubarGroup,
  MenubarSeparator,
  MenubarLabel,
  MenubarItem,
  MenubarShortcut,
  MenubarCheckboxItem,
  MenubarRadioGroup,
  MenubarRadioItem,
  MenubarSub,
  MenubarSubTrigger,
  MenubarSubContent,
}



================================================================================
FILE: app/src/components/ui/navigation-menu.tsx
================================================================================

import * as React from "react"
import * as NavigationMenuPrimitive from "@radix-ui/react-navigation-menu"
import { cva } from "class-variance-authority"
import { ChevronDownIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function NavigationMenu({
  className,
  children,
  viewport = true,
  ...props
}: React.ComponentProps<typeof NavigationMenuPrimitive.Root> & {
  viewport?: boolean
}) {
  return (
    <NavigationMenuPrimitive.Root
      data-slot="navigation-menu"
      data-viewport={viewport}
      className={cn(
        "group/navigation-menu relative flex max-w-max flex-1 items-center justify-center",
        className
      )}
      {...props}
    >
      {children}
      {viewport && <NavigationMenuViewport />}
    </NavigationMenuPrimitive.Root>
  )
}

function NavigationMenuList({
  className,
  ...props
}: React.ComponentProps<typeof NavigationMenuPrimitive.List>) {
  return (
    <NavigationMenuPrimitive.List
      data-slot="navigation-menu-list"
      className={cn(
        "group flex flex-1 list-none items-center justify-center gap-1",
        className
      )}
      {...props}
    />
  )
}

function NavigationMenuItem({
  className,
  ...props
}: React.ComponentProps<typeof NavigationMenuPrimitive.Item>) {
  return (
    <NavigationMenuPrimitive.Item
      data-slot="navigation-menu-item"
      className={cn("relative", className)}
      {...props}
    />
  )
}

const navigationMenuTriggerStyle = cva(
  "group inline-flex h-9 w-max items-center justify-center rounded-md bg-background px-4 py-2 text-sm font-medium hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground disabled:pointer-events-none disabled:opacity-50 data-[state=open]:hover:bg-accent data-[state=open]:text-accent-foreground data-[state=open]:focus:bg-accent data-[state=open]:bg-accent/50 focus-visible:ring-ring/50 outline-none transition-[color,box-shadow] focus-visible:ring-[3px] focus-visible:outline-1"
)

function NavigationMenuTrigger({
  className,
  children,
  ...props
}: React.ComponentProps<typeof NavigationMenuPrimitive.Trigger>) {
  return (
    <NavigationMenuPrimitive.Trigger
      data-slot="navigation-menu-trigger"
      className={cn(navigationMenuTriggerStyle(), "group", className)}
      {...props}
    >
      {children}{" "}
      <ChevronDownIcon
        className="relative top-[1px] ml-1 size-3 transition duration-300 group-data-[state=open]:rotate-180"
        aria-hidden="true"
      />
    </NavigationMenuPrimitive.Trigger>
  )
}

function NavigationMenuContent({
  className,
  ...props
}: React.ComponentProps<typeof NavigationMenuPrimitive.Content>) {
  return (
    <NavigationMenuPrimitive.Content
      data-slot="navigation-menu-content"
      className={cn(
        "data-[motion^=from-]:animate-in data-[motion^=to-]:animate-out data-[motion^=from-]:fade-in data-[motion^=to-]:fade-out data-[motion=from-end]:slide-in-from-right-52 data-[motion=from-start]:slide-in-from-left-52 data-[motion=to-end]:slide-out-to-right-52 data-[motion=to-start]:slide-out-to-left-52 top-0 left-0 w-full p-2 pr-2.5 md:absolute md:w-auto",
        "group-data-[viewport=false]/navigation-menu:bg-popover group-data-[viewport=false]/navigation-menu:text-popover-foreground group-data-[viewport=false]/navigation-menu:data-[state=open]:animate-in group-data-[viewport=false]/navigation-menu:data-[state=closed]:animate-out group-data-[viewport=false]/navigation-menu:data-[state=closed]:zoom-out-95 group-data-[viewport=false]/navigation-menu:data-[state=open]:zoom-in-95 group-data-[viewport=false]/navigation-menu:data-[state=open]:fade-in-0 group-data-[viewport=false]/navigation-menu:data-[state=closed]:fade-out-0 group-data-[viewport=false]/navigation-menu:top-full group-data-[viewport=false]/navigation-menu:mt-1.5 group-data-[viewport=false]/navigation-menu:overflow-hidden group-data-[viewport=false]/navigation-menu:rounded-md group-data-[viewport=false]/navigation-menu:border group-data-[viewport=false]/navigation-menu:shadow group-data-[viewport=false]/navigation-menu:duration-200 **:data-[slot=navigation-menu-link]:focus:ring-0 **:data-[slot=navigation-menu-link]:focus:outline-none",
        className
      )}
      {...props}
    />
  )
}

function NavigationMenuViewport({
  className,
  ...props
}: React.ComponentProps<typeof NavigationMenuPrimitive.Viewport>) {
  return (
    <div
      className={cn(
        "absolute top-full left-0 isolate z-50 flex justify-center"
      )}
    >
      <NavigationMenuPrimitive.Viewport
        data-slot="navigation-menu-viewport"
        className={cn(
          "origin-top-center bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-90 relative mt-1.5 h-[var(--radix-navigation-menu-viewport-height)] w-full overflow-hidden rounded-md border shadow md:w-[var(--radix-navigation-menu-viewport-width)]",
          className
        )}
        {...props}
      />
    </div>
  )
}

function NavigationMenuLink({
  className,
  ...props
}: React.ComponentProps<typeof NavigationMenuPrimitive.Link>) {
  return (
    <NavigationMenuPrimitive.Link
      data-slot="navigation-menu-link"
      className={cn(
        "data-[active=true]:focus:bg-accent data-[active=true]:hover:bg-accent data-[active=true]:bg-accent/50 data-[active=true]:text-accent-foreground hover:bg-accent hover:text-accent-foreground focus:bg-accent focus:text-accent-foreground focus-visible:ring-ring/50 [&_svg:not([class*='text-'])]:text-muted-foreground flex flex-col gap-1 rounded-sm p-2 text-sm transition-all outline-none focus-visible:ring-[3px] focus-visible:outline-1 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    />
  )
}

function NavigationMenuIndicator({
  className,
  ...props
}: React.ComponentProps<typeof NavigationMenuPrimitive.Indicator>) {
  return (
    <NavigationMenuPrimitive.Indicator
      data-slot="navigation-menu-indicator"
      className={cn(
        "data-[state=visible]:animate-in data-[state=hidden]:animate-out data-[state=hidden]:fade-out data-[state=visible]:fade-in top-full z-[1] flex h-1.5 items-end justify-center overflow-hidden",
        className
      )}
      {...props}
    >
      <div className="bg-border relative top-[60%] h-2 w-2 rotate-45 rounded-tl-sm shadow-md" />
    </NavigationMenuPrimitive.Indicator>
  )
}

export {
  NavigationMenu,
  NavigationMenuList,
  NavigationMenuItem,
  NavigationMenuContent,
  NavigationMenuTrigger,
  NavigationMenuLink,
  NavigationMenuIndicator,
  NavigationMenuViewport,
  navigationMenuTriggerStyle,
}



================================================================================
FILE: app/src/components/ui/pagination.tsx
================================================================================

import * as React from "react"
import {
  ChevronLeftIcon,
  ChevronRightIcon,
  MoreHorizontalIcon,
} from "lucide-react"

import { cn } from "@/lib/utils"
import { buttonVariants, type Button } from "@/components/ui/button"

function Pagination({ className, ...props }: React.ComponentProps<"nav">) {
  return (
    <nav
      role="navigation"
      aria-label="pagination"
      data-slot="pagination"
      className={cn("mx-auto flex w-full justify-center", className)}
      {...props}
    />
  )
}

function PaginationContent({
  className,
  ...props
}: React.ComponentProps<"ul">) {
  return (
    <ul
      data-slot="pagination-content"
      className={cn("flex flex-row items-center gap-1", className)}
      {...props}
    />
  )
}

function PaginationItem({ ...props }: React.ComponentProps<"li">) {
  return <li data-slot="pagination-item" {...props} />
}

type PaginationLinkProps = {
  isActive?: boolean
} & Pick<React.ComponentProps<typeof Button>, "size"> &
  React.ComponentProps<"a">

function PaginationLink({
  className,
  isActive,
  size = "icon",
  ...props
}: PaginationLinkProps) {
  return (
    <a
      aria-current={isActive ? "page" : undefined}
      data-slot="pagination-link"
      data-active={isActive}
      className={cn(
        buttonVariants({
          variant: isActive ? "outline" : "ghost",
          size,
        }),
        className
      )}
      {...props}
    />
  )
}

function PaginationPrevious({
  className,
  ...props
}: React.ComponentProps<typeof PaginationLink>) {
  return (
    <PaginationLink
      aria-label="Go to previous page"
      size="default"
      className={cn("gap-1 px-2.5 sm:pl-2.5", className)}
      {...props}
    >
      <ChevronLeftIcon />
      <span className="hidden sm:block">Previous</span>
    </PaginationLink>
  )
}

function PaginationNext({
  className,
  ...props
}: React.ComponentProps<typeof PaginationLink>) {
  return (
    <PaginationLink
      aria-label="Go to next page"
      size="default"
      className={cn("gap-1 px-2.5 sm:pr-2.5", className)}
      {...props}
    >
      <span className="hidden sm:block">Next</span>
      <ChevronRightIcon />
    </PaginationLink>
  )
}

function PaginationEllipsis({
  className,
  ...props
}: React.ComponentProps<"span">) {
  return (
    <span
      aria-hidden
      data-slot="pagination-ellipsis"
      className={cn("flex size-9 items-center justify-center", className)}
      {...props}
    >
      <MoreHorizontalIcon className="size-4" />
      <span className="sr-only">More pages</span>
    </span>
  )
}

export {
  Pagination,
  PaginationContent,
  PaginationLink,
  PaginationItem,
  PaginationPrevious,
  PaginationNext,
  PaginationEllipsis,
}



================================================================================
FILE: app/src/components/ui/popover.tsx
================================================================================

"use client"

import * as React from "react"
import * as PopoverPrimitive from "@radix-ui/react-popover"

import { cn } from "@/lib/utils"

function Popover({
  ...props
}: React.ComponentProps<typeof PopoverPrimitive.Root>) {
  return <PopoverPrimitive.Root data-slot="popover" {...props} />
}

function PopoverTrigger({
  ...props
}: React.ComponentProps<typeof PopoverPrimitive.Trigger>) {
  return <PopoverPrimitive.Trigger data-slot="popover-trigger" {...props} />
}

function PopoverContent({
  className,
  align = "center",
  sideOffset = 4,
  ...props
}: React.ComponentProps<typeof PopoverPrimitive.Content>) {
  return (
    <PopoverPrimitive.Portal>
      <PopoverPrimitive.Content
        data-slot="popover-content"
        align={align}
        sideOffset={sideOffset}
        className={cn(
          "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 w-72 origin-(--radix-popover-content-transform-origin) rounded-md border p-4 shadow-md outline-hidden",
          className
        )}
        {...props}
      />
    </PopoverPrimitive.Portal>
  )
}

function PopoverAnchor({
  ...props
}: React.ComponentProps<typeof PopoverPrimitive.Anchor>) {
  return <PopoverPrimitive.Anchor data-slot="popover-anchor" {...props} />
}

export { Popover, PopoverTrigger, PopoverContent, PopoverAnchor }



================================================================================
FILE: app/src/components/ui/progress.tsx
================================================================================

import * as React from "react"
import * as ProgressPrimitive from "@radix-ui/react-progress"

import { cn } from "@/lib/utils"

function Progress({
  className,
  value,
  ...props
}: React.ComponentProps<typeof ProgressPrimitive.Root>) {
  return (
    <ProgressPrimitive.Root
      data-slot="progress"
      className={cn(
        "bg-primary/20 relative h-2 w-full overflow-hidden rounded-full",
        className
      )}
      {...props}
    >
      <ProgressPrimitive.Indicator
        data-slot="progress-indicator"
        className="bg-primary h-full w-full flex-1 transition-all"
        style={{ transform: `translateX(-${100 - (value || 0)}%)` }}
      />
    </ProgressPrimitive.Root>
  )
}

export { Progress }



================================================================================
FILE: app/src/components/ui/radio-group.tsx
================================================================================

"use client"

import * as React from "react"
import * as RadioGroupPrimitive from "@radix-ui/react-radio-group"
import { CircleIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function RadioGroup({
  className,
  ...props
}: React.ComponentProps<typeof RadioGroupPrimitive.Root>) {
  return (
    <RadioGroupPrimitive.Root
      data-slot="radio-group"
      className={cn("grid gap-3", className)}
      {...props}
    />
  )
}

function RadioGroupItem({
  className,
  ...props
}: React.ComponentProps<typeof RadioGroupPrimitive.Item>) {
  return (
    <RadioGroupPrimitive.Item
      data-slot="radio-group-item"
      className={cn(
        "border-input text-primary focus-visible:border-ring focus-visible:ring-ring/50 aria-invalid:ring-destructive/20 dark:aria-invalid:ring-destructive/40 aria-invalid:border-destructive dark:bg-input/30 aspect-square size-4 shrink-0 rounded-full border shadow-xs transition-[color,box-shadow] outline-none focus-visible:ring-[3px] disabled:cursor-not-allowed disabled:opacity-50",
        className
      )}
      {...props}
    >
      <RadioGroupPrimitive.Indicator
        data-slot="radio-group-indicator"
        className="relative flex items-center justify-center"
      >
        <CircleIcon className="fill-primary absolute top-1/2 left-1/2 size-2 -translate-x-1/2 -translate-y-1/2" />
      </RadioGroupPrimitive.Indicator>
    </RadioGroupPrimitive.Item>
  )
}

export { RadioGroup, RadioGroupItem }



================================================================================
FILE: app/src/components/ui/resizable.tsx
================================================================================

import * as React from "react"
import { GripVerticalIcon } from "lucide-react"
import * as ResizablePrimitive from "react-resizable-panels"

import { cn } from "@/lib/utils"

function ResizablePanelGroup({
  className,
  ...props
}: React.ComponentProps<typeof ResizablePrimitive.Group>) {
  return (
    <ResizablePrimitive.Group
      data-slot="resizable-panel-group"
      className={cn(
        "flex h-full w-full data-[panel-group-direction=vertical]:flex-col",
        className
      )}
      {...props}
    />
  )
}

function ResizablePanel({
  ...props
}: React.ComponentProps<typeof ResizablePrimitive.Panel>) {
  return <ResizablePrimitive.Panel data-slot="resizable-panel" {...props} />
}

function ResizableHandle({
  withHandle,
  className,
  ...props
}: React.ComponentProps<typeof ResizablePrimitive.Separator> & {
  withHandle?: boolean
}) {
  return (
    <ResizablePrimitive.Separator
      data-slot="resizable-handle"
      className={cn(
        "bg-border focus-visible:ring-ring relative flex w-px items-center justify-center after:absolute after:inset-y-0 after:left-1/2 after:w-1 after:-translate-x-1/2 focus-visible:ring-1 focus-visible:ring-offset-1 focus-visible:outline-hidden data-[panel-group-direction=vertical]:h-px data-[panel-group-direction=vertical]:w-full data-[panel-group-direction=vertical]:after:left-0 data-[panel-group-direction=vertical]:after:h-1 data-[panel-group-direction=vertical]:after:w-full data-[panel-group-direction=vertical]:after:translate-x-0 data-[panel-group-direction=vertical]:after:-translate-y-1/2 [&[data-panel-group-direction=vertical]>div]:rotate-90",
        className
      )}
      {...props}
    >
      {withHandle && (
        <div className="bg-border z-10 flex h-4 w-3 items-center justify-center rounded-xs border">
          <GripVerticalIcon className="size-2.5" />
        </div>
      )}
    </ResizablePrimitive.Separator>
  )
}

export { ResizablePanelGroup, ResizablePanel, ResizableHandle }



================================================================================
FILE: app/src/components/ui/scroll-area.tsx
================================================================================

"use client"

import * as React from "react"
import * as ScrollAreaPrimitive from "@radix-ui/react-scroll-area"

import { cn } from "@/lib/utils"

function ScrollArea({
  className,
  children,
  ...props
}: React.ComponentProps<typeof ScrollAreaPrimitive.Root>) {
  return (
    <ScrollAreaPrimitive.Root
      data-slot="scroll-area"
      className={cn("relative", className)}
      {...props}
    >
      <ScrollAreaPrimitive.Viewport
        data-slot="scroll-area-viewport"
        className="focus-visible:ring-ring/50 size-full rounded-[inherit] transition-[color,box-shadow] outline-none focus-visible:ring-[3px] focus-visible:outline-1"
      >
        {children}
      </ScrollAreaPrimitive.Viewport>
      <ScrollBar />
      <ScrollAreaPrimitive.Corner />
    </ScrollAreaPrimitive.Root>
  )
}

function ScrollBar({
  className,
  orientation = "vertical",
  ...props
}: React.ComponentProps<typeof ScrollAreaPrimitive.ScrollAreaScrollbar>) {
  return (
    <ScrollAreaPrimitive.ScrollAreaScrollbar
      data-slot="scroll-area-scrollbar"
      orientation={orientation}
      className={cn(
        "flex touch-none p-px transition-colors select-none",
        orientation === "vertical" &&
          "h-full w-2.5 border-l border-l-transparent",
        orientation === "horizontal" &&
          "h-2.5 flex-col border-t border-t-transparent",
        className
      )}
      {...props}
    >
      <ScrollAreaPrimitive.ScrollAreaThumb
        data-slot="scroll-area-thumb"
        className="bg-border relative flex-1 rounded-full"
      />
    </ScrollAreaPrimitive.ScrollAreaScrollbar>
  )
}

export { ScrollArea, ScrollBar }



================================================================================
FILE: app/src/components/ui/select.tsx
================================================================================

import * as React from "react"
import * as SelectPrimitive from "@radix-ui/react-select"
import { CheckIcon, ChevronDownIcon, ChevronUpIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function Select({
  ...props
}: React.ComponentProps<typeof SelectPrimitive.Root>) {
  return <SelectPrimitive.Root data-slot="select" {...props} />
}

function SelectGroup({
  ...props
}: React.ComponentProps<typeof SelectPrimitive.Group>) {
  return <SelectPrimitive.Group data-slot="select-group" {...props} />
}

function SelectValue({
  ...props
}: React.ComponentProps<typeof SelectPrimitive.Value>) {
  return <SelectPrimitive.Value data-slot="select-value" {...props} />
}

function SelectTrigger({
  className,
  size = "default",
  children,
  ...props
}: React.ComponentProps<typeof SelectPrimitive.Trigger> & {
  size?: "sm" | "default"
}) {
  return (
    <SelectPrimitive.Trigger
      data-slot="select-trigger"
      data-size={size}
      className={cn(
        "border-input data-[placeholder]:text-muted-foreground [&_svg:not([class*='text-'])]:text-muted-foreground focus-visible:border-ring focus-visible:ring-ring/50 aria-invalid:ring-destructive/20 dark:aria-invalid:ring-destructive/40 aria-invalid:border-destructive dark:bg-input/30 dark:hover:bg-input/50 flex w-fit items-center justify-between gap-2 rounded-md border bg-transparent px-3 py-2 text-sm whitespace-nowrap shadow-xs transition-[color,box-shadow] outline-none focus-visible:ring-[3px] disabled:cursor-not-allowed disabled:opacity-50 data-[size=default]:h-9 data-[size=sm]:h-8 *:data-[slot=select-value]:line-clamp-1 *:data-[slot=select-value]:flex *:data-[slot=select-value]:items-center *:data-[slot=select-value]:gap-2 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    >
      {children}
      <SelectPrimitive.Icon asChild>
        <ChevronDownIcon className="size-4 opacity-50" />
      </SelectPrimitive.Icon>
    </SelectPrimitive.Trigger>
  )
}

function SelectContent({
  className,
  children,
  position = "item-aligned",
  align = "center",
  ...props
}: React.ComponentProps<typeof SelectPrimitive.Content>) {
  return (
    <SelectPrimitive.Portal>
      <SelectPrimitive.Content
        data-slot="select-content"
        className={cn(
          "bg-popover text-popover-foreground data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 data-[state=closed]:zoom-out-95 data-[state=open]:zoom-in-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 relative z-50 max-h-(--radix-select-content-available-height) min-w-[8rem] origin-(--radix-select-content-transform-origin) overflow-x-hidden overflow-y-auto rounded-md border shadow-md",
          position === "popper" &&
            "data-[side=bottom]:translate-y-1 data-[side=left]:-translate-x-1 data-[side=right]:translate-x-1 data-[side=top]:-translate-y-1",
          className
        )}
        position={position}
        align={align}
        {...props}
      >
        <SelectScrollUpButton />
        <SelectPrimitive.Viewport
          className={cn(
            "p-1",
            position === "popper" &&
              "h-[var(--radix-select-trigger-height)] w-full min-w-[var(--radix-select-trigger-width)] scroll-my-1"
          )}
        >
          {children}
        </SelectPrimitive.Viewport>
        <SelectScrollDownButton />
      </SelectPrimitive.Content>
    </SelectPrimitive.Portal>
  )
}

function SelectLabel({
  className,
  ...props
}: React.ComponentProps<typeof SelectPrimitive.Label>) {
  return (
    <SelectPrimitive.Label
      data-slot="select-label"
      className={cn("text-muted-foreground px-2 py-1.5 text-xs", className)}
      {...props}
    />
  )
}

function SelectItem({
  className,
  children,
  ...props
}: React.ComponentProps<typeof SelectPrimitive.Item>) {
  return (
    <SelectPrimitive.Item
      data-slot="select-item"
      className={cn(
        "focus:bg-accent focus:text-accent-foreground [&_svg:not([class*='text-'])]:text-muted-foreground relative flex w-full cursor-default items-center gap-2 rounded-sm py-1.5 pr-8 pl-2 text-sm outline-hidden select-none data-[disabled]:pointer-events-none data-[disabled]:opacity-50 [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4 *:[span]:last:flex *:[span]:last:items-center *:[span]:last:gap-2",
        className
      )}
      {...props}
    >
      <span
        data-slot="select-item-indicator"
        className="absolute right-2 flex size-3.5 items-center justify-center"
      >
        <SelectPrimitive.ItemIndicator>
          <CheckIcon className="size-4" />
        </SelectPrimitive.ItemIndicator>
      </span>
      <SelectPrimitive.ItemText>{children}</SelectPrimitive.ItemText>
    </SelectPrimitive.Item>
  )
}

function SelectSeparator({
  className,
  ...props
}: React.ComponentProps<typeof SelectPrimitive.Separator>) {
  return (
    <SelectPrimitive.Separator
      data-slot="select-separator"
      className={cn("bg-border pointer-events-none -mx-1 my-1 h-px", className)}
      {...props}
    />
  )
}

function SelectScrollUpButton({
  className,
  ...props
}: React.ComponentProps<typeof SelectPrimitive.ScrollUpButton>) {
  return (
    <SelectPrimitive.ScrollUpButton
      data-slot="select-scroll-up-button"
      className={cn(
        "flex cursor-default items-center justify-center py-1",
        className
      )}
      {...props}
    >
      <ChevronUpIcon className="size-4" />
    </SelectPrimitive.ScrollUpButton>
  )
}

function SelectScrollDownButton({
  className,
  ...props
}: React.ComponentProps<typeof SelectPrimitive.ScrollDownButton>) {
  return (
    <SelectPrimitive.ScrollDownButton
      data-slot="select-scroll-down-button"
      className={cn(
        "flex cursor-default items-center justify-center py-1",
        className
      )}
      {...props}
    >
      <ChevronDownIcon className="size-4" />
    </SelectPrimitive.ScrollDownButton>
  )
}

export {
  Select,
  SelectContent,
  SelectGroup,
  SelectItem,
  SelectLabel,
  SelectScrollDownButton,
  SelectScrollUpButton,
  SelectSeparator,
  SelectTrigger,
  SelectValue,
}



================================================================================
FILE: app/src/components/ui/separator.tsx
================================================================================

"use client"

import * as React from "react"
import * as SeparatorPrimitive from "@radix-ui/react-separator"

import { cn } from "@/lib/utils"

function Separator({
  className,
  orientation = "horizontal",
  decorative = true,
  ...props
}: React.ComponentProps<typeof SeparatorPrimitive.Root>) {
  return (
    <SeparatorPrimitive.Root
      data-slot="separator"
      decorative={decorative}
      orientation={orientation}
      className={cn(
        "bg-border shrink-0 data-[orientation=horizontal]:h-px data-[orientation=horizontal]:w-full data-[orientation=vertical]:h-full data-[orientation=vertical]:w-px",
        className
      )}
      {...props}
    />
  )
}

export { Separator }



================================================================================
FILE: app/src/components/ui/sheet.tsx
================================================================================

import * as React from "react"
import * as SheetPrimitive from "@radix-ui/react-dialog"
import { XIcon } from "lucide-react"

import { cn } from "@/lib/utils"

function Sheet({ ...props }: React.ComponentProps<typeof SheetPrimitive.Root>) {
  return <SheetPrimitive.Root data-slot="sheet" {...props} />
}

function SheetTrigger({
  ...props
}: React.ComponentProps<typeof SheetPrimitive.Trigger>) {
  return <SheetPrimitive.Trigger data-slot="sheet-trigger" {...props} />
}

function SheetClose({
  ...props
}: React.ComponentProps<typeof SheetPrimitive.Close>) {
  return <SheetPrimitive.Close data-slot="sheet-close" {...props} />
}

function SheetPortal({
  ...props
}: React.ComponentProps<typeof SheetPrimitive.Portal>) {
  return <SheetPrimitive.Portal data-slot="sheet-portal" {...props} />
}

function SheetOverlay({
  className,
  ...props
}: React.ComponentProps<typeof SheetPrimitive.Overlay>) {
  return (
    <SheetPrimitive.Overlay
      data-slot="sheet-overlay"
      className={cn(
        "data-[state=open]:animate-in data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=open]:fade-in-0 fixed inset-0 z-50 bg-black/50",
        className
      )}
      {...props}
    />
  )
}

function SheetContent({
  className,
  children,
  side = "right",
  ...props
}: React.ComponentProps<typeof SheetPrimitive.Content> & {
  side?: "top" | "right" | "bottom" | "left"
}) {
  return (
    <SheetPortal>
      <SheetOverlay />
      <SheetPrimitive.Content
        data-slot="sheet-content"
        className={cn(
          "bg-background data-[state=open]:animate-in data-[state=closed]:animate-out fixed z-50 flex flex-col gap-4 shadow-lg transition ease-in-out data-[state=closed]:duration-300 data-[state=open]:duration-500",
          side === "right" &&
            "data-[state=closed]:slide-out-to-right data-[state=open]:slide-in-from-right inset-y-0 right-0 h-full w-3/4 border-l sm:max-w-sm",
          side === "left" &&
            "data-[state=closed]:slide-out-to-left data-[state=open]:slide-in-from-left inset-y-0 left-0 h-full w-3/4 border-r sm:max-w-sm",
          side === "top" &&
            "data-[state=closed]:slide-out-to-top data-[state=open]:slide-in-from-top inset-x-0 top-0 h-auto border-b",
          side === "bottom" &&
            "data-[state=closed]:slide-out-to-bottom data-[state=open]:slide-in-from-bottom inset-x-0 bottom-0 h-auto border-t",
          className
        )}
        {...props}
      >
        {children}
        <SheetPrimitive.Close className="ring-offset-background focus:ring-ring data-[state=open]:bg-secondary absolute top-4 right-4 rounded-xs opacity-70 transition-opacity hover:opacity-100 focus:ring-2 focus:ring-offset-2 focus:outline-hidden disabled:pointer-events-none">
          <XIcon className="size-4" />
          <span className="sr-only">Close</span>
        </SheetPrimitive.Close>
      </SheetPrimitive.Content>
    </SheetPortal>
  )
}

function SheetHeader({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="sheet-header"
      className={cn("flex flex-col gap-1.5 p-4", className)}
      {...props}
    />
  )
}

function SheetFooter({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="sheet-footer"
      className={cn("mt-auto flex flex-col gap-2 p-4", className)}
      {...props}
    />
  )
}

function SheetTitle({
  className,
  ...props
}: React.ComponentProps<typeof SheetPrimitive.Title>) {
  return (
    <SheetPrimitive.Title
      data-slot="sheet-title"
      className={cn("text-foreground font-semibold", className)}
      {...props}
    />
  )
}

function SheetDescription({
  className,
  ...props
}: React.ComponentProps<typeof SheetPrimitive.Description>) {
  return (
    <SheetPrimitive.Description
      data-slot="sheet-description"
      className={cn("text-muted-foreground text-sm", className)}
      {...props}
    />
  )
}

export {
  Sheet,
  SheetTrigger,
  SheetClose,
  SheetContent,
  SheetHeader,
  SheetFooter,
  SheetTitle,
  SheetDescription,
}



================================================================================
FILE: app/src/components/ui/sidebar.tsx
================================================================================

"use client"

import * as React from "react"
import { Slot } from "@radix-ui/react-slot"
import { cva, type VariantProps } from "class-variance-authority"
import { PanelLeftIcon } from "lucide-react"

import { useIsMobile } from "@/hooks/use-mobile"
import { cn } from "@/lib/utils"
import { Button } from "@/components/ui/button"
import { Input } from "@/components/ui/input"
import { Separator } from "@/components/ui/separator"
import {
  Sheet,
  SheetContent,
  SheetDescription,
  SheetHeader,
  SheetTitle,
} from "@/components/ui/sheet"
import { Skeleton } from "@/components/ui/skeleton"
import {
  Tooltip,
  TooltipContent,
  TooltipProvider,
  TooltipTrigger,
} from "@/components/ui/tooltip"

const SIDEBAR_COOKIE_NAME = "sidebar_state"
const SIDEBAR_COOKIE_MAX_AGE = 60 * 60 * 24 * 7
const SIDEBAR_WIDTH = "16rem"
const SIDEBAR_WIDTH_MOBILE = "18rem"
const SIDEBAR_WIDTH_ICON = "3rem"
const SIDEBAR_KEYBOARD_SHORTCUT = "b"

type SidebarContextProps = {
  state: "expanded" | "collapsed"
  open: boolean
  setOpen: (open: boolean) => void
  openMobile: boolean
  setOpenMobile: (open: boolean) => void
  isMobile: boolean
  toggleSidebar: () => void
}

const SidebarContext = React.createContext<SidebarContextProps | null>(null)

function useSidebar() {
  const context = React.useContext(SidebarContext)
  if (!context) {
    throw new Error("useSidebar must be used within a SidebarProvider.")
  }

  return context
}

function SidebarProvider({
  defaultOpen = true,
  open: openProp,
  onOpenChange: setOpenProp,
  className,
  style,
  children,
  ...props
}: React.ComponentProps<"div"> & {
  defaultOpen?: boolean
  open?: boolean
  onOpenChange?: (open: boolean) => void
}) {
  const isMobile = useIsMobile()
  const [openMobile, setOpenMobile] = React.useState(false)

  // This is the internal state of the sidebar.
  // We use openProp and setOpenProp for control from outside the component.
  const [_open, _setOpen] = React.useState(defaultOpen)
  const open = openProp ?? _open
  const setOpen = React.useCallback(
    (value: boolean | ((value: boolean) => boolean)) => {
      const openState = typeof value === "function" ? value(open) : value
      if (setOpenProp) {
        setOpenProp(openState)
      } else {
        _setOpen(openState)
      }

      // This sets the cookie to keep the sidebar state.
      document.cookie = `${SIDEBAR_COOKIE_NAME}=${openState}; path=/; max-age=${SIDEBAR_COOKIE_MAX_AGE}`
    },
    [setOpenProp, open]
  )

  // Helper to toggle the sidebar.
  const toggleSidebar = React.useCallback(() => {
    return isMobile ? setOpenMobile((open) => !open) : setOpen((open) => !open)
  }, [isMobile, setOpen, setOpenMobile])

  // Adds a keyboard shortcut to toggle the sidebar.
  React.useEffect(() => {
    const handleKeyDown = (event: KeyboardEvent) => {
      if (
        event.key === SIDEBAR_KEYBOARD_SHORTCUT &&
        (event.metaKey || event.ctrlKey)
      ) {
        event.preventDefault()
        toggleSidebar()
      }
    }

    window.addEventListener("keydown", handleKeyDown)
    return () => window.removeEventListener("keydown", handleKeyDown)
  }, [toggleSidebar])

  // We add a state so that we can do data-state="expanded" or "collapsed".
  // This makes it easier to style the sidebar with Tailwind classes.
  const state = open ? "expanded" : "collapsed"

  const contextValue = React.useMemo<SidebarContextProps>(
    () => ({
      state,
      open,
      setOpen,
      isMobile,
      openMobile,
      setOpenMobile,
      toggleSidebar,
    }),
    [state, open, setOpen, isMobile, openMobile, setOpenMobile, toggleSidebar]
  )

  return (
    <SidebarContext.Provider value={contextValue}>
      <TooltipProvider delayDuration={0}>
        <div
          data-slot="sidebar-wrapper"
          style={
            {
              "--sidebar-width": SIDEBAR_WIDTH,
              "--sidebar-width-icon": SIDEBAR_WIDTH_ICON,
              ...style,
            } as React.CSSProperties
          }
          className={cn(
            "group/sidebar-wrapper has-data-[variant=inset]:bg-sidebar flex min-h-svh w-full",
            className
          )}
          {...props}
        >
          {children}
        </div>
      </TooltipProvider>
    </SidebarContext.Provider>
  )
}

function Sidebar({
  side = "left",
  variant = "sidebar",
  collapsible = "offcanvas",
  className,
  children,
  ...props
}: React.ComponentProps<"div"> & {
  side?: "left" | "right"
  variant?: "sidebar" | "floating" | "inset"
  collapsible?: "offcanvas" | "icon" | "none"
}) {
  const { isMobile, state, openMobile, setOpenMobile } = useSidebar()

  if (collapsible === "none") {
    return (
      <div
        data-slot="sidebar"
        className={cn(
          "bg-sidebar text-sidebar-foreground flex h-full w-(--sidebar-width) flex-col",
          className
        )}
        {...props}
      >
        {children}
      </div>
    )
  }

  if (isMobile) {
    return (
      <Sheet open={openMobile} onOpenChange={setOpenMobile} {...props}>
        <SheetContent
          data-sidebar="sidebar"
          data-slot="sidebar"
          data-mobile="true"
          className="bg-sidebar text-sidebar-foreground w-(--sidebar-width) p-0 [&>button]:hidden"
          style={
            {
              "--sidebar-width": SIDEBAR_WIDTH_MOBILE,
            } as React.CSSProperties
          }
          side={side}
        >
          <SheetHeader className="sr-only">
            <SheetTitle>Sidebar</SheetTitle>
            <SheetDescription>Displays the mobile sidebar.</SheetDescription>
          </SheetHeader>
          <div className="flex h-full w-full flex-col">{children}</div>
        </SheetContent>
      </Sheet>
    )
  }

  return (
    <div
      className="group peer text-sidebar-foreground hidden md:block"
      data-state={state}
      data-collapsible={state === "collapsed" ? collapsible : ""}
      data-variant={variant}
      data-side={side}
      data-slot="sidebar"
    >
      {/* This is what handles the sidebar gap on desktop */}
      <div
        data-slot="sidebar-gap"
        className={cn(
          "relative w-(--sidebar-width) bg-transparent transition-[width] duration-200 ease-linear",
          "group-data-[collapsible=offcanvas]:w-0",
          "group-data-[side=right]:rotate-180",
          variant === "floating" || variant === "inset"
            ? "group-data-[collapsible=icon]:w-[calc(var(--sidebar-width-icon)+(--spacing(4)))]"
            : "group-data-[collapsible=icon]:w-(--sidebar-width-icon)"
        )}
      />
      <div
        data-slot="sidebar-container"
        className={cn(
          "fixed inset-y-0 z-10 hidden h-svh w-(--sidebar-width) transition-[left,right,width] duration-200 ease-linear md:flex",
          side === "left"
            ? "left-0 group-data-[collapsible=offcanvas]:left-[calc(var(--sidebar-width)*-1)]"
            : "right-0 group-data-[collapsible=offcanvas]:right-[calc(var(--sidebar-width)*-1)]",
          // Adjust the padding for floating and inset variants.
          variant === "floating" || variant === "inset"
            ? "p-2 group-data-[collapsible=icon]:w-[calc(var(--sidebar-width-icon)+(--spacing(4))+2px)]"
            : "group-data-[collapsible=icon]:w-(--sidebar-width-icon) group-data-[side=left]:border-r group-data-[side=right]:border-l",
          className
        )}
        {...props}
      >
        <div
          data-sidebar="sidebar"
          data-slot="sidebar-inner"
          className="bg-sidebar group-data-[variant=floating]:border-sidebar-border flex h-full w-full flex-col group-data-[variant=floating]:rounded-lg group-data-[variant=floating]:border group-data-[variant=floating]:shadow-sm"
        >
          {children}
        </div>
      </div>
    </div>
  )
}

function SidebarTrigger({
  className,
  onClick,
  ...props
}: React.ComponentProps<typeof Button>) {
  const { toggleSidebar } = useSidebar()

  return (
    <Button
      data-sidebar="trigger"
      data-slot="sidebar-trigger"
      variant="ghost"
      size="icon"
      className={cn("size-7", className)}
      onClick={(event) => {
        onClick?.(event)
        toggleSidebar()
      }}
      {...props}
    >
      <PanelLeftIcon />
      <span className="sr-only">Toggle Sidebar</span>
    </Button>
  )
}

function SidebarRail({ className, ...props }: React.ComponentProps<"button">) {
  const { toggleSidebar } = useSidebar()

  return (
    <button
      data-sidebar="rail"
      data-slot="sidebar-rail"
      aria-label="Toggle Sidebar"
      tabIndex={-1}
      onClick={toggleSidebar}
      title="Toggle Sidebar"
      className={cn(
        "hover:after:bg-sidebar-border absolute inset-y-0 z-20 hidden w-4 -translate-x-1/2 transition-all ease-linear group-data-[side=left]:-right-4 group-data-[side=right]:left-0 after:absolute after:inset-y-0 after:left-1/2 after:w-[2px] sm:flex",
        "in-data-[side=left]:cursor-w-resize in-data-[side=right]:cursor-e-resize",
        "[[data-side=left][data-state=collapsed]_&]:cursor-e-resize [[data-side=right][data-state=collapsed]_&]:cursor-w-resize",
        "hover:group-data-[collapsible=offcanvas]:bg-sidebar group-data-[collapsible=offcanvas]:translate-x-0 group-data-[collapsible=offcanvas]:after:left-full",
        "[[data-side=left][data-collapsible=offcanvas]_&]:-right-2",
        "[[data-side=right][data-collapsible=offcanvas]_&]:-left-2",
        className
      )}
      {...props}
    />
  )
}

function SidebarInset({ className, ...props }: React.ComponentProps<"main">) {
  return (
    <main
      data-slot="sidebar-inset"
      className={cn(
        "bg-background relative flex w-full flex-1 flex-col",
        "md:peer-data-[variant=inset]:m-2 md:peer-data-[variant=inset]:ml-0 md:peer-data-[variant=inset]:rounded-xl md:peer-data-[variant=inset]:shadow-sm md:peer-data-[variant=inset]:peer-data-[state=collapsed]:ml-2",
        className
      )}
      {...props}
    />
  )
}

function SidebarInput({
  className,
  ...props
}: React.ComponentProps<typeof Input>) {
  return (
    <Input
      data-slot="sidebar-input"
      data-sidebar="input"
      className={cn("bg-background h-8 w-full shadow-none", className)}
      {...props}
    />
  )
}

function SidebarHeader({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="sidebar-header"
      data-sidebar="header"
      className={cn("flex flex-col gap-2 p-2", className)}
      {...props}
    />
  )
}

function SidebarFooter({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="sidebar-footer"
      data-sidebar="footer"
      className={cn("flex flex-col gap-2 p-2", className)}
      {...props}
    />
  )
}

function SidebarSeparator({
  className,
  ...props
}: React.ComponentProps<typeof Separator>) {
  return (
    <Separator
      data-slot="sidebar-separator"
      data-sidebar="separator"
      className={cn("bg-sidebar-border mx-2 w-auto", className)}
      {...props}
    />
  )
}

function SidebarContent({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="sidebar-content"
      data-sidebar="content"
      className={cn(
        "flex min-h-0 flex-1 flex-col gap-2 overflow-auto group-data-[collapsible=icon]:overflow-hidden",
        className
      )}
      {...props}
    />
  )
}

function SidebarGroup({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="sidebar-group"
      data-sidebar="group"
      className={cn("relative flex w-full min-w-0 flex-col p-2", className)}
      {...props}
    />
  )
}

function SidebarGroupLabel({
  className,
  asChild = false,
  ...props
}: React.ComponentProps<"div"> & { asChild?: boolean }) {
  const Comp = asChild ? Slot : "div"

  return (
    <Comp
      data-slot="sidebar-group-label"
      data-sidebar="group-label"
      className={cn(
        "text-sidebar-foreground/70 ring-sidebar-ring flex h-8 shrink-0 items-center rounded-md px-2 text-xs font-medium outline-hidden transition-[margin,opacity] duration-200 ease-linear focus-visible:ring-2 [&>svg]:size-4 [&>svg]:shrink-0",
        "group-data-[collapsible=icon]:-mt-8 group-data-[collapsible=icon]:opacity-0",
        className
      )}
      {...props}
    />
  )
}

function SidebarGroupAction({
  className,
  asChild = false,
  ...props
}: React.ComponentProps<"button"> & { asChild?: boolean }) {
  const Comp = asChild ? Slot : "button"

  return (
    <Comp
      data-slot="sidebar-group-action"
      data-sidebar="group-action"
      className={cn(
        "text-sidebar-foreground ring-sidebar-ring hover:bg-sidebar-accent hover:text-sidebar-accent-foreground absolute top-3.5 right-3 flex aspect-square w-5 items-center justify-center rounded-md p-0 outline-hidden transition-transform focus-visible:ring-2 [&>svg]:size-4 [&>svg]:shrink-0",
        // Increases the hit area of the button on mobile.
        "after:absolute after:-inset-2 md:after:hidden",
        "group-data-[collapsible=icon]:hidden",
        className
      )}
      {...props}
    />
  )
}

function SidebarGroupContent({
  className,
  ...props
}: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="sidebar-group-content"
      data-sidebar="group-content"
      className={cn("w-full text-sm", className)}
      {...props}
    />
  )
}

function SidebarMenu({ className, ...props }: React.ComponentProps<"ul">) {
  return (
    <ul
      data-slot="sidebar-menu"
      data-sidebar="menu"
      className={cn("flex w-full min-w-0 flex-col gap-1", className)}
      {...props}
    />
  )
}

function SidebarMenuItem({ className, ...props }: React.ComponentProps<"li">) {
  return (
    <li
      data-slot="sidebar-menu-item"
      data-sidebar="menu-item"
      className={cn("group/menu-item relative", className)}
      {...props}
    />
  )
}

const sidebarMenuButtonVariants = cva(
  "peer/menu-button flex w-full items-center gap-2 overflow-hidden rounded-md p-2 text-left text-sm outline-hidden ring-sidebar-ring transition-[width,height,padding] hover:bg-sidebar-accent hover:text-sidebar-accent-foreground focus-visible:ring-2 active:bg-sidebar-accent active:text-sidebar-accent-foreground disabled:pointer-events-none disabled:opacity-50 group-has-data-[sidebar=menu-action]/menu-item:pr-8 aria-disabled:pointer-events-none aria-disabled:opacity-50 data-[active=true]:bg-sidebar-accent data-[active=true]:font-medium data-[active=true]:text-sidebar-accent-foreground data-[state=open]:hover:bg-sidebar-accent data-[state=open]:hover:text-sidebar-accent-foreground group-data-[collapsible=icon]:size-8! group-data-[collapsible=icon]:p-2! [&>span:last-child]:truncate [&>svg]:size-4 [&>svg]:shrink-0",
  {
    variants: {
      variant: {
        default: "hover:bg-sidebar-accent hover:text-sidebar-accent-foreground",
        outline:
          "bg-background shadow-[0_0_0_1px_hsl(var(--sidebar-border))] hover:bg-sidebar-accent hover:text-sidebar-accent-foreground hover:shadow-[0_0_0_1px_hsl(var(--sidebar-accent))]",
      },
      size: {
        default: "h-8 text-sm",
        sm: "h-7 text-xs",
        lg: "h-12 text-sm group-data-[collapsible=icon]:p-0!",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
)

function SidebarMenuButton({
  asChild = false,
  isActive = false,
  variant = "default",
  size = "default",
  tooltip,
  className,
  ...props
}: React.ComponentProps<"button"> & {
  asChild?: boolean
  isActive?: boolean
  tooltip?: string | React.ComponentProps<typeof TooltipContent>
} & VariantProps<typeof sidebarMenuButtonVariants>) {
  const Comp = asChild ? Slot : "button"
  const { isMobile, state } = useSidebar()

  const button = (
    <Comp
      data-slot="sidebar-menu-button"
      data-sidebar="menu-button"
      data-size={size}
      data-active={isActive}
      className={cn(sidebarMenuButtonVariants({ variant, size }), className)}
      {...props}
    />
  )

  if (!tooltip) {
    return button
  }

  if (typeof tooltip === "string") {
    tooltip = {
      children: tooltip,
    }
  }

  return (
    <Tooltip>
      <TooltipTrigger asChild>{button}</TooltipTrigger>
      <TooltipContent
        side="right"
        align="center"
        hidden={state !== "collapsed" || isMobile}
        {...tooltip}
      />
    </Tooltip>
  )
}

function SidebarMenuAction({
  className,
  asChild = false,
  showOnHover = false,
  ...props
}: React.ComponentProps<"button"> & {
  asChild?: boolean
  showOnHover?: boolean
}) {
  const Comp = asChild ? Slot : "button"

  return (
    <Comp
      data-slot="sidebar-menu-action"
      data-sidebar="menu-action"
      className={cn(
        "text-sidebar-foreground ring-sidebar-ring hover:bg-sidebar-accent hover:text-sidebar-accent-foreground peer-hover/menu-button:text-sidebar-accent-foreground absolute top-1.5 right-1 flex aspect-square w-5 items-center justify-center rounded-md p-0 outline-hidden transition-transform focus-visible:ring-2 [&>svg]:size-4 [&>svg]:shrink-0",
        // Increases the hit area of the button on mobile.
        "after:absolute after:-inset-2 md:after:hidden",
        "peer-data-[size=sm]/menu-button:top-1",
        "peer-data-[size=default]/menu-button:top-1.5",
        "peer-data-[size=lg]/menu-button:top-2.5",
        "group-data-[collapsible=icon]:hidden",
        showOnHover &&
          "peer-data-[active=true]/menu-button:text-sidebar-accent-foreground group-focus-within/menu-item:opacity-100 group-hover/menu-item:opacity-100 data-[state=open]:opacity-100 md:opacity-0",
        className
      )}
      {...props}
    />
  )
}

function SidebarMenuBadge({
  className,
  ...props
}: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="sidebar-menu-badge"
      data-sidebar="menu-badge"
      className={cn(
        "text-sidebar-foreground pointer-events-none absolute right-1 flex h-5 min-w-5 items-center justify-center rounded-md px-1 text-xs font-medium tabular-nums select-none",
        "peer-hover/menu-button:text-sidebar-accent-foreground peer-data-[active=true]/menu-button:text-sidebar-accent-foreground",
        "peer-data-[size=sm]/menu-button:top-1",
        "peer-data-[size=default]/menu-button:top-1.5",
        "peer-data-[size=lg]/menu-button:top-2.5",
        "group-data-[collapsible=icon]:hidden",
        className
      )}
      {...props}
    />
  )
}

function SidebarMenuSkeleton({
  className,
  showIcon = false,
  ...props
}: React.ComponentProps<"div"> & {
  showIcon?: boolean
}) {
  // Random width between 50 to 90%.
  const width = React.useMemo(() => {
    return `${Math.floor(Math.random() * 40) + 50}%`
  }, [])

  return (
    <div
      data-slot="sidebar-menu-skeleton"
      data-sidebar="menu-skeleton"
      className={cn("flex h-8 items-center gap-2 rounded-md px-2", className)}
      {...props}
    >
      {showIcon && (
        <Skeleton
          className="size-4 rounded-md"
          data-sidebar="menu-skeleton-icon"
        />
      )}
      <Skeleton
        className="h-4 max-w-(--skeleton-width) flex-1"
        data-sidebar="menu-skeleton-text"
        style={
          {
            "--skeleton-width": width,
          } as React.CSSProperties
        }
      />
    </div>
  )
}

function SidebarMenuSub({ className, ...props }: React.ComponentProps<"ul">) {
  return (
    <ul
      data-slot="sidebar-menu-sub"
      data-sidebar="menu-sub"
      className={cn(
        "border-sidebar-border mx-3.5 flex min-w-0 translate-x-px flex-col gap-1 border-l px-2.5 py-0.5",
        "group-data-[collapsible=icon]:hidden",
        className
      )}
      {...props}
    />
  )
}

function SidebarMenuSubItem({
  className,
  ...props
}: React.ComponentProps<"li">) {
  return (
    <li
      data-slot="sidebar-menu-sub-item"
      data-sidebar="menu-sub-item"
      className={cn("group/menu-sub-item relative", className)}
      {...props}
    />
  )
}

function SidebarMenuSubButton({
  asChild = false,
  size = "md",
  isActive = false,
  className,
  ...props
}: React.ComponentProps<"a"> & {
  asChild?: boolean
  size?: "sm" | "md"
  isActive?: boolean
}) {
  const Comp = asChild ? Slot : "a"

  return (
    <Comp
      data-slot="sidebar-menu-sub-button"
      data-sidebar="menu-sub-button"
      data-size={size}
      data-active={isActive}
      className={cn(
        "text-sidebar-foreground ring-sidebar-ring hover:bg-sidebar-accent hover:text-sidebar-accent-foreground active:bg-sidebar-accent active:text-sidebar-accent-foreground [&>svg]:text-sidebar-accent-foreground flex h-7 min-w-0 -translate-x-px items-center gap-2 overflow-hidden rounded-md px-2 outline-hidden focus-visible:ring-2 disabled:pointer-events-none disabled:opacity-50 aria-disabled:pointer-events-none aria-disabled:opacity-50 [&>span:last-child]:truncate [&>svg]:size-4 [&>svg]:shrink-0",
        "data-[active=true]:bg-sidebar-accent data-[active=true]:text-sidebar-accent-foreground",
        size === "sm" && "text-xs",
        size === "md" && "text-sm",
        "group-data-[collapsible=icon]:hidden",
        className
      )}
      {...props}
    />
  )
}

export {
  Sidebar,
  SidebarContent,
  SidebarFooter,
  SidebarGroup,
  SidebarGroupAction,
  SidebarGroupContent,
  SidebarGroupLabel,
  SidebarHeader,
  SidebarInput,
  SidebarInset,
  SidebarMenu,
  SidebarMenuAction,
  SidebarMenuBadge,
  SidebarMenuButton,
  SidebarMenuItem,
  SidebarMenuSkeleton,
  SidebarMenuSub,
  SidebarMenuSubButton,
  SidebarMenuSubItem,
  SidebarProvider,
  SidebarRail,
  SidebarSeparator,
  SidebarTrigger,
  useSidebar,
}



================================================================================
FILE: app/src/components/ui/skeleton.tsx
================================================================================

import { cn } from "@/lib/utils"

function Skeleton({ className, ...props }: React.ComponentProps<"div">) {
  return (
    <div
      data-slot="skeleton"
      className={cn("bg-accent animate-pulse rounded-md", className)}
      {...props}
    />
  )
}

export { Skeleton }



================================================================================
FILE: app/src/components/ui/slider.tsx
================================================================================

"use client"

import * as React from "react"
import * as SliderPrimitive from "@radix-ui/react-slider"

import { cn } from "@/lib/utils"

function Slider({
  className,
  defaultValue,
  value,
  min = 0,
  max = 100,
  ...props
}: React.ComponentProps<typeof SliderPrimitive.Root>) {
  const _values = React.useMemo(
    () =>
      Array.isArray(value)
        ? value
        : Array.isArray(defaultValue)
          ? defaultValue
          : [min, max],
    [value, defaultValue, min, max]
  )

  return (
    <SliderPrimitive.Root
      data-slot="slider"
      defaultValue={defaultValue}
      value={value}
      min={min}
      max={max}
      className={cn(
        "relative flex w-full touch-none items-center select-none data-[disabled]:opacity-50 data-[orientation=vertical]:h-full data-[orientation=vertical]:min-h-44 data-[orientation=vertical]:w-auto data-[orientation=vertical]:flex-col",
        className
      )}
      {...props}
    >
      <SliderPrimitive.Track
        data-slot="slider-track"
        className={cn(
          "bg-muted relative grow overflow-hidden rounded-full data-[orientation=horizontal]:h-1.5 data-[orientation=horizontal]:w-full data-[orientation=vertical]:h-full data-[orientation=vertical]:w-1.5"
        )}
      >
        <SliderPrimitive.Range
          data-slot="slider-range"
          className={cn(
            "bg-primary absolute data-[orientation=horizontal]:h-full data-[orientation=vertical]:w-full"
          )}
        />
      </SliderPrimitive.Track>
      {Array.from({ length: _values.length }, (_, index) => (
        <SliderPrimitive.Thumb
          data-slot="slider-thumb"
          key={index}
          className="border-primary ring-ring/50 block size-4 shrink-0 rounded-full border bg-white shadow-sm transition-[color,box-shadow] hover:ring-4 focus-visible:ring-4 focus-visible:outline-hidden disabled:pointer-events-none disabled:opacity-50"
        />
      ))}
    </SliderPrimitive.Root>
  )
}

export { Slider }



================================================================================
FILE: app/src/components/ui/sonner.tsx
================================================================================

import {
  CircleCheckIcon,
  InfoIcon,
  Loader2Icon,
  OctagonXIcon,
  TriangleAlertIcon,
} from "lucide-react"
import { useTheme } from "next-themes"
import { Toaster as Sonner, type ToasterProps } from "sonner"

const Toaster = ({ ...props }: ToasterProps) => {
  const { theme = "system" } = useTheme()

  return (
    <Sonner
      theme={theme as ToasterProps["theme"]}
      className="toaster group"
      icons={{
        success: <CircleCheckIcon className="size-4" />,
        info: <InfoIcon className="size-4" />,
        warning: <TriangleAlertIcon className="size-4" />,
        error: <OctagonXIcon className="size-4" />,
        loading: <Loader2Icon className="size-4 animate-spin" />,
      }}
      style={
        {
          "--normal-bg": "var(--popover)",
          "--normal-text": "var(--popover-foreground)",
          "--normal-border": "var(--border)",
          "--border-radius": "var(--radius)",
        } as React.CSSProperties
      }
      {...props}
    />
  )
}

export { Toaster }



================================================================================
FILE: app/src/components/ui/spinner.tsx
================================================================================

import { Loader2Icon } from "lucide-react"

import { cn } from "@/lib/utils"

function Spinner({ className, ...props }: React.ComponentProps<"svg">) {
  return (
    <Loader2Icon
      role="status"
      aria-label="Loading"
      className={cn("size-4 animate-spin", className)}
      {...props}
    />
  )
}

export { Spinner }



================================================================================
FILE: app/src/components/ui/switch.tsx
================================================================================

"use client"

import * as React from "react"
import * as SwitchPrimitive from "@radix-ui/react-switch"

import { cn } from "@/lib/utils"

function Switch({
  className,
  ...props
}: React.ComponentProps<typeof SwitchPrimitive.Root>) {
  return (
    <SwitchPrimitive.Root
      data-slot="switch"
      className={cn(
        "peer data-[state=checked]:bg-primary data-[state=unchecked]:bg-input focus-visible:border-ring focus-visible:ring-ring/50 dark:data-[state=unchecked]:bg-input/80 inline-flex h-[1.15rem] w-8 shrink-0 items-center rounded-full border border-transparent shadow-xs transition-all outline-none focus-visible:ring-[3px] disabled:cursor-not-allowed disabled:opacity-50",
        className
      )}
      {...props}
    >
      <SwitchPrimitive.Thumb
        data-slot="switch-thumb"
        className={cn(
          "bg-background dark:data-[state=unchecked]:bg-foreground dark:data-[state=checked]:bg-primary-foreground pointer-events-none block size-4 rounded-full ring-0 transition-transform data-[state=checked]:translate-x-[calc(100%-2px)] data-[state=unchecked]:translate-x-0"
        )}
      />
    </SwitchPrimitive.Root>
  )
}

export { Switch }



================================================================================
FILE: app/src/components/ui/table.tsx
================================================================================

import * as React from "react"

import { cn } from "@/lib/utils"

function Table({ className, ...props }: React.ComponentProps<"table">) {
  return (
    <div
      data-slot="table-container"
      className="relative w-full overflow-x-auto"
    >
      <table
        data-slot="table"
        className={cn("w-full caption-bottom text-sm", className)}
        {...props}
      />
    </div>
  )
}

function TableHeader({ className, ...props }: React.ComponentProps<"thead">) {
  return (
    <thead
      data-slot="table-header"
      className={cn("[&_tr]:border-b", className)}
      {...props}
    />
  )
}

function TableBody({ className, ...props }: React.ComponentProps<"tbody">) {
  return (
    <tbody
      data-slot="table-body"
      className={cn("[&_tr:last-child]:border-0", className)}
      {...props}
    />
  )
}

function TableFooter({ className, ...props }: React.ComponentProps<"tfoot">) {
  return (
    <tfoot
      data-slot="table-footer"
      className={cn(
        "bg-muted/50 border-t font-medium [&>tr]:last:border-b-0",
        className
      )}
      {...props}
    />
  )
}

function TableRow({ className, ...props }: React.ComponentProps<"tr">) {
  return (
    <tr
      data-slot="table-row"
      className={cn(
        "hover:bg-muted/50 data-[state=selected]:bg-muted border-b transition-colors",
        className
      )}
      {...props}
    />
  )
}

function TableHead({ className, ...props }: React.ComponentProps<"th">) {
  return (
    <th
      data-slot="table-head"
      className={cn(
        "text-foreground h-10 px-2 text-left align-middle font-medium whitespace-nowrap [&:has([role=checkbox])]:pr-0 [&>[role=checkbox]]:translate-y-[2px]",
        className
      )}
      {...props}
    />
  )
}

function TableCell({ className, ...props }: React.ComponentProps<"td">) {
  return (
    <td
      data-slot="table-cell"
      className={cn(
        "p-2 align-middle whitespace-nowrap [&:has([role=checkbox])]:pr-0 [&>[role=checkbox]]:translate-y-[2px]",
        className
      )}
      {...props}
    />
  )
}

function TableCaption({
  className,
  ...props
}: React.ComponentProps<"caption">) {
  return (
    <caption
      data-slot="table-caption"
      className={cn("text-muted-foreground mt-4 text-sm", className)}
      {...props}
    />
  )
}

export {
  Table,
  TableHeader,
  TableBody,
  TableFooter,
  TableHead,
  TableRow,
  TableCell,
  TableCaption,
}



================================================================================
FILE: app/src/components/ui/tabs.tsx
================================================================================

"use client"

import * as React from "react"
import * as TabsPrimitive from "@radix-ui/react-tabs"

import { cn } from "@/lib/utils"

function Tabs({
  className,
  ...props
}: React.ComponentProps<typeof TabsPrimitive.Root>) {
  return (
    <TabsPrimitive.Root
      data-slot="tabs"
      className={cn("flex flex-col gap-2", className)}
      {...props}
    />
  )
}

function TabsList({
  className,
  ...props
}: React.ComponentProps<typeof TabsPrimitive.List>) {
  return (
    <TabsPrimitive.List
      data-slot="tabs-list"
      className={cn(
        "bg-muted text-muted-foreground inline-flex h-9 w-fit items-center justify-center rounded-lg p-[3px]",
        className
      )}
      {...props}
    />
  )
}

function TabsTrigger({
  className,
  ...props
}: React.ComponentProps<typeof TabsPrimitive.Trigger>) {
  return (
    <TabsPrimitive.Trigger
      data-slot="tabs-trigger"
      className={cn(
        "data-[state=active]:bg-background dark:data-[state=active]:text-foreground focus-visible:border-ring focus-visible:ring-ring/50 focus-visible:outline-ring dark:data-[state=active]:border-input dark:data-[state=active]:bg-input/30 text-foreground dark:text-muted-foreground inline-flex h-[calc(100%-1px)] flex-1 items-center justify-center gap-1.5 rounded-md border border-transparent px-2 py-1 text-sm font-medium whitespace-nowrap transition-[color,box-shadow] focus-visible:ring-[3px] focus-visible:outline-1 disabled:pointer-events-none disabled:opacity-50 data-[state=active]:shadow-sm [&_svg]:pointer-events-none [&_svg]:shrink-0 [&_svg:not([class*='size-'])]:size-4",
        className
      )}
      {...props}
    />
  )
}

function TabsContent({
  className,
  ...props
}: React.ComponentProps<typeof TabsPrimitive.Content>) {
  return (
    <TabsPrimitive.Content
      data-slot="tabs-content"
      className={cn("flex-1 outline-none", className)}
      {...props}
    />
  )
}

export { Tabs, TabsList, TabsTrigger, TabsContent }



================================================================================
FILE: app/src/components/ui/textarea.tsx
================================================================================

import * as React from "react"

import { cn } from "@/lib/utils"

function Textarea({ className, ...props }: React.ComponentProps<"textarea">) {
  return (
    <textarea
      data-slot="textarea"
      className={cn(
        "border-input placeholder:text-muted-foreground focus-visible:border-ring focus-visible:ring-ring/50 aria-invalid:ring-destructive/20 dark:aria-invalid:ring-destructive/40 aria-invalid:border-destructive dark:bg-input/30 flex field-sizing-content min-h-16 w-full rounded-md border bg-transparent px-3 py-2 text-base shadow-xs transition-[color,box-shadow] outline-none focus-visible:ring-[3px] disabled:cursor-not-allowed disabled:opacity-50 md:text-sm",
        className
      )}
      {...props}
    />
  )
}

export { Textarea }



================================================================================
FILE: app/src/components/ui/toggle-group.tsx
================================================================================

import * as React from "react"
import * as ToggleGroupPrimitive from "@radix-ui/react-toggle-group"
import { type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"
import { toggleVariants } from "@/components/ui/toggle"

const ToggleGroupContext = React.createContext<
  VariantProps<typeof toggleVariants> & {
    spacing?: number
  }
>({
  size: "default",
  variant: "default",
  spacing: 0,
})

function ToggleGroup({
  className,
  variant,
  size,
  spacing = 0,
  children,
  ...props
}: React.ComponentProps<typeof ToggleGroupPrimitive.Root> &
  VariantProps<typeof toggleVariants> & {
    spacing?: number
  }) {
  return (
    <ToggleGroupPrimitive.Root
      data-slot="toggle-group"
      data-variant={variant}
      data-size={size}
      data-spacing={spacing}
      style={{ "--gap": spacing } as React.CSSProperties}
      className={cn(
        "group/toggle-group flex w-fit items-center gap-[--spacing(var(--gap))] rounded-md data-[spacing=default]:data-[variant=outline]:shadow-xs",
        className
      )}
      {...props}
    >
      <ToggleGroupContext.Provider value={{ variant, size, spacing }}>
        {children}
      </ToggleGroupContext.Provider>
    </ToggleGroupPrimitive.Root>
  )
}

function ToggleGroupItem({
  className,
  children,
  variant,
  size,
  ...props
}: React.ComponentProps<typeof ToggleGroupPrimitive.Item> &
  VariantProps<typeof toggleVariants>) {
  const context = React.useContext(ToggleGroupContext)

  return (
    <ToggleGroupPrimitive.Item
      data-slot="toggle-group-item"
      data-variant={context.variant || variant}
      data-size={context.size || size}
      data-spacing={context.spacing}
      className={cn(
        toggleVariants({
          variant: context.variant || variant,
          size: context.size || size,
        }),
        "w-auto min-w-0 shrink-0 px-3 focus:z-10 focus-visible:z-10",
        "data-[spacing=0]:rounded-none data-[spacing=0]:shadow-none data-[spacing=0]:first:rounded-l-md data-[spacing=0]:last:rounded-r-md data-[spacing=0]:data-[variant=outline]:border-l-0 data-[spacing=0]:data-[variant=outline]:first:border-l",
        className
      )}
      {...props}
    >
      {children}
    </ToggleGroupPrimitive.Item>
  )
}

export { ToggleGroup, ToggleGroupItem }



================================================================================
FILE: app/src/components/ui/toggle.tsx
================================================================================

import * as React from "react"
import * as TogglePrimitive from "@radix-ui/react-toggle"
import { cva, type VariantProps } from "class-variance-authority"

import { cn } from "@/lib/utils"

const toggleVariants = cva(
  "inline-flex items-center justify-center gap-2 rounded-md text-sm font-medium hover:bg-muted hover:text-muted-foreground disabled:pointer-events-none disabled:opacity-50 data-[state=on]:bg-accent data-[state=on]:text-accent-foreground [&_svg]:pointer-events-none [&_svg:not([class*='size-'])]:size-4 [&_svg]:shrink-0 focus-visible:border-ring focus-visible:ring-ring/50 focus-visible:ring-[3px] outline-none transition-[color,box-shadow] aria-invalid:ring-destructive/20 dark:aria-invalid:ring-destructive/40 aria-invalid:border-destructive whitespace-nowrap",
  {
    variants: {
      variant: {
        default: "bg-transparent",
        outline:
          "border border-input bg-transparent shadow-xs hover:bg-accent hover:text-accent-foreground",
      },
      size: {
        default: "h-9 px-2 min-w-9",
        sm: "h-8 px-1.5 min-w-8",
        lg: "h-10 px-2.5 min-w-10",
      },
    },
    defaultVariants: {
      variant: "default",
      size: "default",
    },
  }
)

function Toggle({
  className,
  variant,
  size,
  ...props
}: React.ComponentProps<typeof TogglePrimitive.Root> &
  VariantProps<typeof toggleVariants>) {
  return (
    <TogglePrimitive.Root
      data-slot="toggle"
      className={cn(toggleVariants({ variant, size, className }))}
      {...props}
    />
  )
}

export { Toggle, toggleVariants }



================================================================================
FILE: app/src/components/ui/tooltip.tsx
================================================================================

"use client"

import * as React from "react"
import * as TooltipPrimitive from "@radix-ui/react-tooltip"

import { cn } from "@/lib/utils"

function TooltipProvider({
  delayDuration = 0,
  ...props
}: React.ComponentProps<typeof TooltipPrimitive.Provider>) {
  return (
    <TooltipPrimitive.Provider
      data-slot="tooltip-provider"
      delayDuration={delayDuration}
      {...props}
    />
  )
}

function Tooltip({
  ...props
}: React.ComponentProps<typeof TooltipPrimitive.Root>) {
  return (
    <TooltipProvider>
      <TooltipPrimitive.Root data-slot="tooltip" {...props} />
    </TooltipProvider>
  )
}

function TooltipTrigger({
  ...props
}: React.ComponentProps<typeof TooltipPrimitive.Trigger>) {
  return <TooltipPrimitive.Trigger data-slot="tooltip-trigger" {...props} />
}

function TooltipContent({
  className,
  sideOffset = 0,
  children,
  ...props
}: React.ComponentProps<typeof TooltipPrimitive.Content>) {
  return (
    <TooltipPrimitive.Portal>
      <TooltipPrimitive.Content
        data-slot="tooltip-content"
        sideOffset={sideOffset}
        className={cn(
          "bg-foreground text-background animate-in fade-in-0 zoom-in-95 data-[state=closed]:animate-out data-[state=closed]:fade-out-0 data-[state=closed]:zoom-out-95 data-[side=bottom]:slide-in-from-top-2 data-[side=left]:slide-in-from-right-2 data-[side=right]:slide-in-from-left-2 data-[side=top]:slide-in-from-bottom-2 z-50 w-fit origin-(--radix-tooltip-content-transform-origin) rounded-md px-3 py-1.5 text-xs text-balance",
          className
        )}
        {...props}
      >
        {children}
        <TooltipPrimitive.Arrow className="bg-foreground fill-foreground z-50 size-2.5 translate-y-[calc(-50%_-_2px)] rotate-45 rounded-[2px]" />
      </TooltipPrimitive.Content>
    </TooltipPrimitive.Portal>
  )
}

export { Tooltip, TooltipTrigger, TooltipContent, TooltipProvider }



================================================================================
FILE: app/public/images/flightline-banner.jpg
================================================================================

 JFIF       C 		

 $.' ",#(7),01444'9=82<.342 C			

2!!22222222222222222222222222222222222222222222222222  @"            	
    } !1AQa"q2#BR$3br	
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz        	
   w !1AQaq"2B	#3Rbr
$4%&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz   ? zZJZ ( ( _Z 3IE^QGq@QPQG@/% Rv@Q@Ţ3@;REPE{EPQEPQKE %Q@84@-% t)(R3GJ^<٦?bo\_zu[m z^0Vo0U`q1l<A}DwЖ {<t	rG&8vݾYI?t--#7Kgdq#kk{CCRxyY౔Iϣ[G'.Qi||kL1^@na$⪝(*N {&"pmHқX`hVV̍% >$5xWi#6'\p5[]O⪞ZF[JRĥS$}%-%MwCM=iqmcF]	_\vSғWV);;mؽC-1U+I:4`FA=Ok85k_2n0s>~J, G,2p[wV{4I.WEE"[)Ok$̂&H$:־deGlndbA8W7,F,ǹ95)ɦaiofYR55a9(,< k]:N3]|-|;R^,d(ﻭIg]*׷ZI'=:mKClC)DW*)KT_q1tQtV9(jf]%C,3]pORUxuuohR=
j5yXLpá  qf]Bۺ I*?{y;Q<ظ1Ƽɺu$S٤Sտ5*:d@Ҹc0$dqtxnFU຀$)GD3\m88995P2.23+ӭ(0(1@KtpyjgT9C[VvgvN梠tXMWՎ<5:w*H0pEEޜ4rrIike{jsb[xۈ'n
OMtZ:Shs@uĳ9>\ _knQGE		Fڴuiz6w豬`(+
Jud܋0
o<G٘G sڡѢ3I nxqÒ2i9_1/6pB|i--v$OZ=VW<͵Nнs+W=6l^[k"|ΰp8S	WsjX݀ɐҠSW\~VcT'dG.
RͷՒ]Tޛ#[a]@d}Err5Aɶڲ.%A$P){q<RNFPr)Vx1G/sDޕFkXx%z4QK}v#~yڠZ]6rMz9$m*J썌3ȗg^W[`eS9V9$ .g{8WVOGl}LF:{t:Tq̞M´8m35٣iiTs\b͹:nsorHݠun4BIe UYsgy{*W^YZ~T@6oTcZ@I%sڲZ#rVc6kJ/to$FM.8#`jy F8*T>_i-6u4&9QޜZ:
NԆ(8ɦ0PIKA@GzJ;!h@z@~PEt;Q4 Q(AIKހ? QGz?
 )(@	GzZOÊ ;QG~ ;E QE'z) Q@'JZ?* JZ(()} ( ((aGGj?
 ( ?((h;Gj( R⒖
:Gs@Q@g 20i({Sihqϥ.M6 visM4u/gLwz( a4r{Sf҂E旧> R2)1@
LZ]ZN}(FM	9HqԘ>c N)xI\яcHn	m>(@	(+Jb:RMZp!\6fC<lzV],X;L/#TqcsUda"0uB\Udw{f_ jkw}ǘ"sqi5+pjV? n:W1[}6Vy{GT*EvRJJ[-}'wΊkt޿ְZ5vMVhzεH5	gW-#&麥ƕtٌ$G5O8Ɵ
cQ1>)E8٭
#9)]=K#QIF-PMQY#mxY,p0XY"jxY$uZ$ggaG+I'{.{k:APylz9eڤ+ÝBӿ1j3iڌSD.@u_J_}Vx")bvVo-K Y S'x2G)ojj?Mvz
>~eQ]'RQ!<(PN1((4tkjozV+d/OO3ɧ떷2F>g:P##s\oYo__Wmo}~?R2)ksQP^7:\߳Դ4I&2#= WiPqpnN`V툏HWRS-.:Zw[8۴/ z
>\!&/'ҴQOK V19-\v2.4{QPGҍF+tͶͫ	[Rnm'!̰1gұsdٚ=Y.
wob+lmZ :iJ)+cii ;5&M 
$QF}hbc4>P;GB8$I'&ڌ :SiI!)`}i0i(
7ޗ4i09QO4	ފ
(E'Ci9WILEFis@\u(=)hAђ
 IK'( Gz`\QQIҀ
(Ɗ;Q@Q@	Ji?(Q Z(Q@	 
%-% RP hƀ
))h QE zQE QE
(4vQޖ_ʀ袀
(֊;RQހPxHXE
QE( ( )i(Iފ( - *`AHQKIK@A<Q994bNӶ[:@J8VO0ᇥ[:3ZSWoι^/49S.ߥ[eZxvX֪I%-rP#I!*98q[]@Fb *Ѹ][dڬpϧ\qkB<qM$WBt-5ƪo|e+T>l*º!UOc	Sy&Cs?aȣMBW|>E߇Ղ$' U&kx偎ӿ+nu%)Aߕ,^'K8^3zЌ -+z[B(\rqՄfh"QN  (RZݱ?w~?NP)]Kgr.UһS<&ƏJFi-ji"au`K R+,Pj'5)p26u]JP-I,z#YىsMOz2)B*YTwb4>ffGZ\9cӎ*_UQ7mDjF[=B
|xI$y"[w4}~EYD*Am$KNj.Y+U9sEٚzƱ6p
Dț@N])9ȧ(.X*J
(ȣ5D֛hWkH97=qҲZ-ݶ, /ns63%-V!EvUk=#Tr)C`E5Pu
Ox-Xe}sriLSj5ZU]/z(g'%GT>fڪPRVdB'(%+o7VHeyU9*N3I0h$U%.Z^M}?3s@(\RPJș7'vtJ8
9Աw<ړ**
 uxFYFJvQB `4w, Hv\u+MռF]ԯc.L3/]V4}--=Spxz
U#N^w#	Z`Ok FaoX<U3J4!L9cuXNWဩ̔K8תfKvڥ+8Y
sr68K(H=iJ>}s*f+i50B1*
 2<q/RkIME\䣷PJNPt׎1`hg asuݒq\4feڂ{Ԕ簔$1
!=h4'Q@1+1M&(EPIKE 1Ҋ 9.sI\(4? -4wQ!ʊ=(S EΊ NRPsEtAIKE Q@	Eu((AEPG֎PҒQE
;ڊ )})h;RE ~TP0?QE)h  ( 8E
(QE KE E!4PHPzQ ))h;tSGz J)i( (i(y jZjqNhځa O<a4(G2; pJ8JM_Bt%р\|#ߥD|Iv&YDqmbFK}*kw7NPFAq`ȹ$9p\gR$rQ|av'JrI'&ެ6J4Khu øT)jҢnN"a[.8㰤-倬SsJHg
;oMyXk  ݊]	nK*sSbe8zumvkZ2'58j[Q;ũ#H%8)L3st"Z}bN1 Gayg1YONt8ԚuNONy_麄P,rEX~U\<U}A!4dA6BR1ߙAW/#rM7RZFHii)ZP3F)6ъv+ZBkUu#yS*F>)v[iYԘйU|abT:gOBzъ^ULRU$P0*QOP:tW#E)1N#F)1XJJ^ }1@яj0qҖm.)hzQqF){ъaa1F.)v	oF(C#TU{"O^.j6SW6xz36T) l4N"4 8;ӏj n8ZȭgkZYǒqsʴB;K+fS0ñ?a^E60IK@8$RA =dī\)X${ʌ6Oj|5d`/TCfm=;ӣ-voVիB^.ǣæEqI7Gmؓ5s3!8¼?_^Ou9&GbN{z
ΔHqE8UOE6ԣT|9>f>o|\q+<]IjO!ðӴgV]=PwWj+^LƼtLгAgj}s#/$H<ެf.fY--,2SER j8 NgErOM ZݝM'{̠tzIb|.&qe]+=,	$j:C;8 bW?^lv#SzROZ< ɩ;cڑF/z J( v'S	4	IJsE2D J)hBQKE𥢊 ;E @NSMh;%*1AR(J1-'z`RPGz;@	ږ
 %h4J((h ?
)hE
(=( RP!(4PIK@QށQ@Qր
(
ZJ^ Qhz(
(
?
(4vQ@'J^z@h4CIKAtQ >QE %-PEPEv;PO4ڗ PR0iE!4,342e9g=XN:RҽRv:ɹ>5kdq$P.q\f2]'ѹ($[g_EV9^'fκ)JIw̑JU''5%G>xJ7l}Fpz#ޭU/43t%}%XsԷOo(YhP@=tn{IRǀϨ?QWIcB{{^]_͞9
]E0_%1z]18fIs %dgZ3Rt4MQ
^Ȧj5htU8`pֺm"uld'߭sj{!K^HQޱ:zW;a`'q䓏z+qt[Ɇ)Xz#2iE".v9qֲOٻ޵_mEZu-=ojfqWQՃ< M# A`Q
u=M>^}Qsp<trXM
wRD|j<1k,!
Ҽ C==zZ֯ԯu71p:1Zwg%%nPFֻմ<\-?:d CiQ:0ǷjFi$I[
$KΓjg{+AtdXA	2{VUjڅkhZLNymb9Q3WN[;wґ1b=Ο(
P46U8X"&k`J"*3	\郚4kR_*#8'y=
)V:K8fD[teȈސG'u--қ-},`~"fVd:RX57C2rF࣯gJFqIwkZ)	Wiq)@~tB\R@bY\)#ڵ$|=wYN|6IK[Uѯ-͐eTrOJLY"16xJ؞FK6r:`}*n?J㌞j˙zΙЧwTaJXdRUjM4z2O8=԰ZڴN*\0Xjoev;0NwfEooay'MO8,qM:$;&.tg(;u0Y݀'oڟo+\G<gFw)442w#z
ƈu0\Zs\ʝ7)jqn%7/@;0O0:ĚbttwiZ[hgrf?05HqOL)γZ-:b[zPHRrF{
/j:I)4p
C򢗓Mc;9KޏJ	QE QEwj 1E~4(
(
((P1åΏJ)NԼъ)c% R: ( ( J
RP E 
 %ʎh;QKP h %	ChZ3IE ;4dfKhIIK/z)3K@Q߭wQ@R }h Q 袊c
!4mPH{PRt WmJm- :^h-%/Z ( QEzR@S锪{whu-'-"qi9LZȥY#)crEXo]
pF6LVIk'F
ݣeh
79?z(%><95Nd'ZI934fjعM yB4)zPHiq
'=1@1N^
:Am{[/%*H\Pj:T#c+	NN,
Ȣ͎m6]G6HF	nf\885i(r`3XNR/s|,˱>t&7 1WUj*fN35X}PPA;Fm\'i9Κ3NYYiz=?e֬E߮e
TW{k{dO)/$u_D5'{VtʦMjaKWtA"7۽d !Cpk7)x<mr>Q_?5Jݿ/ҙk-uاP4<x5wmvD$<
Ok-6XFi`!NHY'Pj389
c8SIu'NUn^fi1RHeeb)G#Bt67#.O@HP/5r[y)$M[o;m<zF.[tmWךAH6;Wy'Hqͨk:Ӆڵg=DĽ2~Li"[hlyvӰut9
}pjuSk3A'NnZD*B4ʖ?*BNE7.9uoq=C
 jV0mعʍÓ8]Qy	Crc)tdua&Q\[m^#WQ1ؠkDG}.{ho\) ZO[BW.БJ9N=!R2+'w4$*n+_+7rXҖGHkSM<747t{с@7(Uq
ƶeav\.r#fldOjtԚ5U2j7.Q\%8@?v4F	b*&mn'2ϲ5u,sNd;"qqɧS8NA(<
^Vb"u `R FI916NR):(T QE)?
Z( PhE J ))Z( RPh(!G󥢀}
  9E R@	E-PQKIހ􂔟zBhqIFy\_j?7&qIHi(ƒj.i2h4t4R 1KE QE QE( ;G 40@\p"iP;4S2]Ɓw5qh"(J9LSIaRF(K1@	E;(ϥsG (Z'F(- &=hKނ9:R-;(R0-/~qJSA#B3<)n 'KԸo } :R+viS{&guZMH.r!j7W%RF+alu1T:]KT*7kҭ<MJs׈V]!f8tcʳx~a&  $rdmnJ1$瞕F=N0DN 5f䮑?	o;$oUqZȥƢ8'G,l	A3HAzz"QvktjL籞	 `Ozٸu;h^ifHw3ֳvEtBjKGC7kԇ>Z-#~
8 0>@i	-Ԟ8^8Tkb3@!IoQ3HI⥸7j]̱  =A*-J|o';{Ux<KJygh'	4qڬF 
Oat_L)%u4ff8U$gߥ5E$VlҜ$i..fz7vmSFfO@ՊX ? -Q:֎_E44#
$SQI{yFn(⮶*kU$pSIRRّ(;݁ғE2FKK( 8 (=)~4zAJ{F;bGz!<%nZMs^b#\V f'&ky׆ASSF+zm2CuLa	9ج7tmNv9<E֜w^F&I
`˩H
 |YKRaΓoj@&.cb2{gEnYCMB
~(Ps_G+ΌWFDŧꑃ"B&IMu&(ޅz
i>wQ?01G?wsh֯ùkD
0oPy; w*i{2]*RLVd<
}h)BRZ>
4Jw1~qh))LQRP:?Z^PQh0R@	F)qJ1 LQv)?
 1E.)qJ7\R4 ޴3@QHO ;PO&'֘E7ڊq&);@\]ԄEq2hP 4v- R⒀
(=h4PEPGj(4 QE R ( Q@	ފ\Q@	)} Rъ NR@RQ(b(z vF(4Q@;H3FO `]r(Ƞڝǭ,7Z1N#LP+	E-NR@	ڗ@z)h I;Er
38B鎵fkRLֆѕӺ6i?.o1_UKHϦܸV{0QҴodݷ ,Ƕ0:>}=Tw808J5=*?
F _q%D)r Y4HtmuWRr1}Hʓr$`#+jr\Vψc.h=-Q	/%d݌*ǉ-t JKqӦ+t8=*i!bk$8'I<&/^1ZNO5ڞ#ޱ1I>dqwrdQol!e#22ׯ5jqjT%kNuO^GHo&p# 8cWRHF,О{BP#;P+:Ĳ4IUf9TQZ=+ʘȦzqژF
u
giCK\+=OL{2$W
6ojF#,~Gn{r!\n(0ɷ>[*kPI3דV4dGͬڏ'4isCA";ɤX߈"E n+rQ4mȐFzc(S c LVJGYܞs$Ȩ4̞]9uT2wNjJH6ބW$a $9Ym,KHՔn16}Fz{tԛVzT]-EiV
x+g\CfeMĎveozU4CGo+
8ׇ#diY_Y_; cNy?	t5rǮ&56Ҍr ϼ>__M ecY 梹ӡmurvOΪ+[_ԋb^4gw?(~K
dE<Ct/iЋ+#>e=f fTd1 LRvoI~E+?2-Pÿq2@y=*$K
:F84+ŵsc܏$)8OOܓ*9,tU$`>S8 i٤6w#94[_  oO~?h+` nE9,4YuⲾ.yKY")8 d 
Z 3mMڷ鑋DU@[_"o\Xk;g?ik:U5h._k*Ғb\ڈ0̲~SԌH֣k7}ZAM
O)E;FFhl".m?dm&h&{RIhʊ`*ǀ:gJ{$H+ @#uf;W&6z.Rt
jz{me	Pw@CsrLt<g:i\H)<aab:+1^)~nRkGAMsB*펳se0}:w${z>ijqRVgMY<C
ĐU03u^_5PaKhz gvHVycVdϦG3NzMER>
#8o3O	!!H䳃,-,ass+ ӭycFyQU|Aq"˞ 99JsKo?:i13{syrc7(fq<ⱅ ϣ]4ӶG-r+|nlr;V, 6 3,Jj~#oZk`SqSK1@%&9wHEzqM#iMKA?Z(;J)hhS;pR!~4q(
KIA@891F)g'KҞPh/ҏQJz}(4P}h QG0R) Rу@ږt4{Q O_A@(1E- <S 4Ji$'Z)qI:@`fƀ
1hRC7ҹ)v>"3]&lh'8.ǃBc0Ln7>IZ{SSm>z D/މ]9F=y9N A1]6ѩFl@9N3Z+m.ɺ?Q6bz
+oZ#6p9Y[t?Z7x>鍿Bf=AXjo@YqEXk;и5AVbP:;@ý	ފ^Q ~Rz^(@ǥwz:J)ݨc
6 eE{b(Xh;QHv֎Q0Eh3<t!4h*V
*{.U	 JW,n Ⱥ[d*W銉+{]W[5<2PkM7+Esui jY[oY$-.88rz]XҥDm|4)ݾ`}sީ:I=g28A J暥!:ғ5R5ݷtJ Sdj"RN)r$j	TZ[֥kn29lm7hRL>cl'ݰu{ۭ;RV6P,9'9Qc>[i1ʹUJ}{ysaӹΜJkq9#r+cpRA#NPv_\49d!.tC[[&Z=nO%2N}^Z-7m^N1\5-]O(&i)sUþC	 }k	fIf2A"`UA7(ݣ%k4/~Ѝ{=[E#n?OҶNƧ٤ܣc+%<Cb\(QMm *eMrsm
A\bW (Ww$<BOU|֦j!F/2i:aEih˶d#7E!#宏k7ܑܝO{ek.QQEp 1؟aWLM^P~G˜cn:5[TbcƎ.U!{Pdz,K;H=~TnVP!nY8<{Xb笴lRTZgBE|XxTss][Q>XΓj4V܈Hq=:%t	)V苌R>ǩB?Ƽ2Kxd=&"L5VkС#,`ztUu-LB.qd1#  >Ʋ̟FTZ $)"ϕ4'k^ա_Zi6lqq]Sセ۶uͻHr}kQo;oz3,>J,:c
'nG?ZēRK6d
;ko?m__Oʕ渙Fi1<`MR<*2GBFjRWUQ<[Q~5=Ya졋s^}`\q"C-ɃewKXP C@(:mGoJÿu7N@VT#-bmhX<X :sO ,v#ݩztϸ|
t8v*1'AjKLchx'e2o{3lơXE-+	;CkVr^-E/qNy.fURWPp`hO2yG]CGJWk[yF?>VS.fK" g«U+]N/+jxBg{ѫ2ZZ_խG0'z	\i$q4(]Jڔ7ћ1Oc1
}\fFA 3=6;ȭ)/G}6w|cs} 3ڡnI^FiÕX{h2`9<dGM'ғ+ts7sQBM? qE;cZa?!E1Xa;bbZ"?o?*b#Ǡi:63w60(R<QRcI1ތ~TQaS	IڝJJ% GZb=INE?~Hl>aW?"՘{gp΋Ze y)-AX@Y3s!KRWTZ\¿5:xB ӟP
9:w	=&W*t4[Ě\~Ŝ	JHz#C[XCR~(G8ct-S&~-}k4QůuQW'#D'1&Km4$cu>fA1G;F[c#$u$3'jGǵE%GzZJQGz Z))AV6upu5,`( 
𥟚dSUgQn	eY:܇|8eSʚ5')޺M:_&vs>Տ{Mƣ ǨDw,hhPVvfN)^>ISM6omVQzv#ǽc pR❎iqEqJ;sJ4
P)ا)R8
W)>N E?USqإ&g.I='տu,2/l:`pLúVXwise*ŻDpz๮[Q֍(R"PI\獄On*#߼~^JؔD
*r)4ʕ$mz8EYz2}
Uw/ޱ{&yޙ`0TUC"d?֠As{)Evl [?֫kgul )н/jZlVu]%9 rE?֟2Iv0Rx?[u,sъ<-E| *\˸rK-ZLe5Yᕁ+	ފ9 ;hzb	E/z(~TwZ\~4LS?Z!*M
Q:Ӷ(*h
 \J1@	JsF(Aqޙ1H٣}xfLw5vQl`Vy%|xEe[lEOQ$J Gɧ!@ } V>T#UVȻu&m{1;bH^%ÀBvcpjmYI@W-еJ3QI3xMR>3?|=)9.C3E"t8`{`8Nmu
}3?y$[cldgy"Î~ A]s" ۄݔs\ؘە yi]Iy3&jܤ^7~9Ƕk7ol֚OtF6F+[M&{AITUry!
'&-4U.^Y4xcO2eUz}
d&q4T#ʬD/>cpwP=S$~;k+ ԧeaӗ+`Xqׯ5viHk2zc$5Z}	A9cT-Qe'ƷijW'9b72(US5@lU%ub"]L\|?	 \N3Yq9?u-#BF2951+mҴb'Ԓt`#L`n#}}9*kYvLc+p0>WM);#p#T-\>5Ž)d
F Qf1*2>cRMC4)L}(+s@:.1%#f+H,kzSErq9	!`Eu4s˾+uqďMcNCj9Mz	v&jBORb6ia<KpdTS)BEÑ(;bQrl6qHhJq~TƂ9KR(~4dn8>;S=)p}jH8| uIV"=zb5y iM lEKӤ\ } 3K+$G?HkOAҊmH A J^fI?l?(?݌W"o`o'TW<P+cYɏ*~`1>#:#cM(ۢ׵E/O @o|GiG+≧]wYú尹?ȏ^~Ց
eSKlxI'?6q^Ey&jQ|c?ʪzRb/?}&/<})*}}Ltc Y&[[x Ŀp4.bQNښr{ihXiTx+vJ)6sNZi9ZiZwV
JqXoHV+INb-mJJ."	-Z7QlHx-_P
3c޸-X9=;\5qmy-.E>61
_hïneWv>	XtҁSڰVpуêcyѴ205h]Enc]t.Z(vRfAKIڃցQ@iGZm.}&2*CҸ>.VE<2F%Cָjκ&[gC 5	ïB+ִ>/61+L 㨮II]5`F٦;e_C]8èe 3޸H&Fᇭt-R zJӾ(KѶʱP)ivp)vamNEay<-8/J4;;m<-8/4\v8-<-8-+Y^"RӀh8
.7tOB-.m ڴk8kzK9CG?Qo	 .?>h#kfVz[Ogg?a*+Ko T;C._7#t>oϫcոlP7A5ȿ[Yߏ_z|
R{4CMXJכq	 vR?(мWo?z9Wq=$%<-y>3 ӿ m ~ K+ڮ nx<> u ^CUz(1bHbq\La?tJ|Fқe~
O$ xH3N?D*	f+Fؐ Z?h.yd z#3W#.1Debo7í13J>$d,aR?jWKxey7&?R#ˁqéAI nMJN7:3隩3ֽŨ=DH8Gh˸|#~y1I{NqO= 
7?>wip `FW]Q_W}Xgb\ٗ?7 Q'tV 
m}0G^7-ej
 V֒eS];WG/|E	Nw:5Fڭm6rbc)Ǹ{]=hTFBCS{X(J\zQm>\vO.W*"1<*\RȈ6ړҧF=rMcGRRБ5/
/(r2I']7(q2 *^\@ȱ6A@)\g;=I_&}O/ސ4)1Hz.4CF.4;m=Pԋ*[.0lA1EdT z<|EUCwPȩq@RCplm&ڲ!Z|6W8G.`d88E(QQ}Ҕ!JQ[QT+G01h3RIӽ;=(=;QqXn= 8b֋wM,0!?Bʵ-'sQrKv4Gzog  Y"kJνYKԯg'W8?ք?
4hJ}U/Mu6xך8~xjrK ]&oЇǗqݓwxtC=zfO)~5|Ze+h ܉G< /J8i%`xk&<bDԵ,+) 8-d}	[6|EpSSH?SgB?בԧH!I!S|Vopn5)dakܢU)M:?g>5one#WoK-M7<?|^ώ&Teᨿ!Ȝ JwƴZF ֟jK`F*bI&}>໓رP⦜3iO* ?g7^Қw${
םMUϟ*uIXگ*KS]OP+L+^Z|a!`'_}"	Wkvz&zisּ:G_x 'i5H^]"K,0R_JPkOs-媟b*|1c |=GNoh F6U{ݖy?݈ ZK5 YNe>~븿|"t Wkt PY>#Ǐ +u<
GFcj~b.	sS.ZϪ8
c&n_.b15Zkg# Ղ:֊y;0FV4ElV+L+VS
pXҵd4;m*Zi_j.+ʚnʰV;mX+M)Er*}iV+S)Nbm+ 2M\)<G,ҵ<2oi]7ʌmR[i
"v̎qrSIy:bI8 }d"?+GկørGU*c\g'֫mJ+|1qU^
wkWfT\S1$֛],RGRnsr}C4Ui)@BRR i?Pm#R6r|yPH<T*J̺u%tzp pcZ:%md~Glh@J\JNZPUtqW1ЋG-ؑNTE*N snm[(Fwԝ<EK[P[dd_CW1\A*'QΟ"M
I0#ғ)
.~)psJ)iih0-8-</4๥p=@മ;NOOEb0 Zvi\v#	KN	JvSrB#St;l`bSt!pT))\v"pJ'<%nTq)Yۿ0_	O	KvF$ѥe}UY<%(i.q{ވڷ1 /'-9!
%;f(/ci>-S
VZs
}C-zAK~}yO )9_o.)FLlWf\GJ#.K=7qܘYQ:סsD]Fpy2^G?
	N	Q:JG6ԡ)vVw4"JKBmKe0КxJpZW	-bhcz:uBoW?t3)+`%(Z9\}X4G92k:3 VWwiY.y	O?g
gZ@|)GSԻjy1<:~&8YG3O-[dˤ^ :aWЀRbeb|-$gЏQ9A\z0R@VNOs
U,Wt/c|1^?<1q2{#/hؐ0ER^Ş+jP ׬O~ ċ$k::Y?*}EyP9vW|Oݴo: \V]ǃEk7FjHr3Un'":Pm?U{QjM;)4\|$b`+qaP898?'P^!&<(ݠUwgG7'G@lc[{Ŭ#eX(_^z+%bU.jx\{Vs}RdC`jhz0$}3 ֪T~& ^=qIKҸHF*Bm捹T2jV{>Ϧ^K?<QuV2Ixio=uOsZ 	5@3XKԗcϰ1AV:8NAIKC7G*]x!hxR{W /o 04+7jwE(@dTLz!7o<0!D-N Ǔް=	kԍcET1JA5/  
|Q8H,?5aﬢ JbmC9Q|`.Oq 3Z|'XfYW}Ѵ:Qmx^ҒB;#7K}FǑYGVFP'HQPmE=b	66T;i6)6P;m+S₴rJM9QHV܇OT`մˋSRGQG֎MvxF[}*ͻwq7㫿_h)M)[f]vxWLsqZ#![j!'ݔS}^1Ǜ\y+Г{'@?@HR*>Ti8n,fG?~n4/k>NMOemUₚTRl.]֚cEE!QG0Xcҧҟ0XSL^hzSLmO9J:iJb4
>aXP
iZb1O,S+҇Ү+Hce)(?Κce)iX%E0O\)*r7h+L+N +M+S)SXȦ\V M+RxfT-Zl-<73|OV=]( {jr^\I;<
NߝTR6e z}+\.wd2E[ʿ0^ߝozg`Pdq5mw?(<5aPn$ƵK{P
wk
nᝏ^#u9ׁXj4U>.4V%-.8+6a=sivظMˑzahe=J	?
\о
JZbHeh4Ao'9J_Ier!kԹ֛XZV{3մ-cʚ⾟q?cٽ>'Kt6JESyn:W-$wb]{H ãG,ewʹOaJ~mbeԶ2k3b79Fv5W<~qޗ5MopquñPVM$0jpJa8jx\v<
P9J㰀SҊzJдq`ZpJ'7*a)*@Ԯ#	N	RҸBڞ#{SsKv!i*P𔹇bL0XG8GS;yt0Jv\ñ JpOjGN 6NE)*m픹@%OeA%N%.`!K)i\6R쩶҄C҄S{QqmSJA-Oe 66ҸȶRv҅#	J.(\e8%<
v+҅Ҁim?m.(.{J1qSM~ѥI)?ʴ1lcڎklwi!=fOk:_%_M
v#4IHcB=|`vk ?ֽ0GOUJN) YLyW)LI<ReI:uwUnW\8uO>{˻3HJN#4?<EJ9٤Qc{oC{m;dOHKe`2 I UxSy<VWj6?	tm$Ԯ%x$ִ#O'ߞO+Gkcƫ
g.'sᧅ#6RJ1ZV
<ώ kFW/hR6B?a=RSasm4lqF(QTX9m1F=E&FEEhKb,
L{T(ECjLJm&,MMOm+X)1Eˤ1Lz
COAIڦM!܇m!Z1;*ǖ)6
rQM+VvIP;JSJJTSJ.;|ITSU<Vio,zQv89g4ML ZaZM*iJJԥ	1|bT{T:iS)`X5hҚU5lFSک1XA[)9+JBE)i
Rce)i
_/CY*)
9s4
cڟ0VeŚM)H7쿅t~#Վh"ϕtwc/H4%t=?tхg."*'#YEZu[-[xUwbO1;/Q`O=JW7E
.> 4-c! u_jb|Zie}\4rsXЧٌr3撗xct>S1P"QĻNH# tT iqRmiښA%/aGҏ 5oN!>:!;w3WcT\D-&o/'qbi[Gdjrhf<^[E&&^P wwI{j8aǱ)#672׼B?'2ōԭ#l9?ww1Gq	ʸW6{#G]%:X]6?ªjkΰ
xiY\9R;
#<GJ4R(:xzR1\Dx'<j@)˶ \ð L*yB:p&j@bCOVSy;8%OӂR{RsAi}M-8-J0SQ!iB)v }\REm*N)xR(3g4)Qpm;4fvh担b2"ѹE.J㰙=A҄xfP(ǥ8@DS7Ij^}(N\q:<R4Mq.Oh@3T}@0
PPWSr)vpHM1?/Zw( gߐӓmx?+ں]kE>+Іɝ%R1F96T*j"R׵Lj6`;HK}m>k 6U;:bz1 
ɽqyǥ&*B>j]r:LThEmѲCmOr16i6;i6T)<9GCT_'K|\RT3M(Ԭt2yGԵbs֤aޓh9qIK'>L{Rv
&
 sM94UȎijMM"GMm4Z0rL妜P;4݆$Rr˩S}(Z6
~~qRE*BE4j.2")Taɧq5);	_SM**bM;id$SHau@A>1GFf_Z`CMip\Cϭ!=FfsSr?za$>*c4.AmW[c*QҸo;u| ڴZ
;RIq)ӎy~Vqj3.H;`CO΋h_Rf/,sS,Oj1W ?zE[<䜥̷{cÚ[5 Wa#
4*(ɩ-ⵅ!vW'}XK' l};⻯SMS8:7{lյ.AGZ+ҊQVG9ɇEDEd ;<tJh&(5KND*r*MݬQ݀G p9>:093}3\@ΰvu[L09!zK"?0i!zIʞ5)iNr:ڂ( x%Y54wGi:jVAqjt[b_ҹmSNY=Ez,RunBG*%B|cݡR8N2|PݞGjM:"gm0 VtTfe]B/P;gA-?λ"8?uHʔ⿭οFdvӮ23;[AkHQ{m? un+)&5Om>Fq٪EP,S֠q:NެQ?zl,{]Oz2R-\Gsxm=
8(DcԢOZQzӂZw4z㸩c6֜$zNK@r+!nu9FlR-8j/GKL,li@{8KLv51o8OҕiO
YjQpHr88ՕjKRSCz
ǽJOsSqr0zD^Z\d`! Lt4s)DTtZ_(G0hF$4<BǮ)4\4#\WEpO8n )1EtVǵ8Fƭ=1OjQl}j\>-w{
(Ӱ1V|pJ|󕼿j<jREUSuco>Qs}*p
8!SS'%(CS}A˩Ѳ(<]K(sloOro!>i_JM1xjC~j*+_>ҸɹH5M?$D8*dSsR橛QZDN2YppzVRgD"Kna#WA|#JqMxM8312m	z3ܸȨ;|}G|Z2*G@M4{!!2EHd֏n3C#֓r1sJ?i EIj+Ӽ?l/fY޴oWAޚnS֟Cl\RoiCGڐR˸Zݚ34(Gpr[4*G4ޏZ^%{)J
M;x=i>{Ru?e"?i>hsڧ!)򾔛y4{Q2aL,=jHi^;aʑ!qM.=)czd.iHPzԹ22beyCޓ7ehFe
K
<Z耻i-SPI'֛V|ؾoJL5X()1H|X4ӷkM(ݢr)E*ϖݤi\wEC))s=wE\ 
4ݫ)6Z.>dg_JKZ!AO|qSޚm?Z%49jޛBz֚v|we/v4}?zJie_;QhjY}E42"?AI'J]iEvdeҚTv*)+#aQ?ҤixF->k\aTnmY](^lXۜ?{^W{t.&&Tbz _5YY?W@  P}x'6ӬΣ':ҽz4okNo.39ᗻvAuh8y>Յ
)nT+GkQz)/o=;y#'Z~Lm⢼ػ'$խJMBIl=*vPyKSMEks(E/J`3lGSO3]0=zT\Y>#K"p k;jQ=+U5oB/"}'JK.S5TVG	e}jRC+AUolgsZH]17CT=붒46A#k,n2coխ9FsU˪ئ4sބm;֦ ihehR
:QGz Py٦\O)U TGQ*SRVۼ2Ѹ<BW}x_Y[<!?=*޻.bɷ12sSXj=cGBPw[֗.Rq~?Xֿ:u߻f oz쮟Ot2P9=Wlk~+O6
EOwYC)ʑw}3JӍ>I7}Oolu(܄1ƤF(ƔSfaϽQ !LiO&Q%Y (yP5*e( NU^cA
Թ9c52>Fr) ?S
VƏ!S>Q@=i7jE9P;p$wԁO0r%ojxjU5*K(rÌTti=RjO2P[ovCڤXKRwYi%F+9c֤ 
E({ԋֲzpCW'}ZCvAl}ir.9٢iC/R[QROY4qrr*.2,8 \\N>x"}*Oz_3Յ?hU4M3<5j7ORdZP碚-G]ؾ
)op'ӀRKk}hXY[?nsOryYd\
a{/3GQIOҳMKLNM~FhqXUvM:S2.ߞy{:=j2i}dUyyְ)q)<3FϙS1=F+4K9jERh'[_#?J#u]}df
2ЃiO@A@NZm_bXH$f=UT?*ж<+	z2ոlz
>Z<$F1kKmnAa]y$\)ZB;&(>joMMɤۚ%i+ykJ}*ז)}hՖ 	X֯}?ȩ4Ubrϟ:M[?gҏG^=m@i;%m}!4TC_p{.N-u8ݏJB.^FX4k@ʞ}$Q{Z,c^h<Ԛ*6IO&D5)=ݶ㱧CTf9)9yk,
;:3~Kt%(ȵ@4}Q[7>SLq)>noSS\y)	H*<[,IaG>6̆'бU3/eDhE{9/loZ6T>!蟥! G:e#@Z?ZJTy\O{|tҩf Uusٮ4bn#꠶jK9S
Z`no.f{
aZ҃]!7.z%41?J{yJMz*=h7KM&OZahL*繫$
N(ʦ6?iQDN(*o$zO${Փi"f;KHb3yCPDb#8AM61}y伺h|<ޞ{ t.ZX?'>ҼSwqE!AO<8uW*glu&yP;$>f_kc	GtD Qǣ3I=AtfC]urG|6ϑ~/vhFǠxZuߑ~.ϭoxYVbz#>$I9gKob^?{GzO( wWq)::aL9fzv?y'|S]w<=2ihG>J8ݗJ˕+߲]eaS#]`/gڼzv{*qtHX')n9 fǽ(EME]1{qWD, ⥶=MZ
kT>[zTwsE*CZx4IO8K8YqW{nb Uum-C*G+E5n^"FwPi)ӱNp3E!ʜZ

(d2ZβJ+F-_OYF$_^T+WBүU?<:PW,oDާPO֨=kfh ct>JhnVhxd Wl6n SzW6{__ fp.to ϡui܉Fˈɐ>CTm8?ꟺ Q{K.70 qjV"[? ZU-~^`ޞ0y6[#7rGr 	E	⧅qLM8#~W) B?aliHT<dT2[Sj$T;ԴQsfR-ˏZ;B4o U<BAU$#XMGY e-TfJjeҞ #
D&>C?  t'`iP_J^Y#q)zuCRz
QsҋYӁެ	A,e3yjr#>7Rz9!֔HGz@0>R;ԫ;z
O*1tyj:0t+"a3zΥY[UP1ѩwK-=jjW'ƐUO7/OiōF7l_h>i> hai~7SL{

-Z>æ
SO.}D[lSU.3E";_7U
ph$;Jcޘo?i5)s,AVyHQҸ3p_QNE;ipУҞzR;N
=i\TRy52Q=b'^hJ;ʫOƦ[VGM3	(dsoҞ.lߥJR2|_Ҁyoyxk>/¨SIW
y;ۏ;Gu/S&xW'ݝEy0@"-P
ζmHJjhRFֻ  W;g	eEtw๐n*?, r^Ҳ͙TQ[$ZL
#0$G'qJV>\ȴ0za/#V 7i
Ҏ*OAS-8!7cM `u)ELfZPΏ=ۢS ޣ󣙅
	UF?*#li]ɚ%!T/lXGSƔCn-*ḱ		E3w
U(c)kܮhLIt޴bẳU=}'FÙWʘiD2tM44$ b EOz.KEfcjΤ-"_/yZpb4iMKq؟Ɯ *hZdZ  kKDZq9sQE'*)R.y>H)˾kzORG!ދ2}iB{3?4Es>CT?ލJe0LK>cFe3ޛީ4}h~̺_ޚdFoziޞ/oR2|z,>B=iQT֛Zv!tHe^w7X|-0T֓>Bᖘejaޟ(ZaLiޫ|ި::mw
#{{מx^S
{K7v
c^j.bk<&(pOU?vl?pm N @OASKwvXFybz(>Wt)QeP.mUGGۢ<$_Cggr  tڮ`rS q'>¼zQ}ϧb=^ၠ L˩/.^isj-!a$rd
c'TM #xJOSҐ2zv=IUy RQWc%RJ1ܻWpE>訪@UQjn[@¡ 7^=j+peF6[3Iw<kMcc{$m¹-F4RJc2;͒=2u0ea6JKf[܉zա'[W-y UR>J9ztJq~`=Ӻ&IIY=C/TL0k侈Șj
b#"ϙMjNPwi
!>$\:՘E 4-g[xZ,n>lZr	Ey"Vk'.j,n"5?=+Pp~?=aSG嶓}="O@=;:Fg5ʇ]׉Y&._qv}A6=?^ Zڕhԇ7a_*3_?t;䰚8	kv? >,8yu,n[i?uv.״X }{0=jOxzQ}tup+]縧X#B3J'c=)Rl|{ʞ$bzpT6>dm)Dz1}ѥoF\E8$?8^ i{)4Mݐw_.Jp htxb(}L~/??8^ i{9Gp=k_Ս8_O6BN
֜5!K466@Y`ᩁGYKk'LRQqڗYۏY?ڋGQFj_7dj&{RQ}{7|KJO9 ZڗMIG`FӄYJh_Z^]ʍA#zQ#z__֗@{}3K˰rFϨ~=)E=!ҝ}+#֏Z^͇5Q/'4}(l='bVH_
Qz/fٚ稥G#!Sj)EaPxz;3KٚǭhxmAՅ.F/d?6&~N xQ٤$4}f>F1K왪?*E	X 1ӆ!G+%ё]J1iqY&t*:]}O\kzGJ$Q_?@>r e
e .iYg+ikL 
߹#/@ Uԓ{WbX+ZVEPƺdoN捴HNR¹eHVť+=
oC^F11'WeҽÚK6s!+Z4+sOcͨNtS+(\YI5_1R)*v6Y=iU`>L-)Inl]F;UNQM?B4X&t1ޣklI֣:ߪftm|ΝM=I6YDo=0>u54Ӫ/L9$Z#7^juEêbi9ttfސ{ '=(rGEGڇsڃ~tTQC4zR}¹(o4{)}z
O
濵֐
ﰤoҹM:c<OH~Lo[ړ+: k1M?=7!cUk6O4W uR\՟iV_ҏ9`uiGrV|gkIOu>x]i?4!{ΫxPjGդ;ùՙ'=kՐ\j up:9jOxiHnGQGzƟX3J |RH=iUu)?:ΦHu&iUS:t4/r,Oޘړ
k
:tk_
俴֐^9V/S:ϵ/4ݯri
sO>7M7\?q՘}bPoo5?cOfPoWsl>{̌`Nޯ5sj keۼ x/ĵ}@L'W\;W[Z11=IڥǾ9#}#Vu ??տvѦM<MWVZ /_mDi"Fe };ozv&n~iwj/Lj\~zǊѴ *& Kp9Gqj:T) LT`tx_ٶO;
:IGfc'$+ӣIR<\N"U9QZLt(׵0v)zǭK2\LDcҁnKeg%#]P[,*Or}k.->S<zf9kpw.GiMkbue j"nsY&'ޏ?GP{K֪ǭg]b}ƒhCg>=kMd>ⴄ 8e/sTĻ8QySGl];f&		F(aK[ZN
@y_z4onF-;'55frƓ%[ +WR93Ƙe5w8d8FE4Eb0/4ąHih(Ziu-Mt9Uz)4*-t{íi:&QWW:C!-ު?h:Ժ>>Yӳ
RYc"H%^z*FX:_csn7ޮG ]佁&R;R\}OFSU<-au
ͤǱ ^R+_OC˗5)o ]}lu_-)*OCSy 5QCvpR
X"uiRJ,7 7iWh,ÃH3KkhX@#L1N8`|К~$i
/H$JGRpLfT[Aު1\Q@F#8Rq+H<_/_zˑlcֆ	Wr:f?X=8_α~?75"5"CxH8.ӆ5ϙH'?aԎA{0'|~58 
1#4G=5%#
nZ[DnT3n?(1eR>pKw7s/$q+qZIF	\P&hɩ|FzR.ESW~fZN@җs#)~KaY6	9L	4J5MԛNG4?,YI	;p{ҸI.;
=ZM^jGG4u>uLQG4۲c:k*rܩ`^x#Bv8x_-1
Z;?J{Kt Jΐ>/u?
yn#yُeּSs1!ߜ|z&#:g̷z:̚[$_Su^Bc$T!^t*^.
1vqK%nW
9PYg3ڱKۈI8#RiE/MMy3Y%u
|7*X&#j]v9	2O/^^uΩXRpQÅFfx]t+YkC>;c5Z&*\>cc";Khjl'^)~ŷU	[ЊXxaum>,?¡[VWP?Ҧбw}]?>i^8V5*Hy(v*Kxfh+ĊiN*j(=pVO^AstIf:rF*)/9) wu+6q^́0)'Rml[Me=,#U8ߎōAsу[Ky
ҋ}2?`[m v	,b3[5pcF ^e(֊qVh WA FkV_KT	[8`h}YIiz!4%e2Cud6NFlEbsb'">d[iHj!1Y>)HVcUs^:OQYѹG5O%z-:As,(X^B]O*Ҽ>;Sć=j]M
3eNHKyZI6rpc8\Q#+|1~)cM<ys	KAYHJ^~"1FRU|ªvl*^G:G9ү.;_zW7"8ԥ?2Dk2:>ThWGa$b
ac<Oj=bXp`Z⢖;n$%sϸTe4i\M|2q[e
5ʉ !keI9[   kHYaV
R0y ^JHsfjBH[=Kc5$8,H8
Inev<]k]XǼ썈 8E&MZVuz2jڔYUĤv	U
IemzKuiuj"HMB7Zk<}Xd~ sxXv:l0ͨ͐~wa2iJʻ`\ZI]anw">Tb-o+#g*@sMF=Y2"ܸ;18&nN9P?,[ iyɽexJtн۰\	h㘏+Rs ֧&o!!L`
J14Ɩ5vnq&-r3ЫTi!~Z^]"7}*[ۋcYBb>d0꫼\4ǻ?s2R5PmmkP
mbFd\YD=$7ǿh変MďtJ_lw?M=.1ۻ(QqesF85JZ"NWf$|9B?*hmơr৸lsNx!~dz)soT*[t޳p`3Q~|#4)V!՜f,IV '
ۇR@뚂MT 4$ uj78@?ÊF%՚"9qSe|/mK$,)rX~=	UdZK1g[c;mrUؕ6S+K}[sL{FPUTPjI5ԇ7кw2}KPGo/fW;Rx<Т͢2?ܓ z<9=MC
*OElv$ӽtR^xghd`}ED-4Br 'YFxԍiQ(7v۰q3G(swdo~6֛rNGOw"`4c%]ƙbTۏlQŻ'5NrK
W =MFLc<zϽMol9+Ue &l}>o[vǴJQN~AJ˨\H5FP}䉊ۃ Ex)id q?S}ku #Fԟ4@2IkܫM̵ƘQ?d<+Sz,%-
oXp#{4:GӒDf?5ŋ{%e?,2762
_RTfc[~2!/P=} p<ݙfXi/gQGC^!47@: E4vϭۏAGNi9Af,xt6Yŗl+ڡD(2@iOg+9>E8[VDf99@+R#_d>W.v4 (G&OJ
4wEj&~ˢ½y{!\L>"|}DY$|m }i脮ۇJ9UOsh1YV:Z半jhqB^MXX|d]Gf !e|b qJ/_0\vQpM4 Sr["biDV JR+&>P߅  ͌Eb4dhrIҞZ2)=
	L:sJM\<nHȪ1j°}J\`~VRTZ(Tfu
Ez>R"J5`#jFjq=V`- =,kGnѵ/6lpǱ}x#ċuo5
`dqyd Ia:5v=Ў*KϺ<v/%wg5ֲ}Iw(]:H٢u"`91_XMuw2Ouϛ ?<>2ڑ@yߍR"Lo
Fq[52O*Q[Nѩf2pe?@*rPڭسaPWoa&?$=簑o0}{|{f٣pyjxHKdT井"|0>>Y@5O0Ii	mt5Q}L>WYۆ`}C
$pAezk>[lF&鞔-TpcH-\ܞ*ʏ@A©;ӑJcZqxfV!-܍TVk8@LlIFoR}qJ5Fǵ
7Qq[rHp+ t
|z[9C~AϪ*!YCe96mmr_z@T+2=-WA>@$SR&W/4nBItgv'Zpd5V,pK̊3*1wsL]pF sR bHWrܦ}j^ٕ}NCmi٪1?5O0qt$-T9So[7r#xj 뤼anL>:ֲnMZ3FSQ2]>ަp$h#7ճ2n]ӎ{Xɫ5Pt'[JLG4Zm:'PTt츑Tu*j{`;wŴ%RFhH#)#?5WB}Ƶ3|稪Rj32߈5;]ը$LJ]Ky.6 3zđޜ OBn,:U!Rzhٳ<k_ҥ1"`g=UIw7WZc21P9w$wr2ItصV}Ε5n֙&3폭`ά#`utcRR6ROg^桎';NqE;TBCW[SovVl9БKm:nG=+I\֞w,"}1X->dtSj^IfBcVFcXTPEB ɠf>ٌrs޼[&b`Lsɬ7=
"Vvu"yCO[De
bo^Ib3\wVJ;,XsY*-laSuJu+L[bL&$}*մ3fGT ci2ZZgp߻¼ZOkN3m׊!bdou4mqy۩CTc֗ut猉4MTSS9-BfǢתišد0N~5d0'ֽzHd.WZEߐ! ҫJk5o,u:Ψ	{0ksfP3V&YQ\ήB"ǮMD%APv2NONYӮcl|;^tx|Πvě9jc5|-4L6qsSCk'To+"43t5;1qg'Mh'sȊdn 88?+.wSY>]te9Y##LVUΧ,9jXT#$ΌӁi2ZW'T
׃P]9xɪ3@܁)G<Vю5our-(;3X&Vݑއ,Nza'''i'* L| 2z|35_0{fy_jubbPbIZApw)U0v<~ɬq;7OZ.J8m%Rբ
8#|8*#8['C$r+lbQV1͗ӡ=*de
?<X+iv+siv䞀
\{Mj;ɒuysޫj=ÒOJ htG9*_EjyZA$w*A([v6DImlmB\hE7;6JP^+\>7GϨ/]F$vpŉirM2]B VQQK~=k]Yc\I厸=iZ6\ҽK	$w(j~lArda5)NmXʕAF+\^JPC6Oc 1ѫgMg^wR"ZQղr74望ݫrY^;@~WS2u"WOS~{)?'n]S/zSHj/vS}*hǩpq(Vk1ʻe@AM4~Х%8=2eA;&+[[{WIAKH6馄%4Kt`<XgѪj;X@i#']EQ}\e$
UxMnIo4jqfK
MNDʜLʒ*x2;v/&ڠ 
\`B
ʬzm|>!@?&3^zte	n+fW@cgִM'	9P3Mz	1#7n77
[p!TrQMt_<*bL$emO?>ԥuQQzdR'1ZBۮz=>=D܁O֝Bڔ#m6<y?]<6ӹ/ՙܖ?ROW?^ߝaZh˥JUe_͟xitK Ҩ7RO
D(tI9?v/=N"6kq w^/q3JHřI5Ń*=CKr2rh
(M'&,Zv}iOȥG=} $})/ֵt ظI;N{2f0zx l4w+cjaU	 Vju*8埭1}A-͹_S2F*9O(ª3I5' aH(bLXG@OAVcTM_xŬJ9-Y$(zfSZ
F7W	bn؜ԸYzTr-tۍĊdH Ҵc;Oj=Mr*TR25xUNѓֺhKCt,ZF%rjrƺf\[AEloJ3Qd̶nZJ
;U
?*x9eyCavm,
KA{dqޞ8~ozKi6<zr
HG_zh=LuQ@ɭ$d;Wx[z.: xz׌wUISG,nW-О;ozHdӁI#!	cyK67mI=G;WiGq	$d=pkE
j2Dϥ]F;wTW/z84Z^O]r̀-^={H!w|&^'!o38 ,0

zqӣey&z58
삩!}eTZd<IcE@95Zm%LJ%8Lo3<_11\&|Rh'@KsEﷷYD4>DOg߭8]Gd9@A51i\^d4aepRVvz?>T.s@9<,@Xbاy>c@ ʿ4ęհ U?8➳ir׶dX#
9ECj&\zsSf9%.Hv:5U<wu
*ѧҢ[ i Sa̻Ԋq_Jv.c'* e؛ս:sҬ2R1ڬhNk)S7m
g~;a 9\zzUT .zT8JvZ֌ mˌNgjU`T+Ÿɓɿ$9%ޑ8tVk=pb*MdW<ޚjr7zu͔p3Lnc=+H dw⤆HLFTJm+lbLm(U#)>vxX£ 9atŅ$O
JgnkMn\nn9 
4}i:%lU۩+OZ
ƠT8
RT"g?.!2*8[ZEݘhN޹8jD1R m*l*AtShUHr885|3۲~p?UW䗘Z9]"#<%KnBZ5K%jƛy"WG	ws$1<-:sRmu*FȶncP0
iU?¼
9)WCʦ6Υ+ZLh*9-ɦB;*A35c6xz5?VQ7;P\`Hά bCj.TDD@:(x&k6YoMح?4r[cq OJr }ii@ilc\p?5@S]HU?C\T8}+J=Qϊ,fqKN*d>UMN*Z4`*X WpIx~+4떉=j^Sy^n5]
ZT#!53 ޞH g<p[=="ys֣YDqYNQ38$Q#'˵Xxojd-*Յfx4[{ú.Jknd^)E\zn% S# FntZcM?] 
Sl=GZ<_ȧsk3a13Vs0ne [$dj{Fn9V $HaW_Ko*61W.5a1@
\ҥ.kڗ6
[2a;[Nk_ݦ *:sb6VWocZpꗐ'd뎪pMtG+Fsϕsgv¬c|/5JH#R3Ջ?ƵmH{pF8IFq:&o*r}hR|˩
h^鮄w3n @55*>\ksɡ픹9lḣ4!;B)npOU<e-QV	=9$沅˴`
n'sfg*7"D
 甆T+
[⪙[hW.Ĝ`}j@51ך`lryU8Uܽyy/Gapj4ŻXdiGr!@ ϽY9d v6bd)#
׍=p=9i.ؽnVr?*mAk5ҵF{-MsIUIYCc׌3tmp$TtZ,$4P}iVllwfR<
iQ7\s@7&9Rv}itQ`5ThRĊ]0y<R]Hh{К9/0`:Bdr){851	ڛ$@~Y$ȃ=ͳ%Z0+JڮXNcI+@HU(Fpk[OH [V\ZL	"}v`=kuH@ Z[\e؝n£F{A,wyD7Oưu"1F~g+ؾ\{=h=C]Lt\s>"K_EyO5G I1'W^[hc˄$GhzEk<n=כxW5@pǹ_{={i|O $bkΥ%vQV]{׽|IrrJ3E! Bicqz{R( on!%ؒj ;aho'XQZ{8%}mYm"THJo4"X
)zU$F<)ҞH,Ku6obǼpH5zJFE>TO;-yѓ~'1Mr
3$(%l}E iA374ihzG*)hzu{y5̣}Q-ztKdML=&:PF!?
(ZKգ`?CY8t+VM(188&>|6pjΠp[Z.qR+x)Ehq֔&:;o7H1\ֳI_yJ=wH
9-wVT+wϭ*rlDGS VUuc=yCB[H
m50cjLNQ'K8Uި#*=#	v}9{yLn=ǽnz5M0zJ,D19V<n_Rmq)l H#(Ҁhu4PQxKrhdbֲ`HVZ	 	*A؃^
z|QȚ]>J3+5=帵
=ҥ/H1{I'}9DO%dFXto[G@ǖ5Wq*.P`8}kL.!Vu/y/ڵbW>>p3\qTQڴMXg ]Glh=eYW9\h֙pOWIMJ1SmJ$P"6[iG5(sԚzSM
T1qYW 
2oFc:ijҐ:Wb{ Hޢa
ہ3qmԹ$gҙ\$ӹ;'45`@0qUrmqE[Yt {f-ߏjyFHvYzсZi
2r
an9MdK?5T7zPJ&ZK皮֞IՁtÌ
ÚwڡRhm9#o_²4/ZZoqUhjVq\ДQ뚕*1C4k`aT}*6^v+Ciόc/>̬Taڱv=XO
w=q*gQlrȠ\V
,]LTOֹm
Xw0G<f!w&|?J궥}ȓyeĉ%l`ުdcq'\gI]6zuY[v)<wj54҇nn6US}?jrK3{zkc͖$|Q&O۞@ҁHvT<#8>>64Үqpj@A 0skMqlbx&/~\qC3Q㷿Kek~RdSX܇q+v㯩I$Iɸ[$f7n¢0ĝƦoݠ,MK4n1`\t%A[]oIJp#$OGvZ?1fN$o3<ArPjHdޫ5*i4\exDhU@w
ۤݠi޸?i@q ^u' $JKee>lCZbw/jɊ@	:VdH:\6I?)j$~wQ7/CҩZ2zkZvQ
f?՞\ڢp:OFfctL j߉>q`}#X;}ymn 
jC'&5Hj] uLOlRgZra!<RHrr#		XгnTPGPGja^*ьmK"PY4/9:SvZ6j<WV3HޡlcҴ"Ԓ`!JP-YkND&=k<ycbRFvkBkvTu<z	/o!ms(,Cp~RonǠ4s;bN*}Fapd$iR1[OcJNŖg'ۜ<ÎMn&Hd89AIa<Uw9Ry8fȌ)1Xdp#$yF1[`}EW#75&L5O0=*N9TeߞMfUClsJMD[QH٤ ⨑bXiY4wzJW)u9M'Z	yBƐH0y0qZ7Λ&B}ic<ո_!~i4\n֧ٖ#˰P2}+Q j`ds!;ǥ	QLZU>OJ0>Ǒ@:TbV+8ETyOLӳ{1cwzsTVe[zڧ3	cn, ݴ1HPn) _
a)z^
eY}.H=Qz?j|6 k]ŋXX"JSo-v-Kif}O^V6/c
 zx}[~Ǿ%vK?|^XēOyu-̓ر&ץêVO+u_@Gz)+47IAv RAbvS㍦ce4HU8{8d#u>ĕm5"Ӡ]OVFx})|:NLjYXۓIHASctj6&_cl }j'Gc\<Yw6d~DkO{?fw:l28h=VEn(p}^Ky
0UَUƾ#XeaBr1"bsSԶifI;2{ծ}*8Zܲv
ɬKc\=(=i6̧nAIaWث˘XGrv A31P'O#hcG#҃H@ZHn8Ɏ74O miϤ3S*XwtŨiDH`EX[tE$[aMG~m^q =J|ql.YQz"swBUSq8jv1zvA=)H<0B0+A-!R^()1iѹG6L4]oV[; Kx'j4oNAP#W_MawRHA$$H,Uajj,%x{*xB&ȲۺoQZwQ&Q ,kw
hL޶%E_~"pݴR$L0O!GҪJ?̫Iћ uKQReQY67%?љ`n j&#VX{doޣk7t慸S,hL9,j2G )w"PAW~lzS{qV3zVNKc"9"dZ@=)ܛ+nv<Ql\ eEUs
'"h,*:zmcև!(8J,):R[±yϯjAjO]-51R!9L[oJ.aYPVJz
T̅<r#Xk<zbKZMu;4W2C_h?δM3.Vڻp0y}i;P*8n8 /Z-"mU.w6^E$ADv\GFڝyoeZuܷYX}؜H֤rI.xśy懗f,gqUnEZ@qCAΉd r:#:[D` :*~fb}i:v5Y:a{`9<I2xN Uo,w`+4JXm J*>^#5<9ֲtPԊu{쪭 y?U =EyԔK(ԻRfǞ]˟ڗOS |
7Qdh
^?y?KvOOVvFKK5k?R^w<.Uص9w4?.c bݞ ߱Y9JCG*r'Sx??T@yۮڕ]~_n x k" |pBp#sǱjEuA	+*zPy$rs)XU"Imv8Vc8$pAJHGj.GU9ЛJZzHQ(P~
 R?>1I_5";'Hn#$Mn^|Bo]^%;XA1)-J`fupsZu0^,cꖳrnSG+<vSKj٣ 	-G L+?˘OK͍1O^<dBW ߥ 
[
K <4rǰ  KZ# K@9!4Ld&1a{Ieկ?:ߵ 
C]ޟ¨|ñ␷$ʻ$W kӫmǚ*jMاʻ˹u{ -M:L5؇R]ڷǝ փAKZvDs˹}uo
5v'緌	ֲ 
5RK3?`µOPz~,7)zTbd#߷$KRE¸j43%K:9G5U.	uqO\pn{8
W̝X88'[x{
Vc:tYa_n1ia<Y#Sa1ٓ3Rqs>21ҫp *v+ܗa4L'4Bp:uA vF9h	qa֚}FF<<Qg<R7sAHT	v3cx44L9/c]ڙ$ey3OX g54Q@U֥NXuRa+Aŷ.QfԃҶQ

LMc&YyV@)ŰqnMA-HS5#ޠs6#I3Sr7pTIydzd4#O(HUCnbpRg{V5v.Ed)ܳ/\`9f?&]Z-*﹘t ܓT4ƅuw~'Wχňܿ3{ֹ1xFoάשQ- 1
}3^A]z]sSy"%c_ExR:3+>
⽬f-7i43I^!Ӈ?z{S(: ܟҁ&YZA=nKgi A͚f~(]Ao|r)nJ<f\KZ@lR\&"KhMeG<UwY.&XӖcD$qܤ
zU [iR=Eyf4VOվ
9kϯQ]4zZM'`t3?*͕)qUvCmsZВ6'50k^	ҊT:;3 zF`2s\.^kRU[#sB;i*NBMh-grrU H5JJ'	8@ҕ_ʣݎ$XW=;~?ƣ=sK$B*,w+sG{IOZnj<ӱsJrb@/dcwtYa4#wDS9Ha 	T~nGZq>`ւzZh8>8VutMI%L-ĉ+4QRjE[3ZUeNjqkZQG[kV&m&/e1֏<M9OH~F'7WeM-{L1>xd =+§̓ }q}>% #-lv%][11>EAÇ_CX漈R3? ދ;ß;9`1* y'}Q; ctR)#=)Libޥu/l&
NMR0n:
gbOZkaT'GI	r=qR
z>\9LR=SWu=TKhx*!
.AҥFcTPB~ʤ?-ǰRsRqn?ۨ yϯ^t[+zG_ΟҸwկ߭ˏxUM'ߕ axIGɺRs9?ʸLhO#v8eb؞ ;*ŢA"i3INvAriXȲ)G5CdO<?#Qz~Fi{ 4Rf \曑R=M'44O E!>&}:hnO
nVJKմ镣Xa*Rq:cBn*]EnjzRyZ\GI9KM7Oer1s R}iݮ޿s]FA{crY~E+D. WX]#ET*t">m{SQԟʐTKt8s?h%?VPF3~B}$~b<3uœ&+FD䨵qгe#[˘(OSŭ|_J]	#ڸ[KvѴU5\hCk#'3c[ή+)k%#'' bzxow<?c ګ
#SF}՝d5 Ձϭ*T~dՓZè]#e.$R;]ҡյgݻn
vrDqkuĒ<{4/·O(-úիSkXI '~}jשߎ:ϥso֭;'Oh&T j,
]j#}wn:V X߻}~5,hc 3ľLLΥ6esG$VZۺ9Mz71Te-9lޒ\T6^Ri_)$sH) +B}G9KQz^ДK?WLY;dӌ _c hjcJefx})sIc\_o$c`>W}K6e^Fwy"յkUrI2=+VKxQV2Uϟ)$,Medw.%&joܗiᤢZ%A{r1j"/.@%Lӽ>O
L>k ЫuR3"ԯAq PƱj:+=56֓kه!*ž6xaf2'haG4橽[JU/\j:K['iLIxanSgxj}6l#o=3N&XI*"zr.3ߵЋ}&?joi] ~HNU1 Z'saY\w<;v̄:;jk',<W;)ki\!>J܋¨奻;+m@=kԄg7dsLT0k^@X"H71׌lլ%+ŘT$)_z1 q]flbkڂ
zcԪTPWeS;#i1]\:]jZ&E|0j]Ym
; ֳXo-ᤕ sQϭtڎXK<V :0Q (tp'oA#mx{~_$g&u+:Rg=snWh4MfJ)IJHM &1R&qƢ&"jWk -7uy%3]Mt֐p ZkZkȫp"1P\yqS(&kO8;wf}%cA2d,3Ԝb+X?pk4՝:<3jV__)Z\M,x+ENp.s[3kۼcO̜}k=z>S}SʭyAe]7Al'lze |20jTlX +VhG5ZB{gڙqj\DOR>RsM Y2ޘ<\{n)ؗ"o01q uMo')9vw
F֔O^MKNQsO4`HF I-
PW35E0!`<ފ>0Ojo.s1[ơCdy&&*Qtwy?#l鷄Nև<F4#in\̸$uE cNcAN8䚅څ9gvyxzOWGF rI94L~6<R ' M
<=M'$nڧ7SL[q޵[R|T  ⛺"iZ	M&BIIbzfƍb9Fi3Fx@IO<jKړvMHTMk?4u)z]tJϳy}ysT:}Pr_uT
s)$uw["0IV1ii~zry+Ϗ%~&LsTqRy+1<F*MG9`bFW5- l#-\r+Yz;iTojqع n k
vQܓe r2F&W$9-Ŝ%nv
0=hw]j<K䅉 
Lfiws@?> Z yK&p}ߊ7Ұ\ ^ߕGގMJΈqՀT?WELa\kq umH<@
^( u/&){P1XqjV Ң__,wsY]Gq3Erʼ9z;pXastzG4%ƳaT||}+f[wֹ4On"GNe.ؕG#s^m_@5ѧ.YZ6 o}9L9fQX= > [bNyu?ҭ ZE_rc+ν%3u:W99γjݾ\\k#q-A9cRMdQڎT/i.kW0$U쨨Q;dU=9;"\q#sMFh$^4d:F
 .Em Fix0M-- &=3vM H=)@SS*KSi0:Rh;m{[ [h09JP[=-e0ܯ
yXߕnhK茻ki@ ڝwesb;Z'#a֬"d)L g%V[-ʃ`cZTBьw9"z:CH壻U9!ZlCH4Ϝ]Y};9␞)DJѳ+"nfc
oC(\20;O=ER}Mg	 xldr0x:F$$	RdVQyq&绲\[xڰPhƠ6~3?Vc+	4퉈ϰgqIֵmn,,idǔQzNT݉q~\/0#/rs I[ʆ O50]6iLK1Ј76qʉ$ .dY2:}βnKo_G.lx\
 Y\jq #tӳprSczٔvJ,G 6={sXzLbʨH隫ݼ2n#gos܊e˹$cte_#sTGmYke=e\·,]`y/cb\1ݮ;W.&GnRUexr@%MRC{rn]4
sqn%㹸Y.@p	ރs$LHE>ȜLg3>p	
G=*iSeիͷR֛yqjZC|q#ُ&[T$@GϾ ҹ<	1ٜչ,nJM5M OqQRf*unoZ|>lqkn#jF Tj8Ҝ)rua{woGKy'H/n5-!dRHS`x+!d|Fd$n#|qO$wEpJGZW涿Su[hO_}ǔ,lxڲnU๖ V##Xp! TG,䞾>hV&M["rKʐϧ f#!%y W8׊52E0sʑ<{Jw.yl.myt y9{pA<{qY&6R#$Rrq5m<r ={
`qS|Cms!g`,`c 2in
B6M=0r8c\ޛ۝A hDF7~m]sdݫE˷A&BG3׎6fI$tsjrZ*)bs4%L<⭿*Vx̗1|>ڪY]9 .Ix$0I, ShNVUԩ|dNin5؆[ee947B7__K4L1p r˞^4:L2|e+gsUM6Eco;=
1ݹv5uҴ;\[^*pL%G,ďWg'mJ Pn@ˑm#$'+pY$HO2=`Fx}Fd=H/.2݈9=8#5ZM
ZdW]lr2Iv=-oM.[pBv/V#"%m:(zHŏ@OrbxL=GYF#hdL~~4_Pȇ̓|5g5,ǏVHo  
o,!+67eQ+dNr:TĽA`*3WTb]>6Gw>*[rmB;U[eWkqcxd(
ЃWdRK:9@c>U.%Yܑ@Us 02{!uVD8&<SGSOD*3pXlE%ie[oe׵]ێp}GMGqHn*s ~5^ѰvGZi@uk+PpI޽)X0}IiyNPz ^_Wi<b`[54Ѷ6Q̒@ϧ|2i@;d9O$-趓]%ki[ٴd_B9Y93RWFs(;HJ1Gz^FbsG4L4n 3Ab߭)0i9i)4n4u 9CIڗ9	?<jtoW[nK+ i.r>q7ZOi/5ERH#zJ5eu>^ g!QѢ4vW2 H/^|0&gTI&O4*bO&K{9Ggy Q}ֽ'Otp%-$=ڸ_j[j2p[zǠSğnť"!#ÈR>OSZ{d&~_%aOV7z4W| xjʬFii	 U.sIuLD[AZʋNJE%Wʇr
ߎpr5<fЧutP['|@4X`~}czf)NG4x	
GE_1(VZ )3v2'M!5d#Aj⋡r:=J-<8ZI4
.t?g#:4[i=W
Oj/jDy4Tۧ5#Tq6 1_=Bv lͺBhJ5*-5EFf v$[rĒk*RI4R5dN3RM9J{vU5j0+	rAj.?ƥ5Bq9\888sls#٭p09<kC&)3% )4M}ߠT׊W/Aƾ/i'iss<@ߓ摵"*3cxzz.q"1"IRm ֌Rbx43HQi3E%KwG"rI9&Ej^i^f( >3P04}(&; SiB Q4 > Z;QF(uH3zӃ61LҐ)Ehf4!a 8\Z:d[ҒcDѥ$"2R.ScVllc5eO_|Unt^ydḇdTW<6Pyϛvr >.]}da: >ңҤslgs[1C tRd@"e܀֜~乒PJ[k6[E3)eCՕ!>d].35:)r Os:
v<(jK>\@QXy
Ee:[]*ʧ55̚i@lc<eV n\[K /ԦX01Ԅt❜5f^]$`v~b37evfnȩ^~yBXuu0NzaulWP4H ;wƦm&SM#Pi
sbF߮jymZ+K6$I''N=J	>f9		#U/na,V-c=?*9I 4j_hMuZۤ<DcppOcRGd[0Dxx|LdsOwaYgǂqSݓǛ-[.[wGoX?~YM+HŘRaXUW<c?V8'%vO/[:՘dm=8bݦ*mlHc[[@:qި ㊵̶REc4bI6jCmO3$#+ԜB r |5[3;켷6olTS%Ƽd\eڱJzCi5)--V&&ESyRMbbn`>EFsו1抍hI`Kp18aTp' ld5QM-Iz!ā~6{p	aS(c4,m"Mqp1]ŉ=pRj6Qf&xsod~Aje%LJHa·ݺ֖P2NW $3q|۝7&2rbj8>Ν|;yY$#*}9֤OC g
p5ZivL??RFs~I_kGG/;Z6d'Ӱ>Ǐ~<:u
s$y^K@^3o=FArq҇k"UE{m_i8cӞxA	8$IIso-ɲDᔞg֦Ⱦ9| P\F&78]?uuզD>ZI*(_Ɓ}H;l[wm =j9⯸C|\LIw*1T"6iFa%)V,
;G(LFN3Qґ*Kq<Ox џ95R0".e' ~5 Vak5(v)b]>6d0) rc=8i)i3"c66AR^ZYaxݻ `Q'>m6(rgV,hq@K@'ZqҚFG4y<dMkw	 s	ZW՝11Y@nLT1X[᱕&	!?) {\ïߒ
_?# >lnU0<gzUq5TI>VL=:BZ;qFhC֎vGz?
9 (QE ֔QǥS m Rg"1
bPގt#mNi
!sRQ (=q`}iiŽ&=@
ZRJzg#2;F#aƤZ	bWSūٹW:b=?JiOB*yjNʕ\sOZ*ZXb@e:v<᫱jֲql'R-N,dVSp
#wH	V5MB&3= 
,;<w9֟=i-1϶*haB<}}Z?<fm1g"8&oNXy4\CO+M"GEJQж?ưHOOEm?Ɯk##AFm$}7ֺ5q>p Kw
m=|+LgzNEj/<Һ:K}^1Aoҳ.	)s1\G5#O֚\)  't(h Eޒ \ɤ٥m- --% KG }(Rs@Rg wz3INM ;4nF( Q@Q@Ҋ(aK@Ü SJqJ3N R@!cSӔ7fߥ#oT aC!Qq͎ }Q)犯aAhrIIkRy*+a#6՟1tϭ+*+ɓ9cr) ISw0#Tx%Ƅߥ
+oCI`ˈ%dg$RA O'G6NR
V
h6?G2#*(zUN儿ӟa'hCeL7('Ҭo iQ7 M9{QTSoʂ?Fd_?~50N9J AfA h@rڬ{T{hJp2EO߿i;q
+0a*}>ƤH6ɑc4s!ip籫!}Z s
A>&7ǹ[dz32?h+}2#ܪwM&~D#
qUꆎd>FVޔlOO_/.BI]zc2qKO2W=&늺LGSU<	&ary--*"+gqL\1'1Ay`3`z_".N=x9#ECgކqT` tT+ᇭcڤ*}I*wcц`#O9 o |.U‭VżX |wg= 4r2֧l­K1MkiG9pbSF=SC|NJ@';~hMH]-g 9@jx'(]!֗q&{Ӄv>TW,d;w{pE_M~/ucv)sTVOrg'V}h9'TUWuoM s:wTT6ZO)Ye 9y:.'A
BwSM#ҋa>`sLBchiqI逝KILB=iGZLvs(44vEZoh=(&
 m %/4b0 
Q@i(׊mR~tQPaHFP
 Y^3bN*zpd=gTBFZ?"Ǻո$(n+ dұJ:4_3޹x3v_QsR=
+L[},GZST+浴>#_*>;V5=%[TVEwqҲ_$kZG²ߩ!jDTrj܌3q2U8HxVcQ#zl?2=>>U'XuŖp1\ֺ?<gҶíŏ䐘&R^j2i:@z:E Q@(4(<(9<S0}ip QE -cq@09Re-!PRS p)M

(-%/z@--%/֑CizCgvsPyc۲V1>z]koy')o)N)o<`0T]޵Kw<RW=
EfKFobi{
y Үrjz
c!W3Pnddyݨ]^soqjsYKMU߭*۳tkBVSN?VOe	4ߤ.~j=>袗@+7vr~*:D>
苨*3(fJ&Rhq{cո3)<P74PvC1"[xT/JVoX!\v2&yf{DnPe|gZFq"ew4'c1"hR8iK.PqYY$" P	Zz$ehB4D	VXjeK.̅6Oyqk~$1ɸc=Yic,hПSS  kWO5'y"͏,Gy8#Ŧݤ+<=OҲU݋p`S"u{Ю?L JN}!#
HhLo ;V_-#LPQq?k;쨾1U<5mqpU PʆP5.uyj4[>*1NO(=~i{kCsCI5gV 
ښG>Nar3d$}sT?\\mC iA=qV*>us닙<)^jN7$eɤ[82J!H%tZw&N'<qWⴿ*a5Ĺ$($}сS*NH-lrcI0-)@mVAKQs,^ i5a8AWuP`ϴ#FlHXt*W[6RZY2 qsMQCR@?5Z77Ӛ!Z ;֟	ʡqүaEXқc^}UScm#Bgr);0QbDB?Һ	4]{qD0Ǌu$Nʳȿa-ym+^sg_Q>kYfU)%1+7
ǒ+ M,PJJ7%2>J%_aGa#lJc7҅Vctb68mPȭI`au
׷5<u2劖N
aF0?}bԙ%hצD!)|TM8 j,Dr}6¬<Q9mY}\Q>o)R_zy'@ᝇ I$NGZQN5"'#ACX{UWfCB^)
OVcFrg^"bp~W^d
hu?Z,|zelؑy>봓%A_MS2(F涎.1
>N@>/ӠTҮjeFwEQ*ZJj#R*Lͩ-QVчi7Ⱦ1sI0J=3vaiwԙM)4\vCEsSz@F=N ^ )ԝ
1
-)
 .94Z9
?
CKLBR*^ -% J ZJ(zvH?61J*#385ہ:&35%	D$zT4lkBt72?>'
8T'Эb6)$$ns6VS[ Hp٫H hr:ը'+emb|@"X]*#=J]4hf"|Z+CPKHh 8EEg4 QGz>Lњ@/J3IE QE (F:;ZJ3G!2)c34	 4
--'zZ PiF	M 
ZCCjaתʜ5fe*9mJ/r٥D2cM1:*Eo/VP󔗆{_TlSԿ٠Y@b|L DFB@	2eT
jZBX0 񪔹w&#-mnVf~+U_~aۍkdu9I
ժV+Hbg5h1\[XCTzJ/VI~Ꞃ
D,s[\RsߵOk-zwԣo>Uie
vzrݚ;"4J6UC7lHf#E(SLHQN:暦'3@)s@iid֜Fުy\\-6{5K5X4PFne)^i<;m􁪹\YOJF_Hp. iZAOΏK\dQ95wJ-lG I]ja[m'doV~S?ZQIM[V(-Ͳ> 銠C)AdtM],SNɦu|<)K(SU0g.b2yEH.u`I>ahiZTt:1-]Wn""3ʱe7<>Xl*m~Zv\EaGӚRؙ6Ѫ&`n0EPTcڙDB?s*6Vh:[oAeknxpn<qjT5xnS䪪tP {7o>$ø}`Ri@vw#a#lYL3ǖ> )&@9s!FFI#i50Hu9[~FݼeP0^ڭ#Vd5JŷldO/@v+U_ĦC-r/WaTYmM(Xީi:sKaRݿЧIk]?ʗM!
W'y.Fwg-S\b_ިgIc1`I2zTNi
Mwj3FTx~k=;)X$wwQ#*/˩UN_f6-TG=38_Scmyhm$yV\d``΃.|ю?¨G*زP0qYUr?MIXzWK6[TygzTֶhRsɹy@AG_ ZZ<w0^4 lqDY?xt$K˖k>cPHʸ;@C{I˲3.T.nh%l6:r+8ߺ4&eTjHT 5sS$ʳs7WQpUaGa'%s5쐼$=xaVJ `w_3f+Kg2ƕҳHchةN8=
s}ps('*te8V)NemzHf¨w^mLQniuKDa?ٙ gi#TVM˹~k2E0Uy|r #[ :ۓuc-5?, ~êڀs7Oc\]Db[xN`NFR56sGͻK-ZԃO91ɻ}Kՙ^xxU-IJ0Ĺ;_ƛU}㱠+S~r|wUM҇'ozg$5$O8j	zԫq%S-T6'd	MJ%5~S}+-f?<N}j})Oʩ *wOz\9$0UZ.n;Vކ)N;2\a-ч/`vTԪG8=F+A{VUu2xZRpz}*ʣ
oeaQDy c'i<KPݑdR&)B tk9L UqA̹(p>c:Lq\3X5QAkac?*e唖W	YZ62v'Y'A5_TIGF"7?AJmQ+-umpE	ϯ	S5ҥZNrlD碟ʗa}1Uy$֩ݡG:SM ;.i)SM& <Ҟފ;1))x'★FM'z(֛(f&1Ԕ~TSQFh E( ( ފ(.3J<˘,3CvCJdwTQ
 +*aqA=jIYsC5#x1*SjxA$i2p䊷7FOIpF:MPQvݓTM_t֨WM?uoKފJ1h9fg) 4Q@:PEPIJ4 Rcޔq4cdQOӾY8ncSq؋4ULgLLh<释pLH^(zZ?
P?:Ҟ;zz
\"犌#)8:5)l=P1Wb=>J3VMؼ; :.B.W?09GaTyK)Ε;f>bc'.#ɿ 5j>t/LU#RW.;>28_:.Ϗ 2Ix]ϳ'h5-[eF$<S/::#KF!	ӯ[y3ŝǽ` ƵN΄p}Hf\g\6Ww;e`l{+eHT{SO%[DGɾ& zC MscGE^5T96x#a'Z$#q,?¢ @ ~j.$a%RkRD)Yʏ+8x.9['ѿg]gxC;5PELG+:ߧRe  
^ą'i|ymwS%\ms@FA_Z7C -e(|!Vc2+<6@"IWGU<>GFY_t  sG>2}[<#k[V$mMmlN͟W?K4J#X­
U'<.s$\[SlZ[7 };=G?°uUIUc g?5gKdbZ3Ӿ
g*M+\䓍Ȏ|vyc0
XY ҆)drF@sVIksvhE\('c5"Y1 D
<[B,gf8r*<~c)-Z9e:pz'dԈ ?Ӆ&; Tx"׈\1Rx5NomdIHث38 ֭ПOaiD>OXh'Z|:2gqHZ/q@	OzwMKT__izTȕ>`~ *Gl 8bemAW 4c Mk+$;3rOmD;]nʷg#:Eyfw?HM 
~X:yΑ]B0eaEZ
ve`:}^۲%U^nPm?ۊ_:{' ֬vKp^߼ʌr)־XRC^?'F+W /65hc/$ǒe?؟XmGjFe3qHt[8<
H2.វƟ#˚+ِ%IG 5c*c;0sdչ|-?V/!nxҊvr5X4|mG4׌{ .쥰ky.	#=GkI'@N{Set˥[Vqi"F
`~^c?I|
q)6w c_SZ3JCjm<4w{[psU1 V4-Q]RYNSsB x~-^aA#"n>iu <ގ:ՙ4`$YnrIre)sv+I.tȆ1iRB*|ő7մ)m
w.Ǯj_%JOi[E'<!9 RK礄wJmzd>k2so_ ȷ??տƲeWA; a_ww8kw]_Hl{??NQ_5H$wYpYNV5d
=G^GYtw SH}gE??sdӢ'HbFy]($`>GEF?L JU<cVRT\B#I&Ak]!q#8g=i{( 0%2
OG:1Վ+d@v5pprFyN#hU{rwi|@  CY7
cϥarI<J~mnULW&;O[?M7V YhךM%Ad}'}闚=/ߝU v1=sWE%kGڭ}d j_~_rZ-H. +mA
:hװZ#I	/	'q\藆5QjY`3¢K`i12/'Xou{n~w >mGg5]iWVv3Ŷ+r0#uCih;sϓ ]iu^Sqy_ָDE[ֆXp*MDKsj}X|9U?ʠS\w AMiGN=3Rfit2lcgOn[<UINMtSfTW(vw4bַT#:?=҄zS犢X4!8O4
/Z ,x1Qޤ |SOZ="RR *C@((.i4\Pi3E;R`@E% )(jKwpFhji'pȪfT֩s0w4\W:_QUrjv`TvZDoQR)LiJHF`fIB:	2XRC)i3FhȤi) QE QE QK@	Gj^>gڀ9 ip( }b
ij:wKMiw
CC.5J] NHM)4;=)1z撊Eښ͞Cí
?tx5Sʉ:GN?
*@VME'SCgD\⛻*%50ɻ+2[SsjүjI`%/Ү:yZ(R+jׅwΫs
5W6WӥCx?:Da<`ϵtQ9mLȺ
崐Lc(Acq~BŎmLUYl>㟿Һh[ich2L>~i-+YW8,] Ԏ<&}YYI~U<Yցa ۸J/ _14+	@X/m8b:r,奘LbkM[nH}Б'U>2vPjzK-A8k&Ղ\C$,FBȅN=yBԮm|9# H@wJZZ֭w%9'徧{s =ϑfDNb2c?ʧ]+Mqۧ8kK?̹oKq~i4Uk+E9Q=n(kȦ#yJr7dF3+Wmvp1&~5[j7{d@_ګ٤.^[[R5A')]`ʿKWf\[:qS}N]L}oU+^,#E:I]2xཎ9Q9kX[L@9{Jtm=3<"VzB槀$ys	G.=nKJ7	RXr:]^m]٥jp2-$@vGn+s%yg9_/X0 sONQcݫjwڵm=19W#pqS[
&c>jɰ)FѱT߿thyH%ĉOpǦN$T^JÔ4d(-Nsڵ{FiQd n
wK:Lo
9wXfC1v zpw޵X~h(*i=qU$+rnlkAvlΡT.oFO&K<ow2Oy)GWdyd~#8;hdB1%N3j	t;z~Us{l%y\q?־r+>^a%'BM'4>dM8gW6tW]<ZDmŮN">&yOrnZ2&Tdz
Wzz\ao-&mSnڜ9v߱moί%$Hʺ;kSY@:,BNk@u#jgEuu |y(}.ӼGf'O✶LڇBKHHЙ-x}*
owivy6< pSZG_)c 
όө]C
H,%Y8UJm)VQ+	<㜌q*[\XGR<m,FN7Ԝf0cH_ӟڃMgVY=vqЖ~.8qv=zaYᵶB(݀p .|5w,r<j>bN3txq- S'9ǥL[fjѸ }~A Z9 vY݊麴*}, $>VuRHڃiL/Gop'vqQq#TRC#\fJg+4[v.Zv[8cRrgKɯnDP@VP`BcՀ]YK#),,"B<W汋 ⦅LA8&ԒR4ג esϳ\m=)SKnnOAvRsQ|zv}nInK.ўT<g9ei"fW..#kI+)pGJtsS+r87p1J3S8my%sD~hvwW7|Auy67`I95Q.#= 3ՖO85G_Z,,myO~anoyȷ0ø`=kRD}[烕Oj3^?ұj.%Rmyćz=.:.(΋efvC4<22KܮTE@VU6%_ɲ*Q{cp O>Y NWTLߵS	k$oP̣yAqsa5|9qPHL[v̿s -VQnqަ0vKEbd֮\;-P}3VfɅ ݬhKdٶj=mqjvGnxZ'7gR13D*cy3.Uq%
d
tFAPTyPӧt'#ҡO1[Q'?8OYC}r;8q]tiXN=ٿ	*VP,p^ qV&!:Fɕ=0v5vYB[QLb4c2:`B[vnkwi	TZgnAu]M3ujVM8dǗPF:kӵ-/iF_Yk=ѸYv/qTTʚOu2Ժo5+ifIm\ @ XW7}ܖQsG) #=KӮ/taR ZL.<׵cZEP^LU>oj=RVV`(.U4mS!$ Qй{U(>XI~a)JGn5!&9cZ#|R15hd"c΀z{O^ԹR΀bSXӪ"rj,:vh%1
9*>aԔn.RFFhvG#4LQ\Jb)h J(Gz(4Pޗ&7<RR~~S SÞ)(%PNj*\V+y:ޛE
(4袀QE RF=h;P)x4 c֎>Qހ4Q@QKPc֗RQ@'֌RPQE((ti) 
J0F{SXdn!h'4s!s֟MRg4iN%"@s5 $ Ӂ ԴZd7wLL$oHnE?eV-'	Ȏ\ sY|>]7J]*+$`ΐ5ޒ0sD,U yv\񅹏F٧4ڼqrUT0 iPx&-!
[=yW{QRH-we)KOfsBF4 Wл6@t9nUS>GrWeDN*9Pw_)~bE8 )W4tZ<as+w?3@= =P<sܒ[9M@ШNy=YzhJB͒`UhJ_aV:6 фKWizU|]nUv gbTBy&4+]@xfɭb瑘Pw jᩭn\839) 9޼aMOs	JK[e֒49UBc85RWV +o09H9##b+j~hw?UK2v,
OaS/&ɟ>Lfz" Pæl0}GJ;I'$-7^F=V=4mceq >@zWk]21*Ε'psSOv{xY SU;|ۉY1ڣA롻u4}?2##9.MPUn#h̊}2A7
#=@ߑfO
Dlp)aU   kysbJU[C8e<kȵ?V? O?쓃؎
UT"=I}$f	
'؎
g9GR`*ݧo\ҖAZ2bj @it9
d͓si*?v:&soՕCrR}apwDz d*G5.
lb@TeI'eb1RJF9jŮvuAj\T7JPI?Jr_)EY)g.k*ER6gDsHuu/L$$R#g翌s5(ԭ0)Ogn`$W*&5V*+dɉ4* 
H'SZ|MԡG%Z޶QV];Pgw%Bx+
F+r6Eiko]aok-t⛹K 1^eљvc8N1\Nv,%r}kv:+SNDNQw4. O
4f'?~1X7 OMKepd@랼
ϵg_#?) xАNIb힧1}bYd#;RjP^ZRX"
1ӜVQ"4rq·¶]_k߮Õ_f;Qۊ{m=5HCc@<g礃r^yNe#eCV[4~bF$c<Pӹ	EF~E
	1zc'tBA:K˙n&F, 'p*lğAQSTvБ$$*@#$}
VFMfѢr]	`䷠jĞ|^tw!HĄ>㑤S<chK&82GFN2zʞ
ڐ$%˶duqV^ʷdpH8*ބSCFRGK6~!U#yQ`'SF6Sҙ=RQm}D?!t?J?BQ;XXl,HI_q$
R[xN

1 Y0$t_G5Fb| ޝmk5yP:O V
dW:EĳJ6@yoM0lTzEʩ j&[iydnY݉'4dIn,oohަ
44M0qs;lDfcFMk^kp09&R~D|ocFU.hO,C#fdAϽZvh%*Cʸe<j+UU! GR
XEu}Iug{MW=moOHsO8#fIF쎬`)+4X<ѱR;NA#Ў4͘U,le%E>[n+%3],$G:{\+tu%x Xۀ03I4)[v'HXLf>tɐFw!K';J{㹨<Q6mm(Ŵ 7W!;hZUCSֽ&#%)#0ukT!n?pgjЄ­mA`-MIb͔6pAsƫ5W871'<wQ~'/kS;̯F>ECB(܊f5)*u3ߌX^$y<;)
4iD4bԤjF[M5Q7x~֞
1WSXky|up,ͅGNiZ֪ddgEݴ$^M6u{چ`_	HAٽϫq3[dG}jϋmWtdXg8#U)G֜"ܮH7-*RåDҗ5V3Lql 0M			ޚznM7Z[tqHE2=
g!p4G<SgwS0?dO4QLAKINhiϭ5%))Oր
(m !1(RbQҊ4@	E/b1E 
Z( *9©5j-6\|&ܨR(3.l;T:6Xik
z=_U}YYmm?*)G+x.}+cTH&=AG+h, g۞SK= 
VЍtP>2kE& }'ǡATEEtqQA.)qMO,ZSFNњ?W̌$Ej*F)cia3Gj(@hҔu ֊(A֊+tJ JJ(RSP4=iqNHCޙj U<`*3B$x&>Hi( tYqMtPp)@?Z`4~tis@H~?Ӷ~g*,)v9JC!PЭ1Ojq T1Oӽ!eic8X_|#dc3r2~GlXZ2	\žwbωtӥ9ch 2jxn&YU]Nj-
b-w0EV]Zјdz¹'Ԅ%%'mI/ȷ_0 ܶw<tC}3yH*w`3\0 {1,!L|{f[&L |qkOުS]QڕŐvm7
.iiYH8?SdfbP.udgR9^KT]]ɾڱ\$qĂ?sy<A]hD g<|z=d.Nz-a$>Lzۭ"_#2[3kng{5NY>R]6u{,~u<23lQGo%

)ўyQYoRc{Sԉ5erVl:M8}?~cIHFyUFI4qZ,4/ụ c f=͓e`]\=>U[H$vp+C1-F͌
F@_ P}w:N"c)cO1y81]:\#ڭݮt=1!V=FnƳ4A*\<`yS&YOӤiWt1p:aZ		XD!ZqyjuQԅF 'OcEpUًcF5 Ou[#QdutbA7gĳ6ORiKa<129z09)41uoVg#T4Z}Nv7y{})Rsh[}	3i28e*{94_#'d|
Q;;sjC=dLXmwkH=Ú-?Y~edYKyQ(2 2ǐR5_P` c˥ȉVrHV;|+Њ3 ^]N S
,M/ZLSm2XZCsk0rd{N>m҇Kp>ȿ5)s$S@c)-M'CFhӧOYdZ%g>c?;*qnqc~:&}9Ys ~Uif4
ܶdr2pq>樺ݤa\KJz1$1 7Ty<RB'q҃c| ̑!ML!YV8љ`VQʳw79U{{lXYM̏9ں@͑!o- )?Ω0x(:U6Iw,CҫK98"';Sorf#ʚ>4"?~wo-ABTw5jx:}ǝ0o S$)
3!BAV3oqC$Ҥ1#<p$j)c:fROmH?J? {j7
kRܵ\goG&K}
C=3Af.3hP<I>LCh!TJF#䑁ѠkՔ[GzoJ,-YZHw1 p`	t=Ŕ j_V_OpHQ224wP=t?q 9?p= ^38bre(шe9hބ|" 6UJrǒIW$ENS};P[G2[(:)9b:[ +)=kv
DhBKfT5.$'䋇f'ܧ!3Q\gt&VPާ֫#@$6rr
g
v&`dמv¹SCZ7(cG[ (/	'8=k;r:5AKIA֬I$FLY.dqX9luzKi#JT@nl`<rFA>k*q4jy@ۛsY3q\`ӓvJNK;hti&{{Ȍ:r^іY<;MĭR0 ֪sI-6b2PsO7jo60E[סc*xuP܏܏G5iМ&*KF3֛V73(	)vp8rORsZW{7Hvk4·AӰ<  i>P ;@I4`4+CH 
MiWC4n)֤mt#4%8JdNR`jm9Sh@E1Q@-'jZ ;P}
 v)1Kړ ( S	_i7/Zcl
o̎9k2M9zԷۆ֊vPTQӭV u1HmPӅ.*'Z#{*|#~U>'֠g59gQ5csPi9C{#G\rMKޢ>rP" \OrherS@g#Liީ)M#mf~Sݰ?:RiC>E"1ՔsS0I U[4*Vm<Hǰ5v>V'3BXLTV̩
՝=B#Z+ʛZPij4<(b
s}APy&QwtR0Ywmb20yM<ޙ$#!\%rg=qx2pLTi+4b'Fؒ7VQĽ^:RW<dS@
p#M3rd=̲c'4Xw@`|~iꈼ?@ry8J,.bژ1v:Cڌx$xd$i)cp*yJ,2MNHRs+N̎(VrڤbO1#U1xm*u2Ȓ\-4٭LF?4O>:W`ڻ؜AK%HUAc3})YX˚Wr>+pD!&֬^K{h-rF$rsֺ˫mkL].2'ٷ9#j/ϻr)ݎ:
;8K)xgs8Q8Y[W2iGx1\kmUQU$92=zޫMOm4(Tʣ9SUjT{NKv+-#`{Qȸ1\}*X7ȡu<i	Z!oR҇:E^{r.ŉ<5/tQ)= >Π'Q- XXLv9g2 9YbIzjy{{X
*e,I'ߟҝc=К{qpIHK8!u ĳNI?j	QU^7kuEٚHZE>C+?(qqL2iF\TB֣nX[ȢXY%Opi]èFMn	8?P*	дj>άsɪr*+tO<[]K<NQ6WOyu%̡Dс"?!{6gڣ,A$sO'-SC7=:ȑƬ
2I>%m^I3Y!Ѿ玽+>[xvwn3ÌzG^ޫKZj1߽pβ[HJg(G`>kEyZD3Lư[NN|+9uY$H줈
 ˂0Vs%拭,SKxTݺo5	k{+vwV![7xk\nw-]$YI~V {>Gl	̃<OuZ}N{
Afe-O7gk.f8#Қw)m Yjxs#)
R:隗ڢ'uʹ?uZ5:Zu]gGsa;\<7q<]Zı2$F0>u	ty!m_\-؎6|fv ~Q5Y..ub/$Ėгɐ~bJ\ͽ;t8du}&sn"bnZ4l?s|VYp:wy$'$Z&Vm# %S[ O+7a#?4+! 6l&'HԴynyVe8J(&sQ݅iPt*S-n}?*ֵ<Y]%gI!BoLI{i{
q,bKk} Is%̎N#^{
][YYh^kkXLJTy	8M/RBmlFo¶>	!`t5?o^+[By"գ'@N\#>^yśPv-,D=lYFc\?+KMc_.w}}LI'qMӍHǛԃSx6`(,2qk,]
1uoڟsM[苷ZJ
3u$T><uV)+#7'vKIO<#">Ar9<`\w"39a+fL~p}^I
Ͳ*n9 ~?ʩlGR'䑤rYbNI'h6~Ek&2_1ՕzsVI,eQ%qԖI1&F2I$rI9ɫE%X/(	t,)f[13v32+}~-&']ى6.AH)vn2[!. m ;n>`wlmT~":Trm
.Ŕ$ GӁTl;Ȯ ӵK_3@1tg?yʟȊA.f0&(Jqtϭ1_KK,sӭTnۜM>fkf 1hT'U.}zUNu2H̫8S/Jfe	#7UFI>S;c*.]_Ivq[35Ƥ5ڰMcd>nV.49`hp'9 .49)]%'!Q;*?8'`H	axxB+pA4g(i(ϤYqay'5VL罹1U\ `mGN=B  *қkߴJ#p OsSc_hK]\4۪ 3n<f\"F*KrY' YPDIMd}Iڍ@ wcRn12o 6!PL	348aNGB
q3`(,;N	ZKxEWI?8`pҧ Tś,r}jR%P=h(YVEL9QIjDW1"aQԤaBchd'PKI4 Rgޒ%- .W-,w]/SR:S,*Vr4F-m(Lo0#J{g!qx!5)#I7}4BG~f zf.&UbFj[Kbv[ڣ<~V2WKn)谹E㚌j5rۺSSM!)i
 pi-49@:S	-֛ih(M>k6 XޫNL"S9ۊY(=nK6vuY'8>e
b=)e"FGR0{M4SR?: Q4@!h҅
\{gҌǟjRxU@>Лh8m=[2FA>P [8)ƀzӲ=飩v=

4f U`; ;S	@
$2XhB:GĿR)"(1'jK44Woq*HׯCҮmӭͺq4*ҨH8,yEi6qhBH9 ztrw6zǟs3; =1aYX;rRV HZ]WĢ	N3[:B-uo5Fʹm'bN)f2fk1Id;^'awҧ.KP$n3332SOK.yoך菊/
_Fle|[` *=]y[#u*Â02WWHJΥ`OR UUa%f.jҸ'=cqr}ۋ͎ 2C_riLcԭ-I&{I&AK85Cs{fmD%ct0 *%#hCvnힵMᙬẻ  cy~9b5R S(}85HfI98ԶW2];w ؚƚF*g|nw)\Z^#Udg =y'h "׼(:={]B|C IA[^uЂH>ͦvh]ɏwֹM!-Qo='q[]NKEFBO+ſE +;yOcn%kg]@err3UxqߌTpwP!s;Sed$quV6^	[i\ >Ynu!4*!8+V(to<VL)PI?`9oH6ҳ3ihi|	%6Q΀I+G} Ă_Y[VX\ 8+F~MZ;5	*GP7LKn~~B2];O[lᕃe.ӎܦ
J_jh
~4gMLw Vֆ鉲a`GFqYxZoJ4SSN@exb;9Ӝddtz&ʜi!-}^+>zGrŶ4أ_?9OSnS @*¥'UU.OaY6k}iUǃ]NjCquU,3I$R4r/FF 7wj|Wwӵvt\`7p:b
G]kHżf(TC 81JNO^j4T_D&:9~J1CJBR5?jmY#yG+glPM'f/|.nyTs;:OJIB7I5kWK%AYv6Y\Ec`p?ӥf[J 9 J<H!p|$
DNRW'[k»77aՐq xl\=+S_e/=:W;}[:$*];M+Ha5d4qG9E9op]==MtZF:dʁZrq=띕pːG1jA%ݎ8gT܎s[Tw7Z|D+-Q<y?^ik_ZLr$OFsֺ9%-iv-/[Nqqzޢ\H30ERX 9$
]
A4dh."0^7#5<IȅN99ZM|(9_C02DżMl{
 X13)13U%G}]00ܸ%F>#;z{!w5+^ضH)G~RX,8܄x:7S|nxϾ1\Z3țo}&5"0F)UrAN7SY[t}nIdXӬPH	, dBG mV.!H-oƲn4=:o#kfbEbc<Sҳr}naj77<?vLq9;EIэ&E2I4gv̕ ?)ַnUhؤ ;{w5>M6e7}Źq%v8+;)cyoWq?A]T,*$/p  ^I
j;mD_CիJd7 8PT4Fm}#F̅s*(,sJw5uĠ`I+?j$fOV*zϜc= =*'T!&IǦiwsS{>C@f1h1ޔJsoOޘ:C)Mhh(=h #)3@
	\~u"0{C.mϹ'5/4fۥ!xE 4i4M1
4RIL(( -%P҃IRDw4;Tfp*$N^2@2Gj3*k8gTI(	'BԲBH=[hs;M%.>&MMM !iqJJIE H
+r*.fci<RPIK@0M8!4dќԢ#֞i\Ү( `Ԋ1Jr\ R`;R)SElyl7-_u^*Dx'.>4IBTL{
b\)qR8
Eiw֦6,?<WCz"9Ⱕ]5XQJ)j̬&)z{QތRv4 ¸6frh=M T,qO#iNV8dtɩw-%b' 6JkR4 3J	9Ӈ f;vRr3FG\\Ғ0>QL`̸^RnN
pC1mj}i;ӗ74Kɠ@6.}X3rh&	2E,:~y֘iFF(<
@sSN}t.-e_]¦Is0Ǿk#vzV{xbOjZR}&C.b2#YNOLU8󜚑U wg#$̙Prq؋*Skr Q\3 ®[Cqm_b4'8j[C[^X U$pI pJO ֣u S3tr. I? Z}I K==>/ Ϥ TcGiWiXϵ 3  U=g?cE#[d9;L͟LxZEw$3y++h;Xc,p*9$VCfXm,N+~4NhȽ]$2^ $1gP;z75qZZCra1|_?u뛾Km*+cQqYɧ{-BxyT$wzJ,I!u<=grf{yVKo.Fxn5۝M͹b,v*+Z&mQlیkUN=ArWi^^ZڽC,vXU
V=Bc$6` =@~ZiWt񼭄"$xrwEG ++'??k&FYs =z*TX>OCZ#Q"F ysK# f`~m?5u =(к |99! f toCV E7_ sKrCX?[ 7y ]
w =ϭ&yV?\)#]
pX2zQ.sU9yRhlvQ?3R)FaKHh8$<4Ç<õfWtbL?oϥLvpWԱsyhKPwrw~4ϵ$P<v0U՞ŉcV2H[b7{Ȑ{I?Q#/;HgT{T'ҠV֭-E.smJTIr6;GEGIB:.	 oEF}˷-=(	/iX.- ?Ɨ6>o>a=d^DI?ƩyyҎA{Os	eJշc-ҍ=(.	EG$ŻWXz[')cVdiٴF/%ylˑYh9r pCZ퉟 O
}N "YQʑ3}i% B?<~L21DGey($m>8樖$s('sȦU%fDHZ3CEQe"i*P0Ǩ+uqPHr	SHwG=i
:`7$47JL{J~!3A@z Q@PN3JJ;1FROZ ӳD|ԌI)	3iH''^RLW4 QG9 J Z(@b89Uc;XVݚo3g=,uPiDJQv'nk3Q/Z[J]>v՝]Jw*$(ާtDeogZr{Ml3+d57чʝHd~Oj|1qMNQtPFMQbs֭'2)"0/8Zz֩3'U1x5hW3hSڕb-4i2hvbӏ:5WPIjZ.-1ڕsҘNM&1"Y8PU>HN*[i9lgަ2=*;5'xR.3*۳Ҕ/in8#Zn#)<bEpXdBɁUU6Sёwt?s֩Y+YAڙ]ugH3kdH\A"1-lg#Vbfts@!IE ubHnZq_ qRTqQy,#}}y_#+ ҎFbf(2s'jx=qR{Բv⨑iIc$j))˕ܣ}(##z a =ip,_&̀9^}0?rA<1Mh; RQ@IZxN:P4IH b8ajẳ~٢ld/@P{TjN:M ǣDsU]aU!w1>4?	[9_*y5_YT&	6?1 ֦}ȥp9dTQ?bZ\q gq gbZ2*l*2X""
؅?EEȣ"(RFqJ7u.=ǽ  cNƓ%14ƊVFMRPX`O޾
)ù.'K(T4ŏ5}h֫QʃDI/PRQd>fXWhW֠ȸj
Z,.fL$O_ҍPҁEn]4`AvI)d
,\y4L#֝qڏ3#'4̏Z2=h2cmךˀx4#ҌUSe>CTlޕb/T4oSӸX4V(5hڕFﺳuv6RW1U?M0(v[s;e~wͮ[F )$ D=❜j'bfe W13PĲp3BsRŷ(Zte=lVnVTiܛ#Fzԇ<3BJ(!AIj #8Z?)M=N<h*텥ؿ7#0
?:oPH {R$LFyb}I@#v}Zk}EpsFy#&Y?}@_SRJ\ɢv<C:)9J AEhi5dĭmcQ2y.6"K֊D(aǨwjW(ILAK@f`S@ҹcnkB>P>UVdKq228$'vzʀ\,ouiazUD؎PTm;B}iY!8W7[[8MZ. "ɤZUBE*MjJ1cyO54n}X);Y(1f8?Jb874" cހCH)@<RjE<䚌ris@!8@_)7,;yإsP7N)44dIdQՅċ
jD$#:qUx&(58
T/I"m8$G>* Dgb>hNkMn.捻kXL۽h`4x l'8՘!}4	!bǓ@!#e/4JjYq֋ˎ1r6p3H'ع'kFQkC>E1Qf%<B+EOݫg3!sJ
 ȥ`h (=v4 9wSs; :dۂ8jA@hm e: tKG\}h0p֙pқ@񢒗 i( 8X4m#uK4>@0$q٨ocH8ʸpǳ.*o@ɒ !Q{8ϐs*m.8nCaĜaNj`rvqZF ⡫ھ@Q?$7m?Tjʠ}Ͻjڎmψ8Fx JzXLyx0洣u=
CrVp
-W?<;|ʟٷ +9ԑ>1 :ז]Nz}O6\ſMU1Q?ҟo?Ycz7.!ص<^QdW'S^?*C5CA)B"Z6.qhUN)\ItMfQ?҄Pm_CSeMn9
-~C'ʆ=vՋkWJ沓ir{| 4< VM=<tMEi{)Idm*G,e-<ۏn),f򮠒@s*kEyҬ[pwЀɣ!3,Ml:ۯVd-|u?-o+ƫץRlu$9+Tbt:HHX̓2*a@$}
T<h<ג^U.X͵eAFWmZ;58dOa?*;N<̛vXzOBGΏdӸkm'[lq /3u,IFůbM?e<~hdmfQ鳎LrdЖ  )KI 1L{F Qqjbv$qC3~5X?w)UnE&ф^ڪ:B`\К4fQYy
f6+9jͧhұvv/ ve ~a
[֮wGw4IjKRB J< 1օm,H#azS<?qG#Yb8 ܚ|ѵet:c]ᠸ1ȸ%[ ִ7HR	 :#Q
MUhD=jYdBs3bg'	+"GT
6[N}!RB
F3F6cV{&姷cf[{nI0H鴚sb:jP8Di[_ 
8Y 0iwb??Gm;_ }iC._VzoxlHNjg0
DVؒY$`c5JH`svzToz`$V'>g5 =&Y#YVOL\˕[  U!ΑV1Fz`"C-rʧ 2ʦBT>_qpm2RAcuSOJbRR׽1	h4@hT~tc??:L3F1GL?NϽ/?:iZ m6\.i;8$Rai1F:s@
PqL=iI*#
CsRFx>
I;;b[QIpijKdt<ӷ2)b\w\})pr:+0֓A"g=h4qI pSV@m#j1.9 =Uk <*E54+VUIYXy*e'p朐*Eu(qWܪrJiZZcf2XƐQ@qI@$
Z8%.@7^4(1K)(CƙҌ2E8vS5/i
+sKigU
&8%l 8s@ތo֖HT0VbGKL2OFBx<ԱNT*I"LUR
7N,8ǐ9Ux[k㚒&M6ayvRTFF3*2.:ӮY#-ޥhk&Vp)JF	(4":@ӊ\cE&i8 ʿ.Eq؂SUBs£&F=HzԤ[Üc%b!◷Ji4;23=H!xA?ßZB0NWjhov͞ 1۶*:y'3!-% PӀzr*hF>n֤Q۟Ңt!O*@sԆ&ңSV c<T$mCSF0$<ʎk/d".d!q=G>hV9p氪Q)_/T&b
tlarjo9zG[2T|ȀO\wk
;f SGCI(sf'MϟJP	.GPǚ|_%1B)?v9,6jmngx`EH t)u(%[5fߡsh~5Ir5 [:R,3mq%v<u㰢.-wj1MmhT;
;qֲ+pVx9{T t.cn\<+|{g?H	gvK";G^;Vu/r]Eow$ALfnD(?x =X5oռ*kkFI2EĆ"A$A5{kFX&i
UGobk.@( yҪ:f$0%ˀnk@v14wSWeȍ<)iIZ72bLR49^*}ǌqZcF`l&#U
-X"{E٢C<nLqP@,k*tѯ/nCjXUpďƹݾ/9SwSfIUU1KkvV9
>;ʹ$`F9gSKR(rc^>ݹZٴu@wgژXʵՒ'>Xɨt>ePJZ#+sMd]Yw u]5{&bg#ⲦzݸR<U[]7΢-b=醓^k$ a]ڪFv6FhYTtKd@K/CBn0&;vGQ_$[7>
I\l[إݟ5#1*ijp> d"9"d3?g+A}ǿn8o'VAV}I5.L!یK(H,粸p4#pĒ	Ƿ5U*ȒV2bv/ZečȩQN0GM\0?j0JvUA&ih Ͻ6UHɧ2Wf{S!ckzjB8MZ0aGAsR)8F4@Ю7.CTYJ_$UypE4Li
S ;R(Ԕ )sL_ u4\ތ2ғ>(9 u0
Lu OZBiRPR? ҔG":r4c4}JڎXe9~!Jj$(t4R(zi:+	FMSf1$w[Kۭd y>aZq})r;yc5V=gҖ"eL&M!גAڪ㊑-e꒲3 ni$rxiLfNja3b撏j(S9wPah*3ڕNi4  
64vi:sNZޠ(&
;C *Tѷ4qI
AR#sQrzd @SMzHpjeInpOSL5X]EKFWё
LdӝdT$Gkq$:U<}=jHaOJJqOCV.	^KqGR 
D<0DyJҿZnhnP^
96vVd <Rfpx4vsQ}E`OJ{RS$O"c~ }IA$zT~.OGQ !SMڐ({Q@5m Z!VT w5'H£<Ѷ<iu=h
iTwthXA֓P`#`*qD`%cJR=i
jr 4Qڊ ;Gz|+e4
jYv背EVzSnIقIY[ƭiMl_iZnqGʊ7`ߌ(
F`v
r+7eSLMI~o1  U-BKVwR·Qe}vv/\SbT d/ZjNi1	r)A9ԚdmO㞕[*)U7Z.L$pZ1˭{huzcyljc$$p׭rBqT`̠;m=0i0rsҚJ\ȹ+Uڭ`v13x?ݔ#hҴ24« yDV9sUɝE E sjL-Pȱ ߇etYn˄X7Ϸ'cuZAנ55ŭfsmp<ҹ ֯őR6EM};<!$~5&{e܌WJ}#NGNi@Ȍ
zq֬ٸkh5^ 3ZCs<5`JgYnXᕾof) X3֮))X\<f%矩V65lVYpU^sr=}FQWv+w+`^ϠSRRc5vRիi)3w|ckv0ɰ>}i	*g4rp泱[ki&P+le
q<Q^Q&#A>~nrzQJm;1oRb
YuoA4*R2
(*Go֗:^ f((VKHKqtј"Gps*y\{;6#_ƒE)N)P4O5!BiSLM2M\08MQAIKIځIKE 
~aNw<gzzSO#8QJ3L*f
=4S@=);@֐IEHH w(4:T 1IBQE"uqJ$֒wQM bi3HNMDQ3@'$Ru PxYuhW{sV[Wl+nGwM'dH<Zt%TLɧb[yTJfaE eP4FhI@( ;PKIE :P1S)0jNFI1.
7X`2*4"8MH	4
1~tޕ#S
 /zP}鴴<r=jql8?=\h"ɏo>8.pJ~ќIkȧqĆj;TeTr*:Pphdǌ~TrxZj:pOzqOp 4OAzQV"Q\_,GsI=Jqs4qRl1ϵU#KQQNh!Ai^fucH>@}Z@G.z~gHy#A n) QE R⒖&m_<5 ZZL5dS4IP3V&!-qZz4+영䚍ǥõ!lXͱQފ1)hf~bޜUj1'bO2I 6sK2̶RuG TF$HX?1zk7":HkWޝ,rG*ܥ.< lc|Lp sG!VGw+n~Ȏe NyRGky&;8I25c69>ncޝ
h$ I@A<"N{p{Qt	H[q9ߵX÷:]$rsGh/(ٻlü%2n
 Z˃=c)݂r#5\[D7άGKp`ĉ2۽*_*weG$69Hh[?Z΃+t8cآ	!G)=˦W a:KED۟N) ̓T/G?CN[ܙv:|q̮TnRz=M+3HIS5J)Jyf>Rѵg34s+o8Nykݞr}}I	؅M6w.G?qJ/V*sVHG;zҬQ30Ois2"8 
y'zΠ(А˅?tPh<IX/-%ض$#{#'ʑ:FC^ZP=FM_=%8PiuGڧ4bK \j#v"!4D0<qji~XĎk[jc{7EHr9 YON;)QbN23Qy}ȧ1i'ڵ 'b"9#pxdĪyd
{S͎iv(;H 
aD{dvvnefK1I
WxZk,C=2S~ʮ081E
jKɵC)}9R-%3%7"?/ <c.{r_JX#q$*!@ w,:Z݁pVS($(Y fZraI֔J8(\MǃL,,%"}(@r8'zRo[{6nK)<i	̞eGAS\}l>frwh=h J$G 4Si)O,1ޛޔ)VQ}oJKw&qTgcojv:i3E%- Q\Pu* O&4@G4pƑAQ!џʀO"M4mQLTIGA4=B:0ѓIr>بa=QԤlHFQ4Uc7&84Ca&iMJ( RҨɠ	`fǵ8QhM%
(
(
;ފ )J(i1ADݩ/9J>ar{SXm4@O Zz7J;hڀ҃*>;4Lv1KCVaޖjT!SLzS3Dۂ߀A	Jًu=)
Byl_H{Q
c1?J,Kb;Pz))hBQE P)J;ZZNc PzR6ғ( ni( ( sLVɁ4**쑔S1Z8R?G1 rcdI2#>ԝH'?L\I\@<ـ
p=*"dQ4vBBF1M%YwZ( P2@	C
{S`fn~Kܸ腁#yMz
v]F0	?$/
#-W_0QY"{)<1nږabYDc- qȨ̖ʥb-qDD#'Wж֣8lBɹl$TIkCŉ ?C;dʔrzzL#+{5MID(4aHBl_9LłgjAXHIaO͟bLN\-G[	YZIpNҧ$)$d}TD,ʝ֡f׽Rv,mxW!Tt޲At4˅YGR*y;BO?޴`	x͝A׭b#|}5{l'<߰qo44QlQxnqWmAW$VM
Ln٧1<`f2mdҜAӨfԐ(kBpwZ5+; UJw WSjڗ:K.\jͤbB;W=l$4I[A;My13nF#>¥6yUJA]f.HcR.xlUr>D	Uߩ.O/Ќj}iBGJrubdpy9V =~\ߘrCsOxUǴc}Ͻj֧:i&gF9w6PK?epHݹHy7pҬѣh x_vLcm>
i1v?D 4y]G92H3[u\ȁ!P=cPք9w`8y[v,@dy{
:H"KtyGkM'ZB^?4jIͱwe>]HmZßSXUr0HFw (=Je/@&L#ڗBjE`q%qM<r1?;_!3*ч_8GHBr	
MkqVM2&r9$Bަ']11w1=M0⒀mqSM<PHʓ𥢀_
P}*N1G(sOƌIOC@
$Sis ?Q@
(tNZI)Tw<sҐP4Zm<	<2EOA	ZJZCTHQފQ KgSv#R5Ji4Қojdi){	aIފ(QA w u{☼P4154h@J ZJ^PE%- 
\fѰi֎:dTcbAS
қN /Jp8s@ǏNS֙%"G]㞵X֬Znh	w[ޚ[4E;pj7ShqI%v (i(
;E 4PIK@Q@j(
('ڀ$íZI iظG֦$2dڳ$qkܶxj7Eu++{GZ2b;L
Fn])
D-%y<Q@/JOƖ'Asۚlkpsɧ܏^)'8&(X14'?bNfElv5Eڡ )3ʜӍ *@rA0 9Qt/!X5:`<Cb?Zv1yQ1)92dU q:Yeu<Ӛ|8W&V Z@jhيnqNB$/r%p)ܕ$gߊ~ޑaFO!A7J)J˃J~1b^)<
1ųLf9&ݨǎqҜ[8:RSEqd?"
N e_3~>oLR-2|4`J]wyS3+!P2}UTwSsoz]oݨ1N3'M"2`4	V*ON2)hVؔm
J{hqU-9*Sv$u't~Tw x9Rz lX[0~uUE+
֟r2wΟRE QE pA~=0=4 qQ}~@󊍎M)?'Qފ1  E())J(LIE RQ@ii)h{QEaAE
u{T`+8bT`Ҕ0*SaFFRids֐#bL2qVؠP8fǶ*2ycZi@HisiHzQI@(@hN;4 {S>U1)(%/z1@	IKI@EP~ 
ZJ(e-ҚE8jN
=T]:qJ
:E"
~iQ1)G҃E /zPiN4x2Pp:&]@9xG
L晘(4P ( ( (  Z3IK@QހE{PEPRz@i
Nq3&PA H 1FjʾUO4֓W*2H7j>NyERD96S$ZJ;Q@Qހ
(
r
jmI&spQ1=*lb8#a*mآ6*QajMSIzUacJ$wRv;>a` JvMIʓr ҋrӳQ=7b8=iz)q#KOJdD
)9!<QAb3 Fhi
fE /bkg J:(4=NQJO$|2Xˑ@`FFq'֞X|	OSh臑7 $BKݞW);uLA N QJBHךi?341$Ҙ$tӾC\u+Na"TfQފ )?
ZJ ZJZJ \E =x^֛hwbc׊PGLS	$ҭq4@
zRbiZwZLPQE QE )i( ( /j\IEi){P  84 ⒏@p>O<m/R) 攚N@!4PM!4'j)M%
?*(4 QAPSdR@ c54J(4Pw( <QR:t b :E% :LOih8)iNኍ[r-7-PhQEԢQ@Ǐn},4rBzE.(ѕ`⒦s	QAE QE RPE v( ( h9O?ڞP1ʜҕQ =:Ӳ)qӆO4RM?.sArJtj,(b
(
(
(
?<5~*i~XcDh:iM418mZyn?ȸ8
?Zi$!hsH=FNJwjc"x>H`zi98@\Epw[%+61&6[c#=iHO"zP+:Rb( Q( ?
 (Ҁ&\QK~uU~QLigfvsNS@POJPO
:zC 9Oʰs~y 4XW1(1nxLݟJQ` J}N
)ɔ(jcnhcREGSQPP
(ژqAE 
(E %-PJPpiFOZ \bNh&P)ǁGAL'4 f g4(_jHgO:N 2sߥ Q@Q@-% -Q@EQހ
C֖EPKH)2hUKS*&iXBi L&0&3Bh$)3EPh( GZ riqai恈yIށw
(
05r
9#EAAEPGjJZ pqH)RhPRiҀyBԿxTD`\E8;~Q@FhN*'JF?JAZG4W=(<TIb:=*]vECEM=E'R**CiҋmF,6K.)@@&4c@ێ<B$
5M5*nE)zґM9JzOjq5%t5
N!E;CEJ`n5hДQE1Q@Q@wJNrJ}}1\:]J*SϽF<\T{i=G?li&{w}qMiJ[h=GNP[$vھ`?'?ߠ49&11PIP撔1\PvG@E'4PIG4 =( wQ ))v6 TSAGԆKc@?XޣTXw%(=Bl;{M1S5)ط([Ax{Rq0$v5!'@\u!&=ޘP#u1M)ok):( ()h'<>TbhM(	 R<S(.=y^X)7Q&.j\7i1ޞzt+ eRPE-  QE (i
-!Q@
2MJHsN'4dO		I@i(B();PE )TdSbN)I Cў(
(E ! J(E -<0izeJy( 4Ph u%- ;4KqԘQ@)EIR} PF
%SAAڊOj^ _))hs@8 )(dqQ*PrzHqސL,+\sIh\yjQh\~isL;4 HX
,K7&:Mi>jdܗF\vOGZ 7zN0B?ZC
)xEE)A4jpnҐti&$J01/ZinqFxv}xQb0?:w4SBlc#jeX<g$%QLJH`~&
Ƕsҧ;QTtRMJ.[_$ri3 [h' )Z6YղHZە`sҔU˅>gb[Yb|jI*os!pO
i\˜Mַ6I4}O;J SVHL2@x[\{%Q8QWW {F@IWpڳO 3{;F6N7,Ao'8JO(zֵjgG6Y'wσYT$ԊvDM5[iϒ
r (	mh(H;b\v#sm/j})VRROaInqEYGX`bFlǨ3%Oq!Rmϥ9Sr9iJ$9(:Qp4ecr9ei%[T[>zT{0Gj+3Z܋xxnpݐ '=j{`PEh*Rjؤ?(*Dr:;Txjq68ohE۟zdP=j}%PcҫLrzVZ{(vFΠ8?5KCzQz?l Vejϸ9#J@?<8B=ŭ
HYDIq(^}y<ԦZܷ(kzJP!\ -ɍ6JTZ\ÕLa !+P}2HmFjN:
V4":|ILu?ZJpnwJOCӏ7/*^((
^c
L
SL
;ҊD뚖w8>e;TU(cQ3JFROuTT`QhޓcsM:քis!2ךyL1-J^sri@3
 6rhG f( -Fxf)iz(;S rK<R\S6/LQpdT)qZ<EÕO/h
IiCaf4*iT ('4
!I4_IIhRQHzP AGZ(GZ ( ;ԝih
% QE wJ ZJZC@PQ@SC8֜F(:)Xb
(
(Ɗ;Km-[''z {⣩AȨ`N4\!ƎԙLhHb斀fh<sMy\P1FsQcON;ӏ#44lf:SWޚs@~<@'. h (Us@:
Pʎy	摔ƔzpiM ;4.3FiC.rґN(NQ'>1ۇ@?ԫ̟񧓵qRRB&}LAЏ2Ai@=h[O\RGSI&S]ҏQ0,z
ÊI8[-_si{TV$
U҈>YA$m9cL)&Tƻq->]MT^1Qb6$p	nQU;g`}AE$agk	*[\};89}j[ܸrXĪʯi2đKsC[\1XN+yA# `sڪW.죶7 `SR]Ç+}>]>XaڻYilN%42Nﯥ$ZlW4ubϷJ*~_Z.{:mF*	6>i̇!#8ۊϮjw{+MmOPKe`Yu5Eb@r	jMYO+9r]ͩ.})^4}̚s)5/	<
:%OV4vL%8MJ")x<c\:r{`FOqv~&re^
>5`>n*M=h@Ca8NqN:Drg@r*x8i ;F44% y:
 
p2w[?4\Y}k8ŻTVPua%0p3Vd3ۇ	g= 2y\6nFiy]@h]ɟ ! 7dlsGhn|o %>c9]KQr	hE>n214[$Y\g 'LAY|O,})5$\F&m?
VAmm#N9'$\azSln.c|v+zf[	 G$)#;@;艡xdܤ1ӏzqMb1<O,6]/InQOl0O>)[8sHC)_kNkh'$	 >+k*fU#nӕ#MmZ'/1W򧽚|ul@zcƎo1ryX1}FBxac(8c֐~ՁZt0G\MW:4!5f-(89rw|`;TAPiIkB\H{sI֌+S8JjVw4%(%(@ii(iziIzG4^(RjM4 >1PhFӱ9#I# ╋r~Mғ84X.;<`M3<}h+4ti3Fif4Sړ<PZLhE'zp3G@( ( ( (uR( Z ( QڐҚ1@ @@


================================================================================
FILE: app/public/images/flightline-server.jpg
================================================================================

 JFIF       C 		

 $.' ",#(7),01444'9=82<.342 C			

2!!22222222222222222222222222222222222222222222222222  @"            	
    } !1AQa"q2#BR$3br	
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz        	
   w !1AQaq"2B	#3Rbr
$4%&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz   ? zZ)k9ERGj Z(aڗ QE-1(E- KE(R R  RR0PK)hRRKE-
\RRRRR)(--"&)qKF)bbbSK@7b1@Xn)qKKqKpP&( &)E.(R\P11N RQ LQ\Q@	1N.)bREaqF)1F)h"4G1OHP;1N4PqF)أ Qv1ELSF(RbLSv(CO4"2)1O"c1E8JbI}4bE 6R@\Q`6Rb	F)hV\QH
IbHh	IuVIv( 7b
bLP!))bJu LS4 RSI@	LS(N4Iv)BRbE 7Qab1H,7bIHci1N!T% 6u!Ci)ƓM%;SLSHi
ZJZd
)i- -R0@E waK(R(RR RE0
Z(PKE- ▊)QE -RKIK@E(EHZZAҝE-"R1N"b1JR❊\Qqm-;ba;R⋅SKbbbQqf)qN.)\,7S҅a\R7bmQ.F)إNaRa~)(F)أ2SF)76ъ.#F)xQhQpQn(Xn)1OC1I~(0Qv("Xf)M2X)1Rbi"E4!4SQq 4K1@XiaIEa1Iv(+!.(+qKN!aRbLSXn8RbXn(;bQu!4lCF9BQA`%%:8ъ6;i)ƒE;,&(-bBbP!(-%1i)Ԕ Hiԇ4mS1 4Nǵ;LPi
8R-
Z)iQKE Q@ERRGzZ`wPE- %/z( R ^ Qږ )h
Z( *)iRE!E1KIJ(ZE!ihR
Z(e!ih(hQK IA\Ra1KZ\Qqn)qN;(R‰R❊\QpR❊P\v1O.WboQp\S.)@O;&
I6LME<@*iNNLC"EC1E;m.wQ~1@3c~(QxbXf)1RIw␊~(ۚ.#1HEHEHE!+ڌSȦdSHia"i,aO4IN&(
!i
}&(Xn(4RbʰQv)qE1F);
ǵbQqn)1OpQv(0RN",m%8%4N4ci)Ԕ%%:EbiSI mbsEaSIC1N!\,7b1Ja?aE 2v)1@bi)sA"OACHcqF)Mn))Ԇ
4I`6
+ҊJZD)h,-KE-a)h` u@jZ(Z`Q@-%- b )hEwaޔQފ Z(aN0P4-- R))EP*JB)8TРRNP1J"R❊WBbpr7SQW\SKh3QJRK)hSҁK`7S.(R16m1LDdQ~1Ur
?)&Qoba;mh
Eb(5#- 7qtcJm椥JREb2)1Rq4GHqM4%")1N4Ӛf4N"XIq4LS(Xn)
:Rb1Jaf;Qqf(?baREaQ.!RP
8i[ZJn4S!ƑHzӱHE1
"1LR1F)+n)1O4Qqf(;RXf(;EaRbJ.b@%! &))Ԇu%
 6wzC@
=i)ƒi1N41IN! )hi)ƐM!m0M8W S Q@/z)h  
1KE`-R@X(Z)E QKE {Gza`ޖ(KEE`v
ZNaii)ECi)E"дJHQN
R):hQNN%$:QZEP)i-!9bNhZu741i~iXxHLQv)b<RmaQ~)qE(<
1Name;JpZ.@6
QDROM8GNHtyt)!r2)@4aO&ƑJX+AJmRm.Kb{Q>R<RbE!heRi51j
In*gasM5!8LT;))1RHER<Qv8\VMR⋎1F)7)!Ԙ@4)1Nb1Ea&)
L"i*2li4RdLSQN".h8RXn)1?mQ~("Xa;bqEbS%1Xm!P!RP!1E-!4P!
i)ԔiҚJ%4b1@Xn(:B)ؠW4S(
"i
 7qi
8M AKF8H%-q
){@RKIJ)Q\PE-ZF)h,^bXJZZ(XJ\RQpb+	KE.(XJZ)hRR0KIKJ㰢:RM)))mIHzp4NH4f:R.(ӳHcөQ֗KC
( fZ
j/ 
E-
ER\
Ѷ14 -8uⰀRҔ{q@jL
ZahٓRNۊ\(m.iREai1F(v҄җmCmNWښV`"jP.!aMۚHbhihN؎¥#)KDFR05iIJV4KHHHE4w'a"b<SH;1ImxqX?m.W)0sRmm(RRb()RS$n(-4&&iM%ZFmm!Id4QpHf("LRFbIE1Kv)qJQHbLRъbBbRR(n)
)hHRd4ILChRP!bE! Jv(a1Ea␊.)QqXf(?bf(LRCN" i4M"9b6Ӎ%
4i1JaE!\,A\QKP]F8p)S&1KKa1KQK.;	1KQEa1KF)@4\, RR	\R\Qp.
)h b0QKK.QK\PKޗP+	ޖ(\R‰bbZ(Q@ERi-!MRKIJ)pE!h)8u2R晚pcQISE8TRD5pe<xRcLv
(RW<RM8x\Q
"3Bw&(Rj+zi9T
$Zv&9Kai*R
3զC@MI(/ZMQpZ@0LSȣo\
HVm BVT+.+M5#
fMR!M>iSXo;Ը4+byL3L""G%B*LfUɱ)f[ivԻhG0HvQ֎aTi1E6VF4	O"A5h͌4ozyS%41NRb1E1E?R0bHE.)أAJ.1@)\\\,6~)0SȤ;Hi;1IRbm\\xQ.;&)QW.)ؤ(Xn)SF=\,3bJw&)!>bqN!\,7<qEH"JW"SRbLR(RRbW-8Rv)qEqIv)qNScwE(a1Q)qF)XLQpR+
.)q@Xn)iqKbR RP
)qF)F)iqEqK\Ra.(P
(R)hX)hťc/zJQR48RE:C(4KH<RE8Re!E8
A֝J$H)jnZC;$E8RV 
<
 T4f)isx1*,rSrJ)w0N
+a' B{z0y)1E`TC ԁ(wSFsQM4$^)ijAjQ<
^j&
PԠq.#FRi.`RHyFE&	)1O\6HMi@V)2\lDf4~Uh3O=id1L")U\4*RiV"#
ѶEӀ6R5=ih+@ʹ!M12"i)Jn3RbMcEj3RiU"M4
7W!(ZMDahʰ)ynis)(KM=i9lGB
?M2l7bPbqNIiiIb}&($f)1O"ӸXabJ7Z
 2Z)41KLPRb1@
өJE 4M?!RSI.+&*B)1J#"!#6m)(I9G&)q؏TȠ~)1E*\MU!AuR?H
;4p@▝ ?m&.Ip  &)qGzZbRpQwQ.1N.(3\|x?bÔf(?mRSF),3bLQpRQqX(\v
){QEKIKJaiE%-+Å- RҹV)GJLRMӅ4SlJpE)ԝ)pjn_(M+NZ@)EMʱ "94 ԶZB;(&b2{
 (iYڔDAFg=J#	I.)qr);
 S
<RJ-!٥MڐF(RJ֍
x6Ȧa1LjsRL5FMIcU60i5h͌"KLO9HѶ4qXSMHri1iaiiM8-HEO֍< HV 
	6ъ^i9qXB)fiHr)T"H4KFھdCd845)hsFVmLMJ)gҪXf)sN&i64ۊijV4M oiRS i)SXnQ.+
QWSqO&(4bE!+
4O"bcNi9bS6)1Ea~(K|x.)hK9FmRm\|xI6xJVs))1RbRB,QnivR!(M<rmMA1JBsm!Z&Eb,RRG0H1Ie(B
S+K9KIprpLRS&)h) -+KSAP4bK֔P) QNmQN.(;@.)iؠJii@pb]7iii\mm?mpͼ6ъwbmMjMF*MqXbLP!(.(RъWKE-+8RRԶRBӀRi
H)P٢C- 49ROPi "iU*e_j#H%8G%JT9*d+H"XӶcG/ّ*cLjPs\9l4b٪(i~+H͊nsTI ❑4E1󚓊oӚjBqN4ҊƐJ `R(J\sK^h.H{SM+iI=*cқ&C" mqM"0#(ڝF3ڎarM"HAbeK*+LE&|9)RI!.E~f`Nǵ0j&Hoz32hI#ޗpRi64 6qښx4\-a6
k(81
=[h ҅4M')[$qR.g&qOۊB\Ĩ>ԇ~1K|i9b=i9S"Fړx6Ѷab4\dRb"E>ar"jB3I1.$x"F9ELTi6[hKڗmE.6TE66>Bjmyd;i1V|{Reml~W*^ХH~]'S?fVIV0,A6jM+&ڱO.0Ji6U@p Fʛi4]M!4FaQHE8M;

4Ԙdb)fnre;\,h8S.t{S捴n3FOcphX@Z\Z;ibR@ iؤhN!
1@
v)E  ;b@:)TRci)h@ƒh;
\Oji?b\IybȤ␊ mQWv(MHm.)إ&Hf)qN.*n4ii97SJQ @ZxZ"AVBBrb"U3OD?jS62$D=cqe)F*P$G9)g)1".ʱ҄+!5;`
F4Z)8MӱG8r9 QJhLfi{@c;Ҋ~Kjg&v]{1Rv
.^~LQKj0hA
'_)fL)M<%i󋐎~)qG0r"gK#4s d;  T]!LSSB)f*M&)CT@8Ґ vmO1\!a@+.) ЎMD98⧘Qw04*fG&#´)	Ĉ/8g8P3)l"I>z[j)ћLizS6+qBQB-jm*y Fڱe=jM>
zi6Ս
Acm&RBMgˤ![ice'OB6U./ڎqrQtyTVI4y4Ñ<)|Jph5M_/wȧy>ХH_*h}j]B"CWFK2)y4MZ"hl\y_J<*SI5
B*\g4)i)4ȊI-MV)ME搥L,MKU(ϭ3؞dqHZ>V'$)4iKdIH\SKSQdNi&MW).h)A!
ip)jp;JN3>p_j.4;c4T)!ivӶӂҹV#NS~s(RȧxQKj$;hS`R`P$[hRIhf(j1NⰔEiA9`RLLA1GZ( HE:faJ4mr)D6Ѷj${hLmCj;hRi)v)ivlqJiM9S֦$0-<-JRh0!Y.k'3eLc&	SlJ6TFSRd
(e)*sS )1)xbl ZWRY(3yZnT#s5cˠW5TDi*S^:Tʻ(}*ߓNO!P!\fʤʂ:pyTlѲeV|<GBKArQա/=rPoʤʢ:_.a:pwg!CGfCRKd[i
S IhT
VjiOZU颸LҔ=}{4AbҥaM)WIqSmjv3uS>){@T	4j zQG["`UjnJlT҅~@=WD{&T+isگl>YRǚ4MVgy~SL~ܟcb(4W4{"ڔGW|jO&+بc=ߒh=)~Ԟ_5{-ϥ=G(ր?/j?df&+Qfdgy~ԞQ/GG3|GZbڝj={,AJ-P[RҗFXڗէ{QJ=b#ڗP(lNE/"+hiZ&.TWيB9QM;GzK!"AK Q;uAuZVʴQi
&k=+EFFOY;E4fcޘdoZAKiUZicV7ldM2T44KL曺B]AKni	$(
[ޘ\PA&O0-L-N+I*'$Rmʅi9h2EKm GLT)6P3'&4i٧a&8SbKKy(JRf
& Zv)\bT4
p\im;"I"= (*4
xZLOR)64F*a.+(5)Jf=K
idP  umȧ{DQOd4SR%mԛA.R<RѶd.V3b`)i6QbQqr/bsJp
HPE43Yh֟Pӂ5
$0.{S{TRJ#E<j8 }j=r"V_H:cu"5"V\ *D+7QHTjp*Eج]SX H*UU|j7T{1ڤEY *DRTsOXϕ=buQ 	NVDT.bj<WDBF()y&a'^ӄ~{QhS{SW<]>хPAN
GK|j>oe.\*y4j]p)4y5s`G;rGVR죜\O+ڔEV
6Qo/ڗoX)M)9ØEqK*H>e>VIӵ5;EMH8=Gz]R`AqEv O\o+IdGQ@?tPνgIϩ-FZWkn<׌rakE)rϦ3^7q	mhۣFEorrKϺy^iX,h1I~LV22EV TyOp{/Fz1֐T	sNxe0P)3ҟ0XiAN{	<O9V)zQp*SKڊO/֟=)<GTfIGõiy4/j=QZ^O/I`8@iO_{F;"3hy|SL^dٚ0f[
QfLl}+M`(zPv"35{Ry#җcFh=i~ybjÕ4kZ&G;adR0JQn1Ү'^LwEC'V)zU%"\W84}T0\ҴTu yJ*#sQZ*3x"
=)1=3/hQmQQM0~KZi#qU˟Za5h$c,K,EBWJ֊Le#]TMtԛ!QZQc*}FÚIAe*{"{>1ҚAHȄM+Sm4ݵZZiZm&j.̀ғmOe.d>VWHV=l	B+mX6
jDѲFN++V66qXeYI.VvmbIUXˤRiP#)M+Rit`QK\VB
vi1KHb杚m(cQZVɃԂAU(qEO=) *)MU8RSeAR 
TjE|&iF;ԁJӕMIGS|)Cf6<.iiTFytTҡ@AVJ<TiBJ ={T
(>Wg4{D?d!
/jٍRj)yF57($GL*_4ҏn3,hh)v'ؤ҈J"
S*l5kɥ
KZ)j_(\P#
3ҜJ=EVnfcR,ԫXf
Ǟ"04PK^{֒*al*{*7(8皴VT+Unki>/S*⟷ڱslB"8%L2=cBS%̈'()]DtJ1N⋲f*MQMKN).fGeI@\̏f(#ڥM(sbҬ}s	E@5s>A4VK.a{BMJ]U@,p*k|jW2\A'+or:SyI> m2 PŚ]uY?7v)'U* 
l0q[z:	?tHn?ÏEc_CgO9Y!};UN(iu)?rW։nnOvk4o SVۙڷ;FlpƫYj	qvuvLR&!e UtФc9AӊCϜ*^_:'#(+>O2y!qQSWF4wv]TmoȄ9l_<^JKOG/[>$}g }+yQ7}\1Y^
 QP[ƓIRc*aOk;)kCO=RS}' LVuLYT^scUuX|A;7BXc]pL{5է;_/d15Gn#7
r|8)\F@?V֟N']B퓒rI_fʼJpگ}N!Oh}|KX ɫX֋{RI;seA8ASBL|c<I
vO&}6;1HcCjl!`;KInj6O0SjtI{R`{T&O֣2}8VuMޢ?zkJ8;_iqL7
+<MF1[k@oZb.٨(޵Ad7֚fcj"R|jL*CZBIIcz$G)iYddސԛ8j'ڲ,R*](B4Sp){FCm5)`)>QsIRE΅+M#Hd0G+t80L4r1{D)n>oZ~͋!R~ܵj=lbw47!ϩG>*dB=i*.cH`RT.v7)E74ԅ+0Bb	jB֗+tpiBO.)ZB[ޚsO^
@PAi0ڔHT%0iqKXN!Z1J!S.)\vJ(P(-8c4
v*JC(ZiSE<j5 5 5fD*eZ6*daYI"UZW4§B
c)31C1b)qekȆzP(_jjBq }*U}
J04ھ[5RV<V#`ffq(1(v|5*2csFBzR(=kDdқ*[D|-}k%LՓXaccOҶ _JVbОﱟJKJ^&ϥ8Zڷ~j>=)}h~&(ja=SҗuRԠfX3VX*{Vr8*R\a*p@;|Jd{Ă:p@:r)rbi-Rf)iTd+"F}
/ƫHZw
C(P;}jgP)wD4%1NT {n]3NP4a},$PdwtqEՐzԋ" HNޕ!L	ڳC=֧2j	֜&5/Խ5|Kd'ؚZ[kБ.4?kqGڟKaܺaPzTB8dUU=MV)SsDQJ8"돆T㹞8,`ںO4֙翵mNZ{?3OlDybmplz|7[0\y$Q=7EVb(<(  cK͝Zyi]KI]dI8UŉAYpUx<P/1Ma'-L}_-=ڃҲb0լ5F:Z&`+hd/qn̓qIX8Ρ!Z!CM.OV sޏjl=ޓxO(5kl_jo$ḣRGofep9*M{ժD:苦}izO-Sz֊4CUȦ5Ϡ\vQܪ;#/ϵEZBj>MjϖlѴU!ґ[a';ҏ,{DOe_(
6VLt,j.IT7UKSFRj6b*"AdoziM=EtKѳޠ}M&N\˱>=)Ң=79EΉ=4S8SM/IUr0i_KIv%ȈҘR7 SH_jaSVSJ*S4QEiS+yFʫ4}(F=*b>~
h
OaLW+IGN.hV6
6J,̈<McړX9
JiCV6ښPasm5`&aE
!SS SfWi6A4YyfS>ҔvDR
e7a.ȊiҦ)M1"i"1cPNfz*(k`4,\e=aPSaV{Rh~ɔg>gaڏh2)qS-I9r2*\SJ#4s!SyF!l )
Pj[4HpQR* 5*v4E"9l)EqP"+)]FȰ3REVI	<ԢJͦjb =MB'jlUJLӕI*a8hCҞ)IOƥȥ1)ISZpTF}Dfy&cڗfW2Z4R~٬ԍbIe^Q12QQFOZxOQXd:Ru/D^7~ҞvS1ZGsB¡<EfAL'h{U}V$eoLw
 Zcxh۳p]{
~D +{S>[gyJ&j-QxǫRdU*U)m
TLyDmJ*`4A#1OtUU5R 1YڝyDi#S iJ9@!>jQM<GVyb
;I4?qs1=iZ&|RXc1PzR0ڟSVǫ/)hzځԟΚm	$b8w&EM7T"   =W.iAHoжc~5" z
|܈iÿVQO-r
T$[6>.`!K
iV97v4'q!1HJ-ed+Wh$eo"SށI)<N~Jyb-5W7+&R6!24VV&w3Y\h 
j_JWb9ao<[R,Dǹb{>ˎSANUb]89m)<j
{S~ʝVĺQ`HK-n5S~̾^پ(6cN`*:QqOeq/gAګ~9%(oOAHaT5+y0J>ߕ7Tbf3"2Wҥ(hBd!횳qG*r)oz>oZb,S(_ZVQ5`ғm_Y ֧)
OaM69ZiZj/֚mNG4ޟ%<aQV(J2]g؀i_j})W)+i>cp޾E\ U"z
M)\U61VҚdj4޴yDwҙi6JS+J\zQtcL` 9]d@Bڗbs 41W}AGE5*AnķSKjqnVB$f00>ptQ"w4ֳ a'{f9.уB
GaNBzbyI6捕TwvarmjAԊ4^s eҴݾڨ*&)sl+M;GSY'RcQ^3`,ofz=fH0bLKڏسl̞gV/'&ڠ,7;iJGAYnE0J(,-4}jM*i{AW旚QJǝ\ORjO(RϥK-EVXR ֳl)P=&SwSNil[\xك],6qԡ5dDҔ¾\SEq=h@ԶRO&-M[LՈұFҋ(6=EJDZB:c,_ ~юtuPslҥ{clOJxdy[kQڏ9O+d{l;
C?6W,ٟJmGzSpޔm6>h"EA֟=oS=iS{:EJB-Q2z|MQu"IESJ 5^=Y7ԟlҫ=Es̘EM71zS>)`'9}#5<
CJoPr"?ݱK
QD0@H`ӀTGۗB҉'֬*ߙl1YJs5QPiޞ4j $S J)<Zx皫ՆityQP^bG8ZcҮ	c4y]osG`E0<CI=G}Q%͒ϥ8#zT_QnƩSG;'ڗoZ\Hè̇9uavJS4^cՍ({daqe3ICTޟ4PD N_ZAOO2+nzS7V v<BaT.)>욻 cE/l/hC4	<j
яVח@G}?Tvm=<3+H^q_[?$vX[x^x+N+ڤ/+r@c:U]zªuQNXQ"R*+F:{Pfojnr&S݌\0D819؜gan0k$}&+{
{ lk=VjJ2]?35>niԟZN2V}Eg63ř[Lڿ@)̟lb=8Xղ3j$A?aG	GQ}.>ƴs֟;yh?:f4Ͱ^(6&F/ִF
Ճ* k;d<E}1
r{5BmZ,7S7A|ʣ<7´K"+VR:Tgn![tr)F[\i.L|!-Z6w|+7F>@kzD]ppK <~-ٜjNoCh@Y֒N`h3 xw6WxCڌ3Y}{ǘŶːCu/O=dAH@5}4`CSI9>D uaHu%\m.i0k=,tFڋW4<Q[Te!O"u
QM$xV!՘jMp$~J=3Hug
?ho4Ȃ;Pc=e#\ΔƸNN8_n\N]qr)>=̍5K7l+IK_D:~T֚oz=HG5 d$9fMdo4garZrh>#`SֳSzΔ'@i{tW$]O0CPiqӼ'IbRqoJ#wS③2Jasj٣ QnݩS7,{¢yOfj* v'i}h]wZ28k(*&A4WVw>kevK/c#ajbz!?WfQCIϙTICS/KZ%O_KޗaTcqoz޵*N]Nctuˢ¿*AB?~U?Z솰}y2cG=vN a}f]XHug4OjQ{Wi5}}O'إ㆙'qNcW[UGaG4rLoJQC]AaG5Gwt/aL1J|-3?ݣ8W@b0iHVc8Qkk4!Z={R}ծb4bLAIAZ!M1w`bTPie4R8OjxSUҊpO,Z؃ޘ/@NjQO=0ڥ~{PoIT
+'lYq)XfKs>X=)VɏS?>fdYR7ƔNGzN2cSܴT""NL5(XKz͏P֧]YWkT0KƤަN)XJaUfkzpt4W}Z}nޗhjr֞5=p{[AFS=KHXJJcH;
.*A0nUInf뷱&I&a*A8<~Uj3udAJY(=Nr"=
̃8\ S}:>ȾA֦֞SE<Y#Kʄkn۰_bSMJ^֪Ag5h4֏~rElR7ORM<D(.%p-T}P vq\{eT]c8X75LëԪ:?fԻ)G";zxU"ˎ?<\(k'h?&V>+5`^ _(
T(,_=MH,=iPuW#7֝1ޫAGIO{q-}Oj>ȕSՍlcwG/YOpZ;~T{XoҒݖ'ж OAS	UuL  O1 m[vW18i4[QBwXSJ!TsӅzҴ{!Z_AE.X
z
o¡6dΗ&: ~UOQikq1'
D]:~5)'tb݂uq4m4%A]'Ulf56
MWsh1q׽mtdUZ=b]l:#cju.G3#z#X VO.C&> ֭#ZDHMM4W,'iO|o5t\{\V>?Οb(UU.|Gxm+͍F7=AcR_y3ZP-ݩC
1HTֵumNwSK%0b=fn4՛ 'Ҷl|9j+mog rpK!=JU[pRf:@k?Sך݃vlJKb< 9>+Q<'].OBiғj'Ty՘PE_3'f4T8_"?h}oVBe,E%_  |џtɀ+7LW$,)hiKh**>*]J8
9Dtf= :qX|Q׷m­7ξn l bSS?7]Ui1	JPnGWekZq ,~1y;RT'@"{%a$c妱m6rO4MX ffEH
P&໊S5ٝ8?֫gMo<q=$/v CYC'N?ޛ ^{MEP^G:ʇ©k 0O[Nřʛoݑ|B#Գ3QYZɬ,{aXt鞼ʽvOhm6>WUsi) "OyXRlCd>.L!@_Z>ZҒ_#'xOUD$~ujDDvrJA( 8]'p^/ʶB{yJm܏i|B#%Q]Ż.#8+D#t|һ 
bubԼ2dl_ֲbiBԪT9hB:c,.>[|i7ߖx߈ Lfnˀ XT*=2@m,Th0ܺ$?Pb}܌J+&Vz*'!f_k1̈́d=~ZVoo
}Pp*_T<dTq-\giWg'ʗ*.)i kߐ*>TvrC(O=+*WB9/hy4ߥ_>!砎`h?!=>l=OIʏRKQ0khZ!4 e}@fnWQ0̃*r>G.
t:=?i{Gp@bFjAB: 32 tRy+;iGI̧7E5_]'h~T3cUzX}zb"ϡ٩<}z"Q fHe_Z}dCS^_֫G%*=R
zM~_хRO[30g&j39bŬ#Yw)qVSfUaGHA'Ԥu꽝>}bDD0Ky:Xv!ը\`zHv xS{>l=!
j+M%).iw p,S{{n=MLΟHs ( ަo~h QeG2{?ݧg?[o֎`׹>7TTh?E^]Ɉ>Z~OAsK0z)?QM_c,Y}j_EIO
.y?Zn`?)⋅ـ-Oz@Xt4ܞMaðczO{҆cޞ%ԤOVDN}jE{FSӅKS%}XtoJ>0lc T%Q>`_JCnt5y8iGHa'B>x5L;O-c]	;^٭{2.a0BykERN	aM.+DG٩f4sE jHRF'*DICO	ZQر<z^"(R1{RFH4Ufpjs9ZjƏE;:zS=9-õL%mOQRmWxu2=*u3ֈ~P*}?`&5*p!'s&PEtW3Vp˚yQ46sbf͗x"Eb: os*G@|EK7ԥFbo)ifC֪ޮ?QBSB #n\c}N?G4<GR)8??*nTʫO>.ǩ wg]OM]DoJ~~(~/{D)GA*=n ^ifM:uu[YG֥[~l;ő
*NpOw5:~Ԃt=fQPUuخ4M<iq
$T@?K>-qe_Μ!^TާEO;]~`akl}i6g_AtT.~釸[n첷G?>u;K銐Gq`*OWoʜ4=[濤.h#p?:D?Zi/iL?~k.pB"9 YL4u~!0O?{}6ioҬ&e)E?*yuvB-$UEgJt7_g z%ӊ%G]_l KM?{iOѪu:"&67F44+|ˈ|5iI P2:VaΗrFV65Lg*CZ]4tiO{{v48OjKg>ƞ5="9h[x%W"l|Pe.WMFL ǾjaLGUmW??^q?` wS0 V5 %Ǯ
L#ӮC#5vH
#a/N\BO*&`m=rUdmE7 yGTG*?\Bi$ZWI{ȴ3Ru3"O֚5?1eP0Ľd_nƇ߶GqLS}Gi&2~T4Xϫ[P}}(}FO -W@[/X,I_16>ZP2шYXx!ڬ	هGݚ:r.+kΒY9E\f+EF
 \MѩTuҲ[q<{rS[0TR[E
vڔʎMQbڼv[F=N沇kA|ZNwf?i#[־Қ1>gB&_G=b% VciSHώnt\
ʎ?ZBZ}>'r>d?
1 ^?:V%>a F3ק 4 "}^__huͪ6xS5K6 Q=e?>[kj[Ec -GMKQ՗rsێO)Y󨿱#G4c֟Uuΐv\Sޓ{f|չ~bZs 4QT0-Tm%>YL:76d/y)fV1AnJڬdGIȤڌ4Ѭʽ\´Fd#J4X?~4}n"[֛kDh*x R{s#iǽ/ZJ5̈́1SS]Fֳ?Қu߰B?>[]H0)izfC <G#?
>s}S~vz6@CS
=SLן?l9ߝ'{pt/
su =?i؟(}Y%3̭o~ηs"i@e猤4ju<1GMO濕? ͛OMu9g/_ʏ KQTG/Nq2K]1yʛYʏ 94 -ɮ>?俕!O俕YB9tZ3?Tf_Gtr$xC]gه6U}`>1\zL^')\zQ\]Q?*oyʟb09o"ȸ_?*o~T64]O!_ʏlrdSt:rbP9oG_ںsnݦ{f-5(+D g
{Pkӆ~OeG/jnpy}iY@[iԞK=gS=Vؘgyw3 i| j |4gMO<ٿh$ΏZ]AO_a fS9;21Iȳyʗs3K!WiE?,QI?iD.BnP-MGVSZN2Pٖ0Fڗ] NuG%>ƞ֯iݟhPo.L߁@EHQh-=3byw?(9:D#S+[2

ʀZ`WΜ%벡}TQH.\tQWDܧ	-R dUn
?*xclOl;
pVn]hy)cR!_;58^z#صʺƝ94n4nn/j}r!违8ZH?*Lz 
i#vr\XQR=Aj.OMpziwb	?ZaT^dZ?KC/%Zvt֣:{! <[ƎvbW6֘bqUCd MH,9{kn>S0 Pb~+TYߝb?/m1`z7͏8; Z>kܟΏo³1| ߎ?L~K1 BgG#ي[VOZM)DvDI֋;2ި?JǴC{lGJ>?CY=J mlqN?}
7B(YIG6o
o-hȃRc@'c`:Z:w?~"DV]"p R;_T?v?=-
R!˞4a jo/Pn(  *\ Wؔ MH
A jCiqn8m&9eczԞCNiCVȜwb+{gӵ巓,;:괫}.
%\|~j>vΛmDĝA0Z<⡠\e: A^L%WG 5w]OQNz*E Ǹo.vm5iK5A(d2G~=Ki_/gmY1{&ɼ#jҸ? %ķԾLQ'/(žY*ke6d5tG]7RqF8h Z 
0?s're^]ezO3ǹ4 	\Zo ʄS zȣ` ^&7#K
0ϻmyE/lz/аԞ#U#,p>(c1袴&I'Y Vt°=*1FWb!$cG$
~\J^KJsF$d@jik
=/W_ x39SO~imO4!C\& V?*Q['S[/L)7 +6Q3Ƌl:dʯyrcO%IRCOٖ3

L*%';'Ԭ{Yw)hץG$D}q ~G Ƌ
T2M pM. /_C1
3 b{UzΚljwdzex%w!Vc
X3+;W]3W<.OVdr*?ͨOտ1=MW-,-gP.<ⒻvBDS`
N䟓'
>\2 <U4;*//\L?VZJ ]l6S ,jZ< 6uئ%~3J$oƭZO6?4ȯߝ8HO| 砣Ϗ¨/01?ΝOPnc)?_ҝصRyKܚoc>I1tߴi>c֐ݦ}/CM7qtӰjK H|T_jpʋH]; }/CR}.ӿYoQ?:aj|Agܜ g^ C'#S&/4L:C:tt-{b v3?ZiӰ^]&h i<*'+˹g_)u34rɘ{*='=ON¼|ғpZC?uWrїՅ'?*>-4o4}ER)<vBoښn
U)<z
-CzC-!M3e'O@)fJO2yw,_ڐdO=^OCL-'LidʘdozfoSM2Zi[֘eSP)J	Ԝ ަj
5'[֫=Ozb,Zn_3ޛ{2Gixc%4EN?-GRުh>vfЃ֞T~isVe$^ʏAT|@ҰM'#<HW4JQ|Nù?<J?PVP~LF?ԴZb*A1+;OΞ"#T6r?otZba{Rg ~7ҦJ&^5Ra^❘L1fت iΏ?(v摳0>?^)E>gbEiDƦ`;y#.rZGisH*Qui~?*y>XI{ΗzԢw4>X+y:
(*Cqwhb YhuaHn!~ DWf}@4hPh/?<$
S7-GLi#|?j3N?Qa<?h>DǢnGB-R$Ǡ&V
qens+,WXU/Ej2wc9k77"2[SOsEV[v?*p߶OP~rDwGZ/i) uUߡ}1GPܻ!mc+`O֤%QhNY j0r2H߭;ˈwoΩ}z~>/woΝ /?/1RLgΜ$yftnA!{j	b_h d hu^>|?8O/OM/sK]>ߞs ?:O
.IvٹN U:_3zIѻӬI.*01
7Y|?jOGI=ZuckV?fyIˆb;8WJutܻ3e5vڭxI}Gl_rapuqnUfX,`asA'w5~x >zc|1NX]]goWw1y}~smH0RGSҭ-Ҳwp7pE{G{I&Z'%evftufVcho\8ϔ;d>ݫZxBj:T)<mĩMݵ/:H ֿ˷l9h9jzfqH,GjnQaL{~~V[_%5Bx?%+7Жv
G rz;P&#rVmJv˽!f ׫HÐЏy'W2FOEi
ҋ~&2Oj~zCuf|[+S )B\]O;Z3_vϨٯkAÚ♆z)Urg^ͿkDuhOkvzO75d횬Զ-FuXO)kjO;
(Ϊߔ4Ӫ/sy>+7 ڃ  <>}) {'Q?jOdVcoAiGk&bjjF1lH1I '?54]Si 'w]cWgk2
__ҏZ(u%Q)[XB$\DtA
M??9]P0OZxSRe{l7EC^T\zMs-Nw3j1<r[7Ԛ$`7#4l2p}zW>Jmʳ?Wlut%uyp*1mrJYAV,ʚFݔ,Z1Bud z&ҼԦVᶋ FKD-,V+)a+E?Fg2m 1h#]^'8#MF $Q7؎A?¹i_c>ڳuE8&6
XǭsY^K{hawfzr>g'=)>=GKٛ_h}bzOA͟ZCp+_֛OAͣ8ǭbz}z{3kϤc}z}z䐹Z<Xz(r#gǭc}}GI?:|"6xo/GۗAȍ?<rGۇOBFǟHfo_֓֟$ozC7cz)H\3{#R}z|Tk'=k'S~=y!r\=i<zhpBFސYmzr[3OG'Fi1r[e}R}i1rWozhQʍo?ޚgz)l\,c0Ho>F+#THgv)
اdjj7bB#f՚n4Z9374YzMЧcKgM7#֟#fﴏZi&ozi޳7h<z3Mǽ>F"e&zizPO(ֱ4s_3O(?ެQ+z_9hO( hަoSK6( j[ϴ ihu8] Xcz7ۏq
֗y4ۛo?i~Kt?n﷟?:?`GݛzR hX!zpaG?3tj_x7Px"QX'?*K> ̍1">DcX۩wQx5Ơ=M8j
zXG"FWҞ58cXa.꟫k#sYE=y_V3sdQǱ?0zӷhv֧G̞.]}Z5;'Vcy R
S8z]}^ljڍZF>Ļ ڍ(AY;KC}b]́K/cKXs_ZZ_iɬ;k
ZjSL{βwѾ>>޴
NoZKQ!~]oIEr(({s[JcQ/+ͣG}b]_)izhޜ%#~]<I6ȒgcJяTicY# ѥ指o W2XvoCý;N|}VQ|u5ce^]́ҢAwOg͌f/5줹sGV7I.d%C AMaaf"X(w'R MԹ jT߷.54UU Va78\ qtb*ZɛF¿35NMNb)VCݳIaR75 gNʲb V܂˴{*j-}u+aH'Z0e|ngᵏ	_@kZnmT+ϽU:d	| ƴXX.oS[Fzp$\zTps{	W}+)ɪ+IʟPf
h@{{<IEl{{Sy5ܜ8{Z0F=I=:E}mfq5w,rfcjT Fܤzjw/A5p*ײ3x6?5noβy
NShs -[t ѿ:y{7 F>?oγ|<ah}oߝ'&~u1K.y/oΏK = 4ya{iw4>/G~uZ~v'>~t}Qmoqޏ4+hSg7 |u{d柲a{W[Q3V`'5sUVAE!>٪Ms* eiC# _𲰺p	䌒ETiH89InkǪ:đR=L8b	ҬNC(xxҔܡd,=lixþjS4s0䎴;n}߶KKj)``2UIu<
Zf$^7r |ɿj`'X OG{Yw.ٿi>7Q.}E!cG`^l4߶T~=eܹٿhl5S4?g\l4mƩ4q]˟mƏKTM{r%l5SqGa{Yw.}_>/RFj={rel5Ow8ret5L&={˹w x}_{(k.߷KIj7Q=~'>/i	^]˿nԟnO4G{Yw.OR}OU<M?e]l4}_3Ga{Yw.}_>/i3G`]lޣzf4{˹{zzf4{(k.߷IGdYeeܽm֩f4{Ƚ=>G4feeܻפk,L={˹x޽7T?ed^kR}y=d^cS~ji7=CȽHnR&4{8tݚOi2hqk"00g޴$)CP]仅.PROqE(qP`9P\p*VɷGPE(G(\KK
j81Qd;O4Pd>j=֗EAv?=Kg_
G =E=I* =i@ ڢKzrR=h8Xw4fzPG+
1`/i{QڕMh+v)RѠj<>iwy+qۍE\Ұ\w.4gދFh\}`KVwiw9ɷQaܛu`Q9BuC]Xw%KKVwQ.yqT綞w8xTF8@bCg~;9u(d1I1VZ|?=UI호BH=]dBAk)A0d#5BȮѸ8gtUR> *HBsE:N;Au[V3$[)42HQz?rBDƣP#G+uA}v6!:3z Oκ,Yŧo D<
ma.+-E?֋J !'n[NoɣQ
}p`c|/zB}cЪ	߹$XZ2iu
RB9r*Zkbܕmlg*Z"SnGƒGS'Ե(LMɨԝ^P :{UB=x4cuZE1cKpKn`z(i?eN}ObhOq lA檦nm5Is&|+UE%KY]r*n%qX nd ?ڳh؆Cӄ2ǟzKEO+A,3U!8VCCnl#ާ8dÌR*lzsZK,rA*1VG V%LMs4<q|zq֢QAj-4m.叾ilW8Pm6\ng#ڋ5ِHXOBqZ&nnܓT'І⺒o>o稨EuDHEﰻwAh&rM=ԅ7n4M5V&SFfMrMnFhIвjԙa\/3R^h[\̀,>YհAԉ[nQ ^2iVB*d=/n:Or\_AԆd|Ux}3G*{-EՌ'>:U
'R79_$Z(|Gt9j3o>sN0Jf:Ld:̛!،*̒!i=k64o;45k@1ZO7dI\硤.qҙ4` 0Ѿ&MQލ+o>除wnFh\u&*<f7QTy;7RdS2hFj<ѓErMfqf3Eq٠fi	q)4M&i,LsI,+i3M&h\~i3Zni2iWzLsI,O4X.8LsIv&i2ia\y444X.;4a\\f44X.V(&W֗"'&+Kbfw֗+hPKёKHh754gFhA4d3J(J>t>E6PJ 41n@fa~M.j0)(>M޸!Znh 3Mq٥avisM4X.;44;4њFi)3FiQPU/ S<^LcQh?&5qO[=Q
,q.M.M*FO3R	j]}HiFqSuQSElQqY 8|uժ/vɤmA GR))rD63ɫU-ʩC]j_8ns1S&>+YN]#J=}^$#c֪26~MzN`qQǡ9F6H.n=_孫O9'+e%}(*@&\i[C>Uk񩑕NjܴC%ep@=Ȩlי-
(xlcOƳΡ#60OZ/?'NI\j[8`[~&У' z[+#[ \ԨnInX  vʞVc)prI*&D:N8Z	 -Rkp4ִ;*,I8#)hiLjȺ%p~b=,g!cT-^c<ޚ<S횧j9C=
a'4Ͻs֤W`zQ<P7g&2w
XK=Z<@BT8&h4_ȿ^E0j6phl`x4Rj"iϘ'(959:v;d9X:6bLPuKv LW4:i$[7981ީ^

ߊe~
g75P&Gu59	}1V,zT3 1hDU}MXdH?$8scfXF^yv8Gr)(ʱqAۉ*7m'}	4$z#cQ}c砩Qcm"m߭m土JQJ=7F(ȩLJOo5EGjM=ސ='!iB3jz&>t9SB.1ՉiI∲wDvf 	*YG QLL?z,?tWEY{eSgQp ʺ, =K W r1n:p]mNSc98Tu-:k]CKoy_e=x?ZXHskCzk:39
YK~<R Oo`+K$okY^:̏o)IqXփq~ٚQe5F֭dkUYS*{TS}T-~%I8wbzrLiTD4kl|ABVm'Cd\H}?Ia]"9tR+M8Yp$-TU222C@6ԫuݟҗ*Ў'iO.iցXeƃpc?0 3N4RdwNVӰ A]M/irGJ4Q H#!ݹ0cS
0iۈGdғGI >P &ixf4@ϽњJNRh43N.h74f 4f&i	&4gL!sA4 .i3HM&hLњCցh&sI`CF
8)jM,7P
:}()iHP0$PS)Ӄ 6S'B4#w"ӶƂAZ0h@ց:HRsK-.isKCPi\CZh4fvisMf4敂Kfh3M- ;4f3J?4f.3H>wMێ?:B4;i9&hߍ-74fn\tpi?1h=WiO n*1΂w=%zPTg#BGH k?gL;r{R~>aF*?tǐԍ)^>S>Gh)BOS/O?JgixtjgiG44mZI$Njkb::{SYb\;Ui'㊄r9'#M 2
/Ѳ=,Mi|ME;joTbp:PdV<MFr	T+zS~UEoy94֌vnh}&aW!$U\BgޣhsL	AST|P۱i|;;(:hb~yXw,$jwåTqKJ.CsѪ2S$p$@4QIޞ5
J@;MCr^*ug=܎OZ"CjO0}eHsH
JzFqԓRA[&	NhLq* =.@]8,ǰ'=)vK408qй#޳'uUh45Kɹtݷ3B[D7VPs\a"<)U3 S+nQ؎rF;M2\4^9(qZNǙHǥ)E2L⫵,6\w9(nDp﵄ONiE
vsZSP,ힵ\fwQ
23.Њ	`}E^]96Q()"6FH2pW"	򬛽i6qdW+3Hd0UfU u]\UoЛ[fif>7;>9 ,B䃞sYM#q?.ճ@`^l\G49<{iĄv?)JvSJj#FŻҪZkt$qڻښ@v;l
\i$8#=[Ai@
q3MflKq@>ALg?%8}
?ƛ`ob܌ʣjC{Tm`)|@s	򑵻(|ե
K):ӻ[d)sǽ;KMZwqiWY:F Jh/EYoBJ`l+tbyi 䞙g~QjJ&v2yUg4L?:ZR|z$ NTXIhsS$}њ Bi3IRg;q'G(I:nh ?UOz4f\jziUST{ϭ!cNúB4b
7q=ilP!74L4n>.
=&FQ@zLsFSR44OMܾDҔ5M-+qgޒ \Ѵ{KL ( jozZ@;aNKHcZ]֘)yøZ3M=sKΔ9$~tLјNF f$t\iLҳ0AK;bqvJKR⒐-/&v3h~"XiB%.GMP]:nM(ޠ4X	nP>?Wt<iB8Eɼ?~&%~u\: 5^b"͕NBu8K+ Ӌh#sRufr)DFs)X;5C&h\ vZCƢhɢrL7fhhLrMf3Jqz
y
(
-&hZ4=CAJN' R8KHwC=E& IsESrsN UO Ϙz4gj\-FbOj0VMznjQ+
N=&JИX:sA{
YI>al 1\{wɧJD6O'8YKe$R=*הcg;PoPEO0HqI:OW"F:sO-l?r2F}O&+K/Q1882'zS>մmSv^HBN9f0ưddr=MKE5xۉHO4C⺒7ܭV?jI+W)Kdk[[9a[mH$rjKUd^qߚ[|(ݚk"I!f$DS4M$<U$+=*RiFz^icH_j+KE%y *Z
sV lXcxWW8 g=!oBΜgSIMk}J-<nFP3)VXҢS1JbqQ#H\wN%Gv;+ѱW#o7{z`jvY6-kY}*du4Xa@*9 `pM8^OBEQʑM+)hjZFD`sօAϵHBszr3CcQD9 I?ʗZk۫F@aXl)ݦ9O,}?:Z$*GS%L.{i_neLIUg9DV9gތ֬p5")HS)lU2M9>N+=K-r)o4!4!=b8Ɋ<KPq
M?7QbC@8SqOM/
12d?!Ǚۊiu_ʝb pҁ(tԾh0=h!?tݠʧ?JO4fX4OJi۔~T67aN D;	HQSJC'4
ȋsS@NҘda8Y
aq<rik/sNN߮M @>1h6 ?#My4#4ڐvChh(ކIJAz6
1
&iJښz!wXir!eJw(i !( .sIj3@4AQ
2i2OzS :ipO֍֋
ɧ oh
BvjJp>\,(_8 ;SFԂ7=7<
/O^)MƔg۴hzcaPTtml@)70hqjPzhdSG@PLF֡3Ab{P%<7Ґu3QN!vIȤɣ4
Fiw4\vh74f"q5h`Թ4њFi3FhњLњ@(.hi{2(l4J9sP
BM@<Ԩ
y1NqH$8KMvC>hz8s/xkUEzbkyUfRz52.
ޢ6sdSiRRBnrz|_[qN=搹be.Q#;8Vq
5a|9"T[pp' g`|<T.=KԗBOsPKd&\{h2jUlS[1]>M Oқ༄եc$R2NعWDUtCLb- =+N(V&!
.`2R%L[rNxS!@͹!R  Sa 2HIZ 9**+<+a 3Vc "qUZ9$H'JnA]lJnݛ}i#rH0ç)	&v5~}R'H>H"b2ivVZӠFLiTKJssj'$bHWdc	yѝC}[fCU,}7&r)a7qr\TgZi"{|Swe@qN}xȇQSy 
QhSG<cc\~ѓ\ZH݃G(xL*Eiˮ9VaXzbk[#U<bI=3I-8۸ Qz΅FQTZINsƈ.(g$(f| ˎNEF-ĩ*6P}LBgsBDVJ'BշwF[Ms֠ u,-ƥF5IILXj)2ѸK5DL2Z\|扺法#s֎D7zS
x8!Za5M	fN<bR}iSUbyɜ*&4yJd"JGjM!M%%IC]\  q؊i>{I)WAO4+Fj"ԛKwsni{`30FsSE@AѷqObHiAR(G9.+
Y8ʝ@
cEDC)9_&1+s)$r\1"ܐ&h.GH54yސM c.
LVw)VzӄGRD`
74'х5aȭGy?(q$?{ *,+t4 3I1΋g;9]Z,'P SO1ȥb'(@
DxdѓOԣn1ژ
Qc2?Tf) sLHW
B$"`0(BSOHOSzĜrh`? 4*7ޏ>D ij#1ͧ`(*	?yX{Q,$~nԂ@>Sy>n4Xw.	Bz҂iXw,CIS@8Fi0M.(fRff\;iޛK Tv<H?*3Jø &,+`;4f(4њC\ihA4:LސQJZCm.ip@J])HXcT9?Z2h'*zR&XD<D2Rn^b(Uh㓃L(ÐsQyփ9`,F*] P3҉އR4t5 Wx4Ը^=i"jnK)T4Z4"+jz<4̋TCG9"<3=sM@\H#ޙ3MGj	5ps
F0F=8J<]4Y\ȷ%Q,v>isT.Nr
F\P98 j^ㄧ4445`UqSϡH\{le'$J$k>ylL\
dUDKsyJ5V%Qϭ@NM$zF٩L/AQ#K)M ⓚ^hyjf*z;(Li*_M5m @hH>EƛoQmY|r~+a3Zw2|eJzSSJ+
zSFc֚M0#!ۍ(cL5D	
֥O/!tR^_OLԱJ@'}k'4+$S1ޥ4μ\FEL{
ZrED=6ܲFpOJn/U$qɦĵmJXqɪi66=yo6sV
=O7̐f4@ؑHBs]+:;f踒4 47R39fZص[M:F۾*fm\I1I<cάy 7jYvHF$
5d$jd1i!$|+~Thgޫ<lS}jUh;wޛV(f> Dqb@Gj
˕lB:bӓ?J.tW
d
,F3"bqdfiJ1K`!FiqE %4 i3&LqȤ})(ELù&Ta?v&qE尩
RҪyGtY*S;}*i|t] \}(b
*yytXejjzjE1 =Ģ`37'<0ùa`
f??:h$uaIy#Q9ir}I>#C@?ZqN$ 餰N4٥Kҁɥ$曺1yɢrMˎ1G!c4dEOz $3@ɥs6Qӊ PisMKHQځJ)fIFC%E&Lhh8ILI`;4ӕi 7MC`*o$4X.]YR>QG>"!'S{TzM"ԙmqi>l?)TA9ɡ+XM⒂i3LsE64 RfFi ;4R1٥p4K~u7EٌuSHwn=U_ZKg\Uvn)j>вQcSvpj/:NƞHԹOzB3#i
'8lRȊJB*FBz0X8H#0Gzfb
4CGh$M]b@NZcӚbԲ.;֩i7\/}=qZ냊Mr3-yf9wsN¹v)m>+0k8>;ӼThS泄c_<(%S5֤YO@h)H29+apiB;:҉MV'rЛ#=
W.AOI7pMᕰxg5`=p2	3qr}{U7R(Y6.Nr3#O;q֧21cXA(w)xbzRrvj*8e*|C(cګ<ͻ'Iq7ضnQrt!ɩ#q5\J6<cyeIi1یr^EP@櫴k$c)8Q&HŰdV@
Lh
H3Ori,GM {"w)=yS-yqc>a>*VܴLqB.H=jDJq}؛[UAǽMԴ\YvlJU?3R4@ldsduvk{"O#8I$ =RJ[y;]'$= :X#Tnc֩M,dw(= 퍵X]c]p*ɓ\%C?Z.]N3ҪZhfrw$#Rnws֍	Tf啎94T1`Am;sYv3I3ʜPmзl欭ʾ7*N2CN,maGe$a	ϥiCQOF E\WLD4C«Id2<gb(a$6y5<[/Pjzi,0yO4RsZ۹;]Zңc.>eQZ2vB7n3{fS(uIE=?p;5@m",69jGP6U(ŨLUS5w85#8q9ImI5bH5\;Ұ4QHA?
!bFO74fg ޙƀ֚wn4 4ԇ;ohsJBқ;~Ts,HXQHw4j7c (SNێUz)c Ѹ0)<$M4 T'L-}^̈6)L+`sM*í M֐J`;q&KHcsLfii )UKq@挚J(sKJ) 恋NȦR4 
74f3L.ivisLf4(斐3IE -.iQځIFidӲ@iriCN޵&ԌJ޴tz3B'ǭ0}3Hi)9ȣcދPOaKpi0O>dyf4ќB E>qr
JHasQIK,@L?)M;⑆:SM$"FZ.$Q֚V;i?:ȧyMqLbH6=jq9>cI
s3A$H Iޜ<81iS~(eSZfaqJf-zg;FiFl;p=鳕 ``Ji/bI"H<Rրie bSp9yEk4+TĀnyn7
ij.ɦ=jH0rMU'4wљݦ\y)nOdry$"{TEo (.05
IZyv1>?dyD19sM<Uښ)NizTg"c!4-I4eqPB\s"78oSUÊapW40
8g';A) *2jTr)↮4^25iOoZw%PzsN3|TD\gjV=j2hcM&F-4f4ɸZҊb$SV|T5-\œ <;ߚPsާR,PjAq֫ (1Z)2VrzsQiriw杄؍tyqSĸpsY0xⓕŷɀd )epO4#VGJRIY
$F <plNi_)1hH)"T܌U"Yz%~ji4Dք;L,l6(4 O7Zx̤RfIxO5(Cqڠ$>.Skw'9_QPҢ <zT5b{3HhFi( A7RRQ`ԫӄh=h(sN Q!J
ujE)Ci<P?Ȫ~a}M+(n1SDۏùd@(\H$-q٣74C^=i.hfϥ-3uf4ܚZC4њ uFi4 Zmc :KHbihisMiu-7u4--6C)sM/4-:f4g Z)(!4fHs
!biRHM4M5I4M<HD4bHi4bHimJh )s<iiOh!ܛ~zKy4fǗ4޴i	+zRn4y.?yoniv攑=7pycM&4f
"8E;M&q@4Ҹ$(EJe'C-	M'=kE"%NPi67fɣu;HM 7R	3K4Lњu.i~Ef4xnisH.N3*-94)1#6GJWp3QPSF_<RLFM394$֚7 R{S!)0)Ђ(1K^h
]P#4YHEz}j!XiÚfjoNfܳ$qN%Z_ sAz&䌞)~u5 {R)6cT
`3	4Uf2ԩtéDʅѢ'Ykc֪nsf#5<|BA4j89vD5<+ڎsJucIDN㓊 u4VhDc<)ѫU+4NS)N:	i)(PL?uR1٥њ u.i@ť74@(;4fK@Fi斁њ@;4Ec6 }&hh4 )(&hc.i٣4R)hRw4;!\1Թ⛚3C3M.ivh74恋GZJ3HcsMu%% .yfAbi?!Hi:jZJhӍ%P&)
-ɰHiԔa(,%PQKE QE -w@4vaIEGc@њ
&p)Ph74P7SsJ)~Nizn9Fpi{(i4O !OZMRRrFiwvJV4ҴbsMe!N=iզCCMwL~4.s@B})6a&
1isHxIdfhL㚄P@"M-u*ϥ74u+ǩrõU)CE&L\I	l4M0&iM!4J
2IS5?pQ57E"bq)q)}0lR4i}$v(ɤM.4Kvhdz@!4LIHMQ,3I
%KMJ34,)K.GMJ.74|q&> pG$r)\n
Z {020}Vb< I*^GB֜ ZV G̢ <)¦̭
>ƣ6:5l=*o4NAE%ԈFx(ԹTP1Դ:'z? ;Z;Z ^鴴\{3I(Ng:fHc'z(٣94vhޗ4 M1E6 --6Km-!\sK.ii3I@;4fCE&hFicFyFi?3HfnhINwLM
! S$JCJiZbIE!4ڙ6b?)R@%w
(
( 4 fHiBi(4 &!sFyR3Fh
G\(jpjp4;nPaܓvi%p4JM!TƚO/U"l.?:4R)"Fr
PaA)|nsQ$7eTMm
;j923ZF/JgUO3qHc>1=Tm8ZE=2Nh=+BK?J2jI[42L9"4;oz Mf)!34@JJ}٦@4њIpaP֋
2}0MhB)ibFN"0Pzњ/֝fiA4?84Xw&,Ul]Ԭ>bؗ4ozӄw)Lz| ҉.QYȦ\0eҝK4Sr)k"њLJ=鴴^g& ZZJ(Rf:Ns@KIEK@ERRvCE% ).i(1sKm- /zZm-!KM--74f3Iތ1fm-!KM vh6!\曞(q٣44ހLv4fW4I(CAJ(!ZCKHi(E%
(
(RRS؍r}*it sT,q}>\,D>qM\գ$f!
4Lƒ֛K@(4i٤
fM8ZC&Vjsңϥ;$M)a(m4dbtyC@Қbc?*l\cStWځzS`En3Nߎ:J
URaܳKUtyX|ŝy<_3Vb\
֣KIl2*y MZL(Gm5+sQ5:Ug0"WdU+*!)3NJ \
/zwHh (4ΔfwQ44ўivi٨&i3M'3@\vhf4;4fh&i4Ji4f?CA!M&h IP4v)|P;
.i
Ѵ;wv4W4t5% )(QIEE%uw1i{Q@K4Z:RږږE%- KIE-% QFiZ(fJZC
_I(SisHbњJ3@1isM斛Fh曚^-f44ub43@4fKivh642) Lg(sFi`.i(BQILBE%ZJ
AIE(1	QSf)ƢeqP{Pi
1G(Ft@&34bd"i<4
6C@4PM'zbE%)i(K ~isL-"Q
 isL8C*D4<ԡBELwOO\P`Uhc@;T)qNLmS74ئ+i{T~e'NW)Ro
Q.3ILIzMBrmowQޝr2IURrВ5P58=.Q*Qk
U=)L>>
)ؤѕqZ
4q(JD#.h*AA!٥2IFifsGjb3Mfnh :sFivi3I3@E&h4f4f43@74fd
7T{&A>Ѻ\vM74sM
Z;QHŢ)  %-QI\I)hR gKHaN RQ@ŢOzZC
\Q@ZnyH4Z\hg4Km.i RQ;<I) McKnh1Rf-/4R٢EFi(4:NPIڐ;i3E0IE -%BњJ8!i3IFhsR+j,fؚ4њ S֓4w3@Oz
! 4LLA&4i
! AIEPI@R曚ZC
8fiA!OT`2LSplP4K EH[8=1Rg"DhJFH\UqyEYd4nM;7sTKd۱KhN¹9jiR4+E!ȣu04M"4nS$ugf\}(z4fۅ80~TXi"KqYcRnz:
ir)\CR0Tf
1EE8S	3E!!sFi)3@!444Zbf)>g(sIL@&J jXS`Os\Q)*I*`Oa;RR izNҏGj;Ph ZZL@E'zZ ZZm-qG3Hw3Mvh斐ŢKHbIZ Z3IE .hIFh4R٢ Z)(cE&yK@bsFhI3H.;4Sihʌg3H-74fE% Z)3EBh3IJ.h&iQA4g&h4f斘
4!z
 4iH>dHiXb	4fhJ
%1J Z;RRh1٥74٥34ӷTywG3@IR}  jP5M.i%;̪4uVCz]Bdۨ5]Kp5p4r\M3u.hHE&is@#E1
斊\SSF 74悴5isE<S4M(j|RbSM (Lң(A)أRm&@GIRmEFjM,34f)f.h!f4Fi3Fh .i3I@4搚 oi7{3K\EfsO$H1D]}*<^)EHtBZ<U.hh܉A
ўiq٤'% ^ ? ZZJ(RfJ;1s-74sKM:oz\Z.ii4:L@GjJ(RQHbJ(M-6> Rf1sE%vhKHQ@Qoj3@!Q vx4;FsIE .hE!/zJ3%1i
fPii( 4Z)(ԪnH
ps ~3J2RRB(qGPDojV֪d@6FiiQRPi(CAHi
!(PhEii(4(Թ1斛Pi h4f4f41Ȧf@zњw&Pi{&"p\5;uRb'
K
KL!viwT`g\y
@g^Ӂ.;m4i恐45f4\V+5)4qYN41IȠ	ACSR<Leɧu2?JMpX$
C4\\R3M 欘L)NِfsGL*ACH@<is@AM,DPH" 41ZaOJa)
њC\f ڊJ+aRQ@.i(ϵ.xw<&}ϵ --&hbIKhh>Z \џZL3IE3Mϵ.i Rf4Z3IEFi6<ўzP4 Lќޓ94vh7&QIE )b4ހ)f4\њLњ83MQLE Fy>׭.ؠbԟQJI4 ! Z)(QL4 (4RPh J`-%CFfy8i&igBhHzJ4RSRRJAIGz
 QI@E%J(f<њC)4 E6Fyf>4 њfisLCFyw拌vST}iݪT O
T6'
OUpII\曚Q@
Ep>(4K
HwҾ >g4
c`iG;])sN)FN)sHh~m74
H")0EXiiMYpiP;&-( 6
Z(48C@2z}S%M=*B($eQ@fJZ\ޓ4P4P1vK@E&y<ihK@3EZ3I@KޒLtfKm- -P斛ZC4斀QC4曞h ;4f4fKM ▓4f)3FhisM.hsFi3Fhf Z)(Qm-!3I(٢\)( v3L.h);@FiP!h&h4(@4( 4QbIA4 CIJi
1	ڃE!AIE%%(BN(E QIGj@- QE&hf \њJJ;<K@\sFhQnyt4jD1*)/1QZFzM} kE q@;Qށ IL!u.5\Ӹg\{ M5iCS\ӲjhMԡ<њ u.u.C.hF
. qSH4fK֛@nQ4wQ4nøJk 4n'4-!4ӌS&3Fhai4Rx&By@i	Bh}ƚiiHh^J;)i IK@Ţ \KM.hh)(QJ3@dIތh4 3%^RfJ(RQHQIE --6;4f<@Fi(cZ\h :3@Fi(1sFzRf \sK Z3Iڌ1fh'(٣41h'z3@1sE4 f<RwfM&h .sE%Z3IGQ@J(M'z(Bh)fHhRQE0RPHSyҊ`L[yӾoJqG9UirsL=ii(
( (f \њNPJ(h%- ihsGjLњ \ўi3Fh٣w4ހPS(if$qJ$5ho2iwqNM^I$sFiV,
PN'N5M.w} jvMPQnL	wqFu.hMԻ<@\usK67T;wP$&4n.?4f4 M74fuOҌAp4QHh)&ii<Ji&P !LZ3IKXE&hE .ii R~Pޒ_J3@KޛFhRf u)3E ;4Rf-њ ZZNf4RQ@/jm.hsE%Z;RQ Z=3K@-4PLњ;ڊL@);iibLё Z3I3@Fi4vh恋3%4 RQ Z3I3@A\ўi3E -LHSRf Z)?% .h' QI( RP!i(J3%JbJpl(  ړ4`sDzF,%H)JF)3Li(QIE -'j( QI3@E&h 4PI3@ތf-3I(ii3FhqJV]1qF=	4 b3I ZJ( SsF}LѸT`0PN
TRAUMޜKLAԦ
NLC4 )Z4ސ.]٨.hLњu.ivyh .2))٢"4R2FLґIii4RPJ;R4J(߅4 i3E --%74ƁI\wK@Fi(g)(bJ(isIFhRQ Z)(1褢J(isM3MFhfK-4) I)\Tf \E ;4Rf-4 4Q \3M.hњnh@њ u&i3K@3M.hsFi3FhsFi4 њm 4 RQ.*3IFiw 
b
J(4\fJ \Ӑnp=mmZC#q5<Rr;VA`59lJ k=jz{X`f
R:푏LRSABQE(Bv QE% -&h f
% .h&hQMJ(sFi(& u vhQnihiphUH@51Cc3Hh<J/j3IE ;4tu34f5<bPԻ-ԻM
Kbmns֗uUۨQnEK\Yf%Ku(4&ii7RQ\04R3@Fi3Fi\hCJM"i
 0)C@)(4њJ\J(ii3FhsKm- .is6P1٢ uM.h{QIFhii(Z)(bRRZ)3 RQ4fE&h&*J u4PIގZ)(-6GzO <fC<R曚^ Q@E% RQ@ť3H%:3I) d@E&h .h%4fIj3@)(4 I;QGZ 	bfM
(BњJ(E%043@%.iBӓ@	F2zS08PeO V&®Lʫ\P6q'LU1DaR)(u	PKޒ@-4 4 R~P1hP\
;24*6)PC
yr(1`DhT^8]f
?/)*P1AojWdiNuDF47m&9i3S֒ 3K(04^+84ӸX~isQKw&iAfN$J
G\Ӹs.`K\{s@4FhJJ3@@!4 CJi(24\%E% (IK@E%/4 %  /J)3E .h4 Z-PI3HҊ`-/jJ)Z3IE -P1h -.i3E -PџZLњ vi)3K֐/zJL1Ԕf \IE --.ihh4 RQhw4RQ@KM 4Z3IE -P1sFi3E -( -hI-fE%ZJ(Q@IގZJ?
)RQE
(M%("+wzT9eڢ@݂('WڳGjph#E>r*ChY;*@9ܮTқ|~1Ll49dqHs#)IށQLCE %
)q.1fJ-fQ@OU,qL?6 恒}1LN9U$UYzH'ZjfEc!CP"2ؤ-VQ$]R 'ҝG8z\Ptf@"@9
u :
.i4N\3FiCKe.iCNG\Ӹf5{?"5z拀L3K`;"3K vynh gQIKXP!hT RQ@E% Q ږIE Z(3IE04fi ޒ \ў)(bIE -Q@)3FhsFi3EQ@ZC֊@-PJ3@Ţ4s@3I3@3IQ@R٢1hFh٤@4\њnhQIFhRQ Z)( -w4Pf \f@PIK@4 Bh
);Q@IEzJ(@z)(f4PFi( %(iCHGJ)ƂjHfazPUE[ғ$zՒ'RǚU850I9<SI4̻
AeU~)=h-̥N
cts@84N3(qJ8دzRڧU\sA4p})NEOͬN(ZmNcfQ22F(f((EKs4f.y*͑ך(r
/6_5EdqܽsUV_z~Қcz 
L Ifp1SV	N21R{J]@F)3qўh٧d3.h٥M(覓I3I)
1.j2isE4Kw&isQ3N$4KwG\Ӹ3KLfI4 ўi4EV&f(hږ-Q@E'z3@E'jZ Z)(bQ@Fi(BњAҊ.hE R撊 Z3E% .iJJ ZZNu1s;Rf@E%uGIFhsE% R(h恋3I(sEPi(4fKm fh)(&>{R~TPRRE%-  IK@-% RQ@IE&hsEPG֓4)(E\QE IEJ ;Q(њJ-8S3FhsNA<NV@˨O<#JqT})'LtҀ1UW =*s	O3ӽ'j3R&Lw4MrГxi;R9 
AH"."9G<784L)Juu!s=eGVT.}99KloH$C0Ni*նϘ
Wa(%\њJ) \3K`Jf5,LS3RZ`
iwPb"x	7R1)4@\aR)7lSM+INl@Ԙ(Rhs)sI:n(04F4 f!٥24\5isN\3K`?4gޙ\Ӹ3K.FiӸsFhh̰(4QE_ƌQ@E%- E -
\tPњJ)E%- QEJ? Z)( .h8@-% IE /Fi(bM%Z(ZLE f
ZJ(h'4Pʓ?J3E &h@ŠQ@Fi3E .~RfE4PKIE J(hƒIE04RsE .hQ@
~( %PEZCE *J(AFhIE QFi\҆<RLZPqLjE9*IlwMfTpb(py 	#ς=. ƞiʽbj _OD64%ޥqҬ44|iު	r:@sHC_jϞdd%&8&<i>Mh)(( (zjQր&
J@=j4
(N9ǥ(!SR7\	295ej^8`4Nti sLʙNh{I@jpj`DF(h
RR6h4њwf\Ӹfh ?4fZwњm


================================================================================
FILE: app/public/images/project-flight-card.jpg
================================================================================

 JFIF       C 		

 $.' ",#(7),01444'9=82<.342 C			

2!!22222222222222222222222222222222222222222222222222  @"            	
    } !1AQa"q2#BR$3br	
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz        	
   w !1AQaq"2B	#3Rbr
$4%&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz   ? 4Rg4Lhu8STNQy4I17QEQIKE0
(RbRLaE1KE(P1)qE- bbPb\RRъ\R
ZLRi4-%.)HqM4ڤK,G&*|:=g(Fe'"l洢jw&ʐ
~f:)Mg45ڴZ*G0׆1VQbAyT*|bա8EIv+>jϗF\DROjUZTRV"R@3n/NkT~SXw?
wP檖6*fLhb"L
&(
%:;4(۱A(vJjEj:ԛhȿqdV*^\gO:ОbMV`@3UK@.MUjR12pݍb))h!(J)hhE-%%- J JJZ(RPQKF)J)hRb	INv)v.;(RLBQ	nj;PYʢ氣)53s0AU%srgli!HIԬi4IVdŤShA4`QIHb
LPEPIKI@Q@RP 4J(5);+Q*(^ǂ99Ϸzvk5\#.eS"e݂'#<QuH.,QYFq95W\t 4s"[HL6Lg >$o@M&rj90jP8k-Lk"Tr3Me"J86DQE
Z()iJZ)h@Rъ)h)hQH1@-P1sER4QE
Pi(b0µ!+Xw8cV7GE)t4ԪsPGXQ\2GJ.
VM0V1Fځܦf/jRRܥղ]|wVvRW˦*6Jij&H 5J59N#NP|ǐ[䊦NMwRRWcJQI[&fr
&*"ԑ.
"IV@;b
;@b⒀ԑV4Zb{26ni4(ScM!b&)ؤ!P(IJҸnBE%Ym4-IL(!(E.(Ch )hQELQKE %Q@`6ZJ J\QE Kfe S#lRfwl-$DGy-!w2iD5n՟8qgxĸj']+EEc SI*IdsζU_5Uۚsjj(甄cQJO4kDb&)%QLBf((EPEPQE QE% QE0
((AE QE))&#yjBNp	RCn[ot62Q&O:OyR:P"e;<S,n=X~_Wq(1Y$ys3``~.ATU	[e~3C	Rݑ'R'Tw}iY: Ƣtm?̹&q\,[0YdU$dxZ57(2Hjx5WM94\Z}H a}I2d$$N}*_StSxƍ}n<׉Gm,t	iw,|
~5˂
8,O)iRnk;V]ԆLDE_4`ՠUֲZSRZe\Jx}޵`*E.)h( QKE!P0Z@%-PKE)hP0 ((b	)h )E%-Ub*d6~h5c>
^_z=N4^SR
qR	+ĻI=ir=h"Y?}K\]iCSSanP`ҵ%MB(Udj
>jdJ6ԩMjcʚqD^x	cU⶚0ID1]P[ÁNR
$
mk^^EL#5=L9eɦ>vJR\,C1Rm+NTSH!CLCh)sLCqINBRS)F)qF((4b3֫fڐWݑ$Q*V|{ȪsMJbRSI@	E-%1	E-ъZ(bE-RP!(HhJ`% R@Pi	rjK28 rkT@HFVјFp⪿K!TZ͹Iuyff,O5N{DOMɦE1)Vja4#&Jd%) J (AEP0J Z)(A
(AEPEPQE*ƟfVrJvJW=}UsW,mc$~awl~G<PKT.ZKIm	_*sROq=+O4U.ňG@!sOwH@{AG@(r Dpȹ98ֳk{+W_yj¡loV6X#sJP4m"OX(m߻kF:3{VhI3Gc@STč--bt'4Si)Rɫ
jE$)9"5`ۆ\QrЩF*ثKa֊1Td\V0=e*}FHxN*,VɦbQKE0
(QKE
)hQKHZ(QE- bb(.(R@	)h &(;br
Y\wRRh[w]tѧ/)=jFB
H.}+ya衪Nzeu4]޲EQ^heRJhi|p9ARإ"悹Ê5dƔya,Jk0"zӼִm̉J5+XE''-L:uf$
1M8
zMNn$0=*Y)  Uݫ	w1V2$fEVaظLl֜gR6؅S&h85	8JahɌ!RT!LSRbLP!?6iԔ QN!*H(zdQM\i/y׭V+HͺFU.7Zn)آ0IN4JJu% %%-JJZ)J%Ph RL)hE;m&(XLQN;
zFK
#Z~Cc:z,1{xKpMTy	r]ݝ|ȒY=j94lITla)\Ri
&i	$
6JXQILAEP 
% -R ( ( ()QE% -P ( 5~X[:5C8 ǭtos`ccN7c	{yZڇ,-`]T6yCUmٮMcs0c}p1zLK?_;lPF
rٯJ5;i:wW2rJXOrǒA g޼҄wCeGdgZG)g@'|c? N(?5oT0$~<b"P:?zWw|׵i3KY1@
zTcDS=fQn6ҲNjr{rFf8MZKe	xA46>)DXh#(9KѸBJ0qP9U(nz֌9
sĸF[O	dU\bbdgO`	$WU,BzHBʢqVd(pF
t)'hQ@QA`RK@b-bR bQ&)iqF( RR)iqF((
)h▗189Rx1WqL&hu	pzE9da޲$U
s(P,;;23NYidЅru|
YrqM,j&撎r@mhfYLU)ȤX$N{"9/Z i4F6+R50FLa)RTHSHJbLSHE2F⛊~)1LC(?E&)@ޝLSINCqIO&)bB)qIN4E:S1@	E-%1	F)h57ev8
Vمh +%Y6n+أ+&
M kG4̣MbjwGj*'gBäEj2*ÊzLTƪBi-WbOZM)dUROZacL&9gFMM;QE(QE
QE( ( (( ((QE% QE0
(
(AW2MI`ZE2K&vmT dH=h3f d&m_0P⥗\[[vѣkX&'3MacA-tV1hGYZƻR%\)U

Fh֣gk=w.ӡI!F>N4P1)sII `Ց?iu8'G$IbX,rt;[c"qGՎ(BER4f
2(҆QC2NU@i
^YiLUPĆNhP@4+#~	k!_b9}9Dfն.k֬wW=*
2jI'Ue:E+te4(0iLZ.r8ٓouWi\,Kpj
;REaԴ@)h  1KE.(-.( b SF(1K1N!.)أQ n)qN..1;b
bPqI~( 6\Q94pLs;uFǚآsIUa\i;b#qIN0
LS()h i
"Ӎ%1IiB)أ0LS&)R`C1I~)1I~)1NLSI@Hiؤ1
4SHE0B)آ;b2(46I JJv(! +sTs[IiZ'F7,U9JuSДt3Z<1RmgYI
K+gzQ!ldb2cBIB;$敍0գ6!4S$JJZJbSI@%P!(%PiQE %Q@	EP (  (b((( ( (RRL4Rwl0̍rrG,8 K]pJy{;(ۗcWނ%M0 0VJ$~櫞:()E!8 i@5<ഒdPvaն }b5,Kh'L xB{+eĭ<݋#ޣ)Ԕ\:EihQI@E E&M`Ӂb<_
(4LF*=9Uzr#jG,2H=4a5}QY4R9hH8P!E<R
Q@L8wRsK@9vTżqRcS·إYkc^$SF)LQ\SbSF(
bm\SK@3b RbSF(Q@RE 7m&)ƒIO0IO&(LSF)n)bn)1O&
 7bZ.1F}!:)S
1&)0E&)"<PiRbf)1O"`2Z
1
"J7J`4LS!Rb("CG"b1QW))1E1LbSJSsݶL(866q\85;+w UIllUfzGXIOJ#֩\2WUfsPdfɥ&jћbCKHE1i)i(P!
%8iZJ%QL((BQE RQE1%-% QE
JZJ ( (b((((AIE- %.8e
Uۈ$N)]$BdB<~WRgwj76^&o=cH％ݵT cʫRC 'RQ@ KEPEZ)(% QE KmKfisJù 4بsJ
+啔2}j4Ԭ;u&j|SwW&4*|*EbqNp)Q)\
)4<Pj&
'`Oګ,ޞnTRRcvY448ȫyfW k9#Hi~EPzj6oҤk^%-5v"Tfb
*zSq[\bRTivp#j])\ъe(XbF.#.)ivҸG1Rm\F)\bh⒤F(Ib#&*LRmpRbIRm6ъ.xILQp#"ԄR":J

 GF)ؤqI~)
14SȤ"4n)qK\P6VHh2)HNqM+wIii1O&)f(8LSRS)CNE-%1	1KNE8"!P4VfNE$@E&]fܦz1VDSJ	Ud֠c櫼сCL!5sZ%b#cQNjai)i@;"Nm0N:IiW"))ؤ,!Ӎ4J(!(RPE QE%
(Q@	EP ( (RP0bZJ@QE QE0QE
EP
)h ()h΁)h
)h JZ(C ZZJ(isIE!
GN ?u.j<qf&YH=japjisJ,sJ&8ۨ@3Mj<њ yq=,z3IE 
8?GK@֬G1S8Iwkj)eOZյ*\Fۚ0EThjŽ`-"P34ðL['s0
pR<@Rlm;)\ѶF.%)6i6qLVEqIf)1R\D{i
Ը\d8LV;vH3b1@SF(!mp"!.M@Ȧ"V!1HE<B)O"bLSI m%;LKLPRF(&'4M"&ƑM?bIl)	T̸Zi
0Ԕ)X1N&)n)1O!sN"S bsI4W n+B1	!/&,VwvGU(4uk6Y$Ƣ04FEx枠n6"#8
h*׊=Kpa/3
=jhCVa 
%Cqpj6aj	Rbb")"iM4M5D
%-!H(BQE% QE0(AIKI@Q@`%Q@Q@X(E RQKEa(R@XJ)h,%Q@X(XJ(,%PZZ+3q(QE%PQKE %-PEPE- QE  R撊 ZZm-!PQHQIK@E%-4Z@8R
:BJ+­X@J,hճG5[6WO>5QٚnvحcaT"VԪ_C	Ĭ8
1N LRJ.) R⒔Rb)qHӶm>an(;(?mъmhHE&(␊m&w,RRmČB	.+2V4*)☆M""Sb&)1N#"EJE!DSqRM"FE&*B)1NGLT"bE! ibQLQN@ kREَPT+\
=YVd Pib ҈^õ@[ط&בp+
6G+!)jss7:R!fJ+ޥvj"*-G2"e1; R4'ˊKR+L>cP-ɦvFM\bSFM0yR#"ij2jF<
R!4N4ڢ%QLBQKI@	)hBRS((`%bXJ)qF(Xm-.(Q.SF)\,&(;bQ.1Nab1NaQpQN	IN Qun)qK1LRVG@bR( ()hQE RPE RE
((E RR0IK@E8RRC
<Tb
K(<2M+{M6ZƤn"XlLJIҲw&Q+4U8Up1]qуV.
x!hRSvQ)1Sme+ZiZp*ڍ1LRmG1Rmm<RTi"<RO! QNQN&)mLPqI~HE 0LSILDdRRM0LSȤ"IyȦRi"2)*LRm;)fh@E4cFVb)1RM"b<RSILCh"J aB)Bi)qHiCM;Fh\XsⴢF86 +֒6tQJcҚSvyFΤTe栛UdMƄPuu*ԅbm=j"t7qMci53S
]ɱqP\,0-b ʰÊhjӉf4N4Tc
!Jdm%;+	IN&(	IN&)J)qF(SIa1IN1N.)\,3bQqn(?ma?m..1Oqf)qN,61@Xn(;1NaQ7bLS;bF)إ1.)LmH4=bV:7bPE.( %%;,%
QK1@XJ1KF)R)hZ( Z J\RHb( QKE Rĥ)E 
p1Ӂ
p2Pjdr
W"R5mnYHmwb7iZϴk	Ĵtqɸ6˚jj0+8ɦg$T*0*䫔ɪT]ыBxf؇;O.ir3L4 f4(L*)ԔaZi.)S2)T,{h1IF#bp;)&݀4D
9XJ@sڡa\,6#wJ8552bMEX⣞0ܽk0^ޞNKRS%d*pE3hLlH;6 "Rb a*LSH1HE<b#"n)SE.)E =PqJjsaVd&yڲFb}&()LC1M4ILHE<bVhCkAペ jSM]fk܀bv $\ן-JlctAHVQȩnIq@~fϚ@խ@f敜G4h	UqғvW"	4R0.jV^%aQZ#6Fi+M+Url0SmpRbIb<QQqXbi1LVLSF(7bڍ\,3bKp1RECmL#qVT/ڗ0JivՏ..aѶytyts)_m&ڱMs)1S+N"&*](<B)b~)1MSK$x&]+bmJڔ%;ZpJGO$Kǚ`5n8sVS)XN+LL1
22M`7easi
)
Qp(JVVb<QO"ab1@XmbQp1OaQ.1O&(	)qK.+
bbR(.)q@	F)qKJ -- R⁉KK\R
--.()RN!h@=N*nA\TjYHٳ*@ltb|z;cQB:v2=]j
ɭ/9%BMḩ 
@qZ@&0;S a@3IzTUҞ:)L9֓bH3QVe.Ӱ)@ȼ4`P#5R[\ⲕN-qQF3XOKtFfޟQt4caW41=i;rUVdgGZQY~OG'&d*x5V㝴!EsJ>HLж֧F5UsE2-4ޜG5fM"E<LSRbCLn)Rb4S@ 4qC5<jƓQqTcM3)*2u4`6CLCH8SSHJ n))Ɗ`
2jL
dJ	tZ-[m: j4Ft99R<ybDH^M(ּتPrDIo j0MajfJ :SZ?jReYjFj&RTL!ګ1aL5ET.S<M)W1PTK[e!QSaL*B)$Hvl4+Ie.wv҄t压DtNʱ\GKՍ9JbJ"\S>zRrTCRj؊J~]]Z+L+E(RIOQlRq@IM	M"Ƙj
"q5i)1NI3iD!i)SQ!̌%8%H̈%8%I.aiNE,FeERGXYk	t5T~hEe͹G4:ET@ktnLTZJcMڣ+WY*"jDU+MVLtUh
RmqXf)vq؏mj]i\,CT(XLU4;qF*Rm)qRmE1F)h
Q.qF)أ\.)qKW1F)أJ\R@)iqKWR❊\R(S@	P)qKW M!)CS&2u֯p@5*dr*͘ȫQڲ!*FzVs OC7Qb3)I>WbpjD< ޑsIP	Dkgv3N^iF	
1MTBqjbztThnML\"K"Vu'1<呲yk$ȕyΕYؚԬ+Ti))DfEJE0iMU%=h^ȫ(OJϊMjnS-r
[p+Vn*1HE:UFE!%!SȦ`6B)i4O4)#"i搊biiHii
8`7bSRb1@!C@FH<UxUmM\3)ӀG!湞Z!sH˚6)*e^<M(Qh9_4baV'!cARlL-<ZGPR&fSvI#ңhjۭFTLvL*2Uޭ:,աT4TkE"Z3iJ)
b\J]/jR"0L (RGҴ<Hc`(y>
]ǥHڟ0X }C!s\,RSfˢ*t>jrVn6RvE!4r!٠)J=jLcL2TlT.L-L-L-Z*fN)zizIdJ-MTK&hRAJ
Ul3K@-)U)U"
v)@HQ\Q LQK(R4
1ۍ
bRMc	H
=e"lv\IL&g4T8"٤].peъbgYQZ2ڣ1JZ 4Fڼm;SRZpZ ҄b 0OjxJM?j9VBST4kHG_#=S$})<6)kOIZژ`j|(le\0JC>arѶO4i\T#IJ98b.E8KѲxڗm&j]; Z]\,G\S҅pSWSJ
x&QR(`[Ck9ZLl,_2ZrV@aj[CfDjP0iQx
AsWPeETemd5EJE1(ɽ`$WEvɒ(zLZ$XP2VV+L+V
J\
SH
ӸM"+M+UqI4w)
QbqN5"AV\VDa[J$Oz9LIE8J1Z&d7S3S(r$FmZ˴J2*a6ޣhCO"El@)TLaFi+M"JySI~)SbHiƐM%8qL@*x IѢ$r=TCHMdjhIdu8IMBdFXP-E7psbCP⛻9sOVs̎lujSfШzӑ5He؁Q+ǚiڭ(Oe
9z(F9O4U%lMT $щgmTWʅ&ZizrsBx8RP+4MK{q3M\ua҉BsHփ"YrZ<P!"L3L*Klc)ܳj zpq3rc4挃KV2m"b7""V"r)jJBX.W+@J(Z,;mMX.A>]X.@#yu0Z]XW"	N	RbS&B
v)q@▖Q@%-,%(@In\OV91O2W,;(RF*K
ZJZ Zp4u!jeqOZLhWmՔma4m_XA9Xm}M
mQ=)c
TQ	S ,Pq#{!j@04 .S`
rK<{S=Rn\kOja>a0ۏJ&F'
{VѶ߳J|WF)C[gҎv=?J_J[`{Th'Q9CHm[Һo)M6җb9l});WJҠ}?کT?Ѳ#@vS;)vU SOj9-lg>}Q΅b]pJk@Gj9m*BҀBSlVVDlƙE4V(0+6؉
ZH)ȠՅJ'")vR	^p* 
Z޵LʒőTezV&EWh3Pc#tv՚6NiJaJS>wD0^hOFJwJaZc*Rҵ`4;_mQkJ Ub'i[I,Z"%(R*Eq-
 j`¸7qP8ZKA<
C	ǭXO<1r6b.qSqZ)b&)UU&&DiTEPȤ?!SM<LUf)HiHE<`0LS&(RbE!m!RP!RS2h L&#	4sMR ɩbr5rM]1Qi$q.tl1ҵ AG-
Oqѯ'RK8Qɪ2.zw:Rꤊjy'_Zѹ.,Eu0jC!`)VixZl85Bc5&GR\AV&Q-N¹!ށ'C3M"Yie$H$7Ѻ%LW"H֊hlӳTESO ʹjLQ f1Ob(Qu PbZ())Ԕ\,%CRSKi()6ՃQc+1l4\,E\S6pSiPv*SⳖ4\f$Qd4e˩wdըT1O\qLIisk("5z!e$EPbD2*9ʡ(+ST=E
OQO)V5cTN4n=jvIQAYC
nGR&
L
XCP"^]! SCqHDbKbh,TsIoџ3=fVN"i:kJl {U.)`]9 {ROj(ʚ^AiM{>:VU40{Tn[]W0Jڪ=5"ԓ1GҞ֗8Zڎ`(,|ըL-ڧJ{Uȡ|U2G
XXU& HS!DY<
RyXTE.ڥ\fG6.r/ڗj B[/j*
FЃڥ*5Z99H$ǥ7 f{:U)mvT+2jVhT<UGZlIP=lc2V[JϥRgy~xZzUϥAr8c
4Vu/S{\"/;y@V#pb	E**{5H4iHL"[1OҢusH"W+MRM"""M"DfjB)S)"E;))SH!E!e7ILC))RLJqIqLRP!))b
<HifcҔ\oqj+]&XIiղNmÒ%z*qR3U)rݝI$*\L޵E9V鸮$e;dycޣQ^+Gk"UVnjW9j!44fb搚3Ib4hSisMÁ5
8w֬T`~E]
Rfm.))+	1NhLQKE\RSR@	E- PQKF(
4Bju4!ZJh(iИc4BNUDT=y,1SLԢT2:ښa\Y4)1G}*V*J9bCN
jFG0XN .)\v#H
q#Di(1+)\eVSTQjmY1/*jQUfBkZnfib)[*DJqL)CsQp)E0T-#sR*5 z-\
i3H8/'=j#ցOqLgzfPܮK85iEU ٠CNN NF)+OW9¥,V=iȨpC&G09aӖzSNj@v1VUB\P_4n(CSU7P֔
JORLvE0Zd-Fi4!Ӂ݊P,J@Դc [&*#5CˋhlҚlҬE0ˊfho`;
J3
kJ>̥Qҥ*ZQPTlv犯<9&9r
RVv*
GO<TFE2<Tm;
,ocL0'9Aa
9oXMW+)L|Gzo֚L\Mn>By5{zQzLi*O()V'qiRm'PMH3`Iv0)hM
"4Ti6U\D&j.|ۊwM"LBy9y=OH+HV4iܛȤX1iӸXE4b4pM1w4+HEHV;ȤHVm;1@&{S9"@a^	欄"QTRe8h# NYB$՝1cYE]lZ[ÓQI UPrqju31sU[F62!zT.稍jb4SMDh%%-%0RRP )RP ( Z )E&)b&[
UciE4hz1Tj2S$-(\VF)RS%&)P1KE &()'.RQpiR@)b JJu% brFj_/.Hsʧcɥ)+3apcQ0r;Z4;	<LEAKJ.sNUɥʇv[_>nf*>i4)ӃQ-<s jEjRfSUa,֬$Ʋp*s*RƎchC.{[M\$RYZ郺9iSv%\Oj-J!4暈\*3րRSHM)qE:.(
Z1N S.( ) R@
ANP)R
pNS!
)) 4i(xT&EEІx9
Wn<zT{FZkQ Ql	<Sڱtj}+33YP^ Նt
SJVDE%KB)Xw#)yҴ2&E"")""DfjCM"7vʏu5pIVzxSVjijmL&eVa44THޯE;^jEzG4.kb:E
"iFlOK8&֤Y]GFgPw?Qjd ~1zMr*ְ?ސ
CЖI@3}53IocS.֦;ܬE?ԈĹL:|d- 1Sy7p44dkW4Xiܓ}2i3EH^ZJv婤iqsHi4ii)CMm1	SEah2*]GjdRS3XYЬB +JIRUy	'vmdA3J	Yϐ`֐@2֢ATFB*cGR=j"ic53dmȨQ&MV"EY1vS)\B*s4;))*R)ܛ
bSJu%RL\SR$2GV
abx,x,hZv)@H JJu%a1F)hqXmQqXXq>PQқ
nEsUFY"g*.4sK7b0TM&()7MLN3ҥXrHAYRAP#E+m>$KsN,HRw->.k!BS5#T<B636ъ֬;Tm\R1JiCEb:ZvF.KK1E`RQ\R
x4N#$RZ26
_Q5AW#4%j\-qQRi*4AS#CY?z&QcVj"uqmji)5>ù U.[ү3Ch±MfoSN~dIך;$\M(֡ܮTt+}S3ֹq&Ѱ֝=.wsGHlK-QTp\1ch<KȔ,0
pc* )i@๥qҸN
i
8!ӂTAK%ޝm(0SQ9{${| ZzTvѪ攓ғb(+T;685Y$O7U	!HIbzϙ(\ut35LZ,M(JjUT)	%^BU4nYw
Xh⡰gִwфϩ$@4,
ˊFNxM<RBH@Pղ7
lTReb
Z*}*6)Nڣ'ڦ&B4
5Ey9Y5dh	3zVe`oKY[YmR'=*-jlsҪ<$v
*˥BVLȦ!8 IDQ<K{V.gʵfvl[3+SwP>S9NQ[{!C08'7sPJl΢a_8+Us9]Jsۇj|VOלS~lv,EU 8C#t*q 3Omw$8P\4l
؊Ӽ]X(ѨFY`~`E	cy[ʒx]OB"rKybr+4e11\NGjHmٞG4QRj%!R4M:i
4RNQ.W&)= +)L0Љb j4XN[F*;oE3Sr@$r]')[dbj'VL&sM6ҭIKaHVQSt)DJBZ-@RrLZ"T
3h
Li
RdL"*i6U&CD$SqS+UqXbJv+-	K)ɩR{ULl{T;Ub!I@
Ib\Q@	INBRE<PҸ*f
y:2:!1x5/jh^iXⱛ~jjfjڒ)TDDժfMɥ5W!$bڳB
8ELl1=걹qSL3~*ɺ&'P4G(RycB~x
?
xqٛL:?jyd[i"w 6
{TRip+IJOZgг	{TFՇj%
{T>Zբn&;SLGҷZOja_J|._,QV֚lj.;+a/{R=8F}+Ulǥ?cҧ42#R'5-) ;S.Ex;i<cn;PW4X"v&⫼x	Kc9ZD
*52!=i OzB٦Q@.iviAqbRý?'*F[rZѶ*FO
HP`u	,S C M8=뜎jZrFNcXw ԁV#FOf!<1#F*EK2!5 X(-%Qc p*2v18=jk:e^~lx2KF`M67oWo\9 H&?ƚ$[Zb;eR9$H\7F9PZfZA#PUt Egs8aҨ%O"ׁXcjKFpZО*A))&5VAHS"R%~=*kZUE]MtVP-G}qRWrkFBAɫT9%vTMUVl8EF9!@OlPfiu	jMQ柚kT2Qk
0ҹH\ f"'QTZWA&51:"Z@2j
󚅅l!jU#5HVGҹ~-f"cY/L隲L>`ZAٙU6{i`I	1[WIC
D	
q]6<755gw(&}DGҰZm)!JphjݵYX*>>sZdozvF 94+=U,=
v^*!]SW) gQAA1ğu(쎊1TwWVIJ6RN؏)wGJ(
I)#MJM`5C<T#W5BT2 *g#?xTR+D1Iz%*vAQlWzBPU	.ٻ-1=EOnWZ@XASErc=h=4Sa@n{juiio
'ۍ_YhEDсP5ըH8EDEBeoZ=EY0G*!۩Ex4%WW!zBfu<T!rG($4f:R$3IE))hBQKE %fP(PsCcH<ԃ(Ns\lRCw-Q;TZƐ1	]gYV
֗R⩒
Hۭ74TgZ!,M4	TC
n3LGo G)hj<+EٖcW#V52ˎI
.I"E*hk>V]ʾz
c5]X8'4.(H0y
ɋFR
 T W=W]8هJpaޙn,QF
LXd7}R֪KvQa(5DCɦS+Ѽӳ+xM2EWSYFchvDRe&H4Ec%HÚn),6PRъ\RR)إpRJ8-+
pOjnE<f!l> 3O\Ҹ
B}j0	p4-2psZW̴R
jcy.]r-b5	c9cp3^Ґ+an.ٟ&2i奿ls<-HSRMkōА	 m P7WĊ=dgvNzSR%	>j皕ܬG5."fH#rZ%qj7
?#XBE=*d-?d,m~"q浼LVݧİZp1IbwL}
[SG[QԴ18Apo9o!6b8SKQݜNog6"dӑIP9%'v2sޕ-HQ'ZFRi;U_c4\[h\iAu&rQ:TiJx++#\nbi	Dlik
A3W<cXsmnj1|MMUbAW7s4ՍŜ0Jn+J73MLB09aZ"54Ba4E"U9\PS7b-w*Zy⵷B<lj3ї<U)!#uBgKh'5Rβڢ*kf[LtUZ)fU>@Gj$+W0 PүF@V&qL*&+KW6a^6%Y+$XI]lۻΏ,w&RI2:9JjHROj  3D!d?#	(a(˚MR ]Q4{ibO*lxֺ ֹCZ.O55pi|0%H4S7`՘B)@&B!X2
obԱ ݖBQTS mgvhO1(f^FnM7d6hlT6
3Tdv&9wcMEYd5!|`ZZ94iդ
-HM74;44\BԄM044i
 %-( K@G!CZKj4KN)'Vr
X\֍͖R@%TSՅI=dI(*GZO(
5<^w%Fjڅ/ږnsQPQqrg4S&Àgԙe0~)QMfmڌn.-)FNpj3BBW4ҕ)t#))ƘA7u)ҴO02sO*i6hFi
HPva6MiAui3cR@ijKV:GzTMT4RG&*r
k-a>zUvcLdMH\Ȧ3v4jb	sQ"LBS48PO;T@)\yGҤCȫ`TXQ>#TOYf;Vi@^ac/m.*`xfJ|
SjڹS-qEtOj!⥎܎^$PР>AS,Fڦ2n4bJVdfR+RX߄S=/8qT#7SQ˩&#obI󗗷q t?Q!Үz\U%CQD}J0Xj2,+딴-zEd|d#e|s)|oCʭ`l.21>S?fv 0IUOB?:)Yc9fRfi6*"[$x]ʔV+e݅rS n~'t 1 Y:UL)䁱NiBxE-
5a5	3t)X\<K-J
'kج-wĭ WαM
 ?W5٭h]ƗqFi/ip3IG3TXަ*Ѽұ^{="Ihly!u=Ea('jIڶEh%EMJC 4,9MȌqP3d`B3P<
QHa$SIi0f4Lc
74M49"#')4qPLDP2ESpE_e֪[+6kDuZX#ECpjThK*FNFAc̏6q \cz|@qi ҹ{{cFV1gjO\vꟍ[cDjANu1U\T Tp$t#5@N*Cҳܓe%JFj2q%rA2x>j6WSg`O5&(0ƹMP VyMFĚ9.NRǓQ'i,]Ԇi3Hi
14ii
 !4@6ZJaa))ؤNp)أ\,61EaRSXn(bqKKӂ.H%H.W"
68;X1=iPo2R=-M-Ib4'&U8HASpGl &˯['w?bRJf5]cEMƕ|GF9~H-_o~c;1 ^'U	skseFO, e)ǹi
g/4 T52kZcJs呚P
eFoHc4Pe&V))[fQi"S1Z03CYJGD)ivR6ҘmYgBsB))>Rh;ybk#I&)7s]6;S~ޕdTE{b`aaIJ(jkD1ҋhVYBoE"
jEZRIRdMoz\Դ2c&Z&j֜ދjF^4=i4$!YsQwLchF*!bQF)iQ]zf),ZLf
pi1#n1Fn*F2*ڪ6>Zl0XmzSkS
92
X8L!Mh9xFOkYҪIh٢ţ<Uϲ7Fν KN}) 
p4TTM! +aIP@5ͳƧ_Eӛ_ָ2]rT^4e~WU*W[%
#_Jx"VsFKZbLN0>-lI 
zZi7dlbJV2LTjٛl#ޱ|ZL~s8x>vuUU)&Pg4|O
K'$U8-$RY~{9i
TK"?O&O$1$st=E>dM74JiSM!4O4`c$Rl#L92C
00iiSM<m;4ibR#jZӱZH	%pzVTSN3  [) ]˞P"fR<Ķd~䮇<ףx%]&[C^uw ^ޙňZJ
jǢ~5n/~R=Wj_x(4QAGQ tS"_GbnzkbX_a]ucYS4\- Z*<B $h(NsQ]
dgy)Ù뱍Ir-7:{aoqp0Yq9T`3Xh؋;b1j[1fި5*ƥN9Yi
JӸFi1RM+NRO&.Im&wHEI\,Gԡ*T&[cR-ZĘTZc%CRy[Sv/p(b G>@~&3Rre/?M݇j1S
0oJ1)G]v1ǵ/ٜ}N=8Y[<<JN71E*jMR (6EA,B3,Z%"EP^!ATe<Cn1X.A!G8uMFPjcY	 xA7lf/5J_?B(>RDW)69鸌P7.eVGV!ɽUl9J/Sfd QKE g))P"m	Hl=jz(oΚlWʭ@XlOg7rzB;0 uȧN?qp>j"?:,W# S/5TέbpIJjO*x}o	֬'~3r*=HbErSY|fa} N վ/kB嘦8OΣbj7J_=OMGaM4YҍRɺ\S}?1\')NΧȅv=r݊ܝ
kˌky]OV݌{*EJ
N+Hƣ'+
"<EjAUnc,Ii=aUٗRab44ԛ;i4
O &ӶJ6rhm(0Ki@46҄ })\R1KjW0)@5 TҞU3RmqZ8+XLx=j9dčҝZkBZԪ\TwT`riܖzLy
>byIPbMS7BaLg	ڑTj_i2_DO5Pt"X@M+fN-K:faԫpũx<V43\_s]IG4WOG$&h_]N׈R
PRD*E5,mwjؓ+fmrB+6;Wg]"Pi&^,V!q7W1mgKs+e#;3|v7	j
isco %gyׄHjO
5}3Zw4snY.Q[!\Xܿ);q!
8yxYI7z/&<HIZ	)Q]'냋6-M~i3u"Bt;+U+_0][s2];H x+ޢd!EYG'YHNQ8Vmb>edw}ML5+"c&]xJ;4j}t4`F嶸oUwFX{ .rSҼJR|?JfI6pKV󸽤QO\qHO8<w{2$N
_1sO	U+AU=17U{SG}ܤC\R;h򾦣 NTtSQ?*
:f݅E`Y٬ns+V<I;]e{#tEsLibZkN*MJggWҠ{C^wu]ܶˑ'ᴦrbbPHns_SV?1v?SW#@-64v1hʃI6SkzaR)GTAc=M0+wHU#͜bd|!X6qyv#*]j_"X5c#y* n+sˠw *N*)YeʨxиdqL"ϥ'ޕsjǒh; vZf5"؜sG2 VٌW"t5/ғmڢ U&&1K9FhD8J=PEIE/EhJLRҁW&7aCȀ*\-BF`4rqTu:>m@
iRݖzTOz<egK)?(_ϕ8,j&::L1F}sWMy^ TȓWOm"Śly&?.X,N-UsYKk ~P` >hER]l2}CUeu}GmIJkU0mvS[8׮[jd g*H g"Y{ߝ2v6FX%v3hD]:a! -^bn`:C{n?"sT?uG@(LQFM{D:ͥ.S=4rJ1~9P,ۃ -?!M7wZCEg :iC4`tb#7NzD  M`BݧElVE3%lb`֠-(AE R@%j}*/⼫#%&zQV@H:Uxehi!<T9<sIv
"Č;w޴[=@[oZM֎P9X‑X2-OjvIfM0UZ.o*C`IWlMJ- E&;ѸZ-cmjO=sJϸ4_OBqV#bTUI@拒)<!A
\ESn)
NCJ)*e&Sd(1ʉ56BnI9jʬ2{xbh˱<Ӕ5UȤL5Qd8N	%)7Z޴w#/44N@{ӾĄ|`38uaq9#ͼR'Erb|:+(;oIVT VJ
[$Zj%5*2/C}"c^J.iϤ-zDPy+LǔIhc9fʞV_Ok3%\KY[;jQWM{ɕgcˀ!4]'z\GhsGAּ,r!0PN{WUXsX w6o7ʿXW~"/*31z_,p
B]3Kz?JaGQ;nBnWaO֮ HݱUtR}aK@,NRWSj7z$ywN}Yn2kEU.PzUpz`]ֵׇYmK}tEfs uXz 
GL--#}Q{<tnhBѹ2oƹMU$Vk$y.zV~8pB?vҋQ+d|Z5݉&-$$j$|[]37t+6iCQC$"j'1j2Mz37O+sciP$2z'[k0㍣W
c G]UGȥ>ƚq0iF`yw(t1|gPN{Vqٝ:ŃVx	=֭ rqWa#IXK	N[5au˗}/*VXҫhq9FJ
NMTwG9Osg=]O0	3j ǨVOa5n3U!fSE<S(T(?*qCṠM$sYS
Ln/:L߸Ö?Ye ;)ĺŜL6`
i?E兖ƱF**r8U8U7lWTvsF<|n FqZ&ZI\~udOtZ
|~U4l4h`v4sJI,inچU)TeSƝ2i8 RePCFMR)D`wIX z2*njxsi=:dsmWyҫ]h$+ u1;#C`sLgQ
<h͕'лAYڵB\~Qi-;DBX.u6Va>o\Csrw\NbiV5Z,?ve,c莊1om#W!GK\!TOj}ZQFR]Jқp=)d1?JIZ$^I} J( -PGj(J
6N7[rTG)~U
.iF/'="oʔY3i3@dΜ4 jf3F1?p$"U7
 =GK;*zO1G΁اoʜ4dʟ'd@4?~u'"L_ޠ4,i%OI *(%DQP
!OC@\DQR©=?ZC @\3YQ_:iǪQpVa]A'f=TVڦ=J>1sB='9:.4fo 31#pIY 6H{qc_JOT7"1Q"'eV+FV^|NbQSyy\,CP*_*E`\})ڗ>'q@CJ$jpsKP ҔHijJ!4+<J@<Z֛8Lޔj}ғ44ӖShCF?xvc*Ep9JBԬ8"'=ƀ"d&k6 vy|\ǰ{ijeR,
Ie #\?Xl"BdtnMuC޲9K7Wuq@Z?-viz!GmoʺcN1IKruGQjcqcY mO!hq&7׶;	+BbY?^{nsMŸsҘ+7A=VvKޯEJc?U.9ǗpH*OG JTmеUrk?g:kVjY>_P\cE+ >kVQ
8\ꦦMb
>ƂM.*\s^&YBD`dlW<kKS9 ezVHoS^>`ETH
Jx`X !Hc2K" Wi"ӤUCHwȹjPyu${:2ShmGU+u'Mt땿{T^[?ҹz
w&8x\LI:_`֥{ UF;Oye2y۝\ [(&گ<h9] n萲j ۏ!ǨEzD+{(PZi曋?JOdE\g M7C 9Q
 	\}ܷR],eGi+g1>њǸ&*]ǤFcx.3YxC̤H^V/k*\:y/;is~K 	Lh>$#sDG/M O.o/ܟjѪi=i#ID*͂"}
zfXxr~ufzO^Bڼ j& .|͞mK\lFC"o^
LVV9f Vcm }V4J%:mw Aϖi:N1TR:H:ѻVd15wi3D^k?ߝFnb~R%Թ|dm976ls"6=Ups"ϝXIAON1}օ.]eejϕf5{OVO,dȬpà0 @7ozBK9s5pNiEX${ո5S8̚(5Y%=9A\Y'ֺG9<4s5ToS~$aHǵ޿wSj	允Ga+	.G WGrIbi}(e#\ T|5mrKX˔~ 'Ѯk,gRє}t۽=6\
I]VܡE?/ Z0K'<fO+dTk TXVh4J?U(W+i\D"~o+B=nGj$*T<I)HF[VZ,2~}_jQۢ% ' VvŷoN9:dET<,cP3s@9׽vEM*.Ϛ#Tu'pqB(_VFev_Ȥ0­+(b)
W<L\t3f$fƭ8J9XmHa>{#$SKz
|V(__fB=
D˞`[hziJ\V KR-G]HZ0#&UgyW)j)GC,5k{kG%.iE TSoϱڕrٹu=)|(=
G/] Mt|;QSc蔟kn@JPj}~_`)-Er7qjT6J?UW ZWb~T2TYe c0( Qv!Ho? C ?
 ?j.+Oc}c'q ]BS+ #I\t 532{ ?g?U z?YL z5 LѺSg`z 4 H~-G笨?tGR$d ~7Y#N?S,GxA  R#YY ;ݯl?fˈ`O#@\  ^?4gb~ 0j(s'V(aީoV,"S.q44Ē *7 <UrMmOţ7Zvmj/h%}h?.K1^Ajpz@h@oj .L8
\g4 B֍#.
.,҄>Ei>&M(>Ԯ{O(&isE`ഹ+(AFFyǭ85.E+UK;Y7S?Z^$+ y D*/`+5z՜r[ԵygTQU:ƚeOS|+1U )bǭI}AI/ ghEi`--;쇻Wo^ ^<5&k>;בI)t-ST/'+ˤ+uPil+⢅ϘFIJMo\=@5'dmJ϶'i*}Ջiˋ_	
Hm .j}{~hHjZwESAȭ4ڥ0iԘ 4?o &Sf%R:r՛e<BJќz5ih|ۘVBܤ|=ϯҴ"^DH =_VVZ	_{\a%?tbYcx_B+uIu2s_/nGE 
͕H-=Z
cZ(Kd(z
q1RcUkْAM}taH.Xw5ڜDUPrAQ"=N#ru4|֡:1۝v7zޟSFz0n37
bȄ5S)>4ZxFqO: xVg"4j&yeQ?:~!T֬PLR=[cڃ	ƽ<*]d5A<?i*s7~{TrՌK|ՅS?*1rzQ*kQ7u.TB*;9y؞]<VHrJ(k+UuǽPm>հǚfyNRf9~MlV<2ZicCwW)1ٍDZZ$jOңkvts7e]}aS+8@?Z ?v.	T5@<Ρm>ņ)'eUyJN憷$42Ԛ^Sy	;iG)fVVn #g@9b=b|C~S{-VqQL w]M,Ȥ~n_֙=*Ri?x~44»[nzTs.BLdܑjH) P2٦ 90E鞕`9ScVGN9ȡRWcICcg & O 
lK''>r
f8G}m)\ Sp^x8?4*b_TwܚEqI0ېXO%r}?u."[M$Ŭ1iu5j?i9jy$A63Fiј%NU0*4ӼBޚTQiaL=)!a0NT|W.Ķy
*yS4-͜jIfJt4 [ۏdVoE=řZf-?3"iDCWRd ~`ܜN
`?ּ` #5]	u,dcf>f;{ɿܷ3mCH#(Z&&| a:h>UB :ֱfܱsQ};>au:TiS_eғ\g8fԽ'ODi]4y/-Pc?&JƱ|[ʞ"
95_:m}Sw{کޑa'H޴:f+A=EKR`ǡ8E'Ut4n0}k9J[ķ˧A3$[J$sۊY=ѕՎĞl3dAGql+ѯbf;\f``E۞qЦpqZ~czʔO(Q	㤤~_Pb ] }S7Y\ 2P!sK(Qu ;b	\R1O&(Qj~(S-:zj}?ʏzRoO/ZgWGGdjOΐG3j< MO>? g ɨ FG#0=bLW}RF) RE QHZ) dѓE- &Z@4KH▒]K@ Z]bm4T4' s+ Rk'+¹\G^~_
Gғ "-Ҕnc>_CVm|5jrVe7jdLRYQR`H6&	'Ω[ p1Vr5V?oja)e3j"vsI;~!?X'k~
ȣV
!*b|903J@XȇDʔ<=>͚1uxCGM/? ^?~ϮZ?1Mr_(d]MKts '?&ᾪ1]YH=U  be?ְLwZV:c#3KR4[Okq	,e03 nCֲ#ީoM*)e(IW4f1Vz]ȷgtc#z+g?z=SAO*=HṈd vX k<MPgpIT񟡯19{hIAƮ2kI+(jG hk*pçRtGlаϰ:s[m#Uu*9	\镪đ@lUrl,dbln?g5f~~t$d6Zk?uclWy,4rX>"@+Ϸ6f'5.|Ʒ]+u,KߞK&*M'&m `T$w**l)RShm&W%3s0AY*&L}>@0ZS~iܗ31o𤨄4٪`fa4f<IҰ65cOrj&"zaozBiEf4ԛ&iI.hԀqb֓`H:+W::
_J?#֔!4eѨ7
M4ymhW?H5Ȭ4;9t~C&|nU/(lecn{m4$N%
\d{n="{Ԯ?ZCF^8# }Z;  /85GkM63٧9&>b;GS!ȺeԆ!5o|?DSUk:B&{?	r 4))Wp2~Q7Ȁ>G@RI,1Ũ~M&'*Un.ۊ&)&K?!{Hq麑K$ԏcB-DdݏW+%7߸㚁ڮǥC%r(TRxJNgyOF4߶'j=3Gz0_vl=VOϗg\G$=Q?AU鮄<EW$nر'Tĺ$\Mcu/DsO]u*>җY>e uQY?F4[ D}jtuڿSGH\esu64lэh\U#JORG>'d'=*ЬӨfQk~E*ۆ
Q
CWnF>XPj@T{r8e?	^UkicA:ԁUPNsGnʣVcch1U>崇Q+RDZ']՘DEe7'?r^j6o[cʫ?iIltik
}~2G\0*6ҟW݇#e_@*&CKqyOTc4ce,2xYeMR6C	1\e`ScC#oAe{MwF2:Kj[IGLTQ(<! 1N&(bI&(.)q@
(R@K~)v1Fړmimj]h<R)m9
&3<q+0)6M =kB<GE3˗z =M IGG?穣ʓz Oʏ-??*hz {Wj+ϣm*	iy#b>2՘I+2=jdE@Ncן_7IcHgj:ne`5BWԗGʺiגé][39kJU0 Ai:5=4	I"	b6 nw VT^%ѳi*hr;P/_F1nyF2{I#IPlz^)Aq\
-r;1|V~)tFkP惹wcs=CөkΛړL%@FT/4^xQFHV8w^X~44F ב nj CV`.e䌤篿Zo
.T{n.+ϴ3H0yfYK	8=pxU˛`7#OO_X
Q^wo
I.IdWvL{F1Zm	`6{tf
WvTW.9lz{i[ZgSxTݬW;ZPki$@)gu m^ Z|Yemk KpFʂGSC4`U`tp_N7%49ӭgCJ;gޭܓU'>7;mF?\5\[l*w`] z(EƒL%)pT~ Fl`H1PsQ!1J@
QJ.(k|3OUrHr?:;~_Qz-3+: v
IʿZ#? S'nVh#%l(wZ7"-H?ʣޠ3O("HFqT֤_:N jyDe&]YKdUE
"}k,=?\Qۨ.Gсe5>V=Ĕd&3{]xT\ba nT#0Lc)kv Y/`b25 nmI(? νM&50LdÊd'/it皯jF5MtNOi^	L1&HuO
zGA<Qh2ȱ7_Zg6q+,j}*њkkLMzcDq}*=ndicc1:sF\6wx`[*+qF {ԺWnSXbqyj2c
CUbkpi=8j"[=sTrEœi#˖DrЮFg*zT'5<:2+h]LؓwUK2ͭUhIڢ}Ps~jS̵ʣ<j@tV?"&Ԧ i/ޕKwi?rq(l9TS't74{'=>"#* 5-Ft*K{CQ,.g zo2A{ҷjp{䈽:+O>e4}?OrF{hRhi#mSKY3Se :>E'd=#]]΍Qt#XP^OR} 
&sqRm|^4/%ժ]J~w*7OD rɁ)3VAofՄ2
Yw'Z1Q[>a4dMCן) )3;w5ئh|Օ^'PA8_& i\oE= !]w8!QxjvT}Mu$GLy5'p8)QOÖZ؁ixH1Bh5a,-+Rk+)",cL֬1+亃T-t.,1/H~*Asf(`];6q̆X?\hȲ7H*jpsYxIM*UةJO8ٝ>oԖ?!qP65qrzY)Q<Օݍ#ךwMISC.5 sT?ovPg `j40)CLnOZg:_:?Z''yG@/ 't~ yQ篿Grz z Rѿ*oOSPF n}*N?T'?Z	LT!;n;zJf)1NNL<pnL
ؤhåawl}w  *ARh!)1WqV5 (uU&*co0~bpq@c~Ub\eT $0ݐztp}Qs֫\02p)RLQZZbLSM<R1K <5$TsNBzʬd F6_G)S % Ty *>П~T}? & tdR?
z7@ S'i>?IE?*7JȎum  U'IY@ٮ|_ޒ|Q탑T}x].=d|=d9; ,$ i~q <$ ko'J_Η"9\?Gg 25~l'{`G3i 猟ɦ{'kmu2t{`9oO <$ M/ٮ?焟ɮ_ }
؎U$Bj+vsfxI |Qmq <d MnJy_ziԭx2d MKXyl2?ִNkR
ZoI;e' env6}1Wέo >ux?=r٧ mT+FOuίhuh_L9UX%?9pĜ`b֋1T" ^*r~}1R5UϰRW#
o-/ 珘ؑQGJbFsӥFd$Ej2rГqM
ԹOqztZGg_@Dj2RmQ6]E8R/9L_j4$;vꔒ	yHCf .t~- csW4;QWM/O𚛎R+|♖?hP!9aZWQ#|*>Õ9^K0PcxLMFYRe PdK_2r}֢ùt>i7F`>;Ƞy.}dh.5qirF?۟[ S4$1ۇU,ѱWaϧPg=E[).mךW.;OVk6ʉw(}k"{F=U#?Q@S:mN*J-6H:w  ZGXA4sU}՟>*#՗ؿd$y9wiͣGTݠlɭcQ39A sҗO*;pi6UMp
1g΅1FHMb\ҎO҆4Y1e <XϽH&qG#XMD؍9Qu##֦t*
dϡ;1)3ަA2
Sjܮ:~bw^xiw3MZ͖lCSLW}PRjT%̡'&AxUM7204sVO5e]~tҀOZN^˚tCT}iϹ2
7haT=t	CeG_xyߕ]XSS%cX'j
=$(q95d}>RJp coR)>l^]ufC`P)l+jfHҶ(64BRqVf--%#wdɻD4g'R71 QVr	]T$@(s1p <ܡItT JjE@ G+1<Qoq$N1U_2*Jkt5Q Qǵsm7UUQOp ѫXiudDzY*HZ-ԐgAzO֣3&O?Zî쎞}VEg~6L~ZЊr	^n[e#x6htZ*NCR&$
F>湂qW"4OJNm'7p{u+5 c='O
YcQѩRѩ2RXRG=0pGZŶDIȩNceEs!zJFV>O=;~F=̝q0-94 g~_j=9c##j`[lӛ^?5 T=! =t7'(:tu)q4nB1G6) 3
:AK*=Ի0KǠZ]$Ҏ=)ǥzSwQqGMI wEj[Hj4NIlً\	|~Zbk]5>C3\͸-=;U{eOTkeR?`3T'BSsYeOHZFaG$BằaUvuTh@X'$tpF6?Uɼ#nNqԇrr:)DbN(]ɨ;9U} g oLW-!z
뎾_T?ʏO <v,PpQCzQ}o D *Wap "yӼTD *@2;țyK <C3E?ɛy?G7ʘ <e oPtSTTͿ* z
-ʤ0#kaQǥ3u(fE3u,e}oʏMWҺ.
_ <Qdl wE  <G١UCs CKѡhThU 硣SCG2ѣxTgߵM = =[vGʚl-OXC3V>/oΎdE?6}% yF
; l ?恦 ϴP ?4h:} E;>} Ef
;b} E/ح?VV~tooΎ`k} KK+Y1MkeVp6ŝko < Esz/Qj?@i(o < E8Al?_ȮIa~mr?ԁOOȶ q"&y |N Z:?MSb}ʷ)v v/WvEJ#m
k= #}cѸ!#LO5մ8\i(6/HED|Kjԁ\vz
zZ v&?W$iGܵ}M4C?fY{՘9O,~ItFjn/T-]7 
=51qVcmS}MO7(}oj/49{}Ķ>(?"\(նE{HdK	۪zEKOJ)D=Z0ZB ocjRRQ)B+s7A  
˻@j\Tj_H
A Q괚B7{iB,ENqe0Du "~Vp&jδK2cqSOR/d3OIZLaKSߐrf_0bZR>59,D+$8ga:m+6MVt95+yJ\(ؤ9K{hxfO#l0AhJ  F׭m5	 

Tc lK(Ԥ$	815^{:l!<5=2?][Ȑbw Ҫc-P&+\Q烃DAK GT,d!}]6i-YUcaT]EjNSY/=O-_6F֑c<FT_&g9P27R-9aDgcTܪ{T~lCdU'-%۳~A\F?OSvI*Ppm7ʔ
h, ON7ݵ hZ&rR+Q-O |TNorse(2ѱ+F8,^Utoŀdb
:kЧRaAzS1Eq7϶_OΓkχgCه4{oTl
	YOHl(u$0}ii]|+O51+**%)3F&x$)888MXcHt9n?.n.w

L+ER;2)n2]C$朇[9,fx=7 Eo-u0î%Ơ1x5kJ"@yS޺Ȭ4#WKxϗ^3E	[8Edȥ. 4ȩU7JXW?<#я^,HPE/١#O柷]꯹B)DoӅǤOAc/KGaQg;HC{o!Uw<. 7ɿ^zM{o y] m |?U#kqIS˰s |}Տ^S
))˰}W |Ŭc5w&TS =`TU*/>- k4_?uѺSfBjxvեfyu'G=э4趧~5^ޟb~3F?*p]	,΄?{zb0~Tc['BnӏiBOCGt;?4c?i)36
6
:E `Sz?>xb[ ŤgZ> S SM wVC - _[a mC	 h9aez~MS"q֚BZ4k *oV. J?s#G$ӏilEa 5D#iEj=#ÖMwiև?u?7(A ##?F R =fu Պģ ץQ ?KS]_/?£m
 Y+7ϐ}PԢqP?ksSRР47.UQys N^?\;?q')ɸsZ_p? 9jw
@o# ?zh/'+ .~-SZa?t??rɧ
R?L k]' 
?x~dؗ4KG3L?nѿ??-kORc^ }?Ywq =Qܨt{?O E ^
z  /SrQgeߏ ǅٺ+Hk
(֭?G5Nw3? ,I-D&kb F M8j 4sϰ{*]Ci iee =4vg^#򇱧e%$ZW_O+д?J/mI ]!L_d muމx.a=%4gZ! 
V]yA2 s 5߲'Xͥt^B>Hs◶b]GE9YQc?+Rt.UvQu]?j
.Qw+9;Fg?af/mZܞYu_Tq{u֖5?0g?' ƚ>F^[YQ_/ؓTMZQb/OdCa?jN/Q}(_)^"\Qv0O/Gٓ*<Z D7Y\ C蔾Bz%5Ive'ZJ~Tyi꿕?f2aʞ1}
.z;	W"Ю_ʏK[9=ʗs?
%8~_YԦ,<e=#oʤ[++Ѣƭ$0'݉Gu,7vyZ&'Kg^|n] t_ҝ vu4XxsN~\&ӆ?83zʳsZMuBs l;t~TT6FSp_mJv4Õc@?ǇpɭN}M+|:GR/{s [@vF:q;ܷR
OV>M+X<m;?)T݁ӟ 
|3aLj+;riS'4ܟ(RQ|= ϢAEjҏz@mEG |M+O^V T*E}5t!AJ8
w%:"/5DWbg:Ő<kJ_#kd[t3s TAWq- vc>"[qA5G>\uM.XkKfp{ⵯ~ɺ`|\W|s\E$"I G *}iJmK(]6y1o-(ctl5o[y@$ut]rIʈ2JHej]-,JG#'=e5GaS V7I 3^͸{{˟ZI8YJ.BD` oLx]iS,7+)`N?YjD\krͦ]fl= Uhw+x5"NuB995*\*ᾆ;h2kRߩUn%UgcᨓQm 8
.BzU荧X Ϭ?/i${p	@ۇ ׬õpN3%̮S6c_t1 mwf,GL*Nj6Ͻ;Fq)MFZ`D "qEHj3T1)y4LƞqM4
05!0֩iiL Si	4q*lbۛvxi*qɯۇףx#Ω+M+$>PNV.a{G
[~N̬k	YMezq_jCӿHO'>R Ͻɤɦ}
7&b'ҌJL9 sG>ϵ}i9據`'GPz+Qt7J8D p4y(x2<J2=
I>b(Ab<zN*]gi|}AS"
O@M8E!?ŏv4{wSIcsLAc\b!ُL[.IHhbTdYc0NiH.*`ć)S0ZwOʬ~&}]M?~* 2>jhM>ywg#Zz8 Slz4h~&/ea $>ӿj:Γw'Oϸ;'B+L:x_kgk=?m>v0%Pw=? E?o1}^<t[a Sz?嚟9sKbt .]N
4.{_a/Ig0
uϭ?>r?K =Gr?嬣5sF3"yg# -ZˏWVQTSS)u>/9Nz?UGڥ= 5 
鍥oL6T{y97t 1G?tL?4ӤٟfƟa{	0|oƃ2w~[gG?*im<{
0,sj?[sZC?
aД=;۷) 
3i <%$WΆϟ
'3u4;TQ C S 
\Y\ӢOXL:-f4;ϱWGы~?zt{
t , 
|.Iv"}T?H@zߓTLb .
|.Yv!#p c+޿Q/WJø0u*</)mX.;{{~BSvh?{zQ_ڋ ђ{Κ7v7F&=uF=6wKWR$qG+}q(>T:]KTfw*;tBkHN5e,Ӣ
c,;I-'~M +X^<=+7Dhj=f͊} ZϸwyBz-vɫIcoDZwҍsݖFSԻ%ǽ8MiA4p8b	Rp5O('ڐNTY?Ri.p#֢4JQN
) 4j0ғxLᶞ
B 4}  	<n !TT=I!෠TJR)>>"Q5*A,x'Ҟ	jx&]+~&\ Oz> 7 ^;Dl}?ҺO5+qo ndx'S'12J1 1 ץ =h$Y.neXe o-oOu}hH[hx@qVI}ZZ0ܟOμ#]T)tVzQP9{w.<9hBa%Uk9
:kx3c.{<<u&.P"/SLZk5E{izm++zKMr@CGpƾisڼW':֟Hqq:0+
QFV}E81pW81Zp+h$)FFAZ_wijJ:V{;f W$~,6;]?nY^CgϠpkʭ5)+!X_֢fqL5#b*&aEJZdDaϥHsL9qS>!UFAHMF

yZaZwG4N S)4zRE4)$q?JiqXoL$>(^ R??5WL&tTi$KMu
kW.TQZNssX<|rF*QWecTO^ɦ-q=j%yjӔЄ$sIQEJLB:?AYsGj2=
IXMj/O=v碱)ha(
C<OA\ ~4AJ˱4~pЛA_B?T9,t#4y>K4qO7?
ip)ǰ],ORO֛Lz8%&}4/FG&} "0dQ
9h ȢOG4sh43F}ϱ7zM1IzL;
 ~)17E4<Ě G݀ӀO &h .M49h'@4sKF(9v
KKqF 74qFz nmRgN()(ҝQPfj]֍ ԅAm@meIcޟB=hsE/5NFxq(Z_ʘ04 3FkA45j=kT٣]z"Uҡ^VoEݺ!U!lO*QP=k
ݜiwa49[`t R&Xx= &?ZϽ7ԵJE4tSIEC{Rh.eqc|?
<GN4f6~isauFgK }SCЊ\(@iiCKј~4]}&b@(_zvzniw
=iG/>(;h4 =M6RZp֘>@HzӇ֣=E82Ӂ_CS5 J	>O0n f	W<7֘?8g"@Տ
ަ7z@HiQ@g OQqHD
8WUǨQ'H=* ڧJ>~ e)oj7eZ#0O\{+u]GsTE 9i$QHBAS~t񠑜y:G*XgOǱ6LHg:Oy<Ļ~VXi]V|SIxE#dTȊ˵&%5S1،v9zriPt hTbRb&.
Z3p1GjIF⎬_/>GzʙEx:nV+xo
=\/]hmcDd:-OUb֔+9#I).rܒhmTl*[EK28t=CLr.-( 2+ӧZM%_j
_HpkӾ l EIt%VKw	Y(+4jI<|BYg(IE/:tZTޘTz<n)H4Ԅl'w
Qos)g~sC{Tgwlޑj3CB`)ΘIjHGbi:GNI>𫥎8@?
|S! fȐ ~5#>j%?44q=E'~U]oQdp=jqGs ?خ<BNխdnxa}Ep&{ ~VḯK?uE;Ms-{6=Es>iO,O]]+f5(.*W:̷v?4<~"!O?XMp{aғJ̓ҏ5 ,K:==TsUƣjz\ }R _>eܛZXK?BW.p}i1_Ώt3 U .њg_Γ͏.IIޛ!ŸfxY}M;O#|hLx6"ݞU	4lUI4qDkUnR]
\椆hK 
F2{n&z??P)Y~*)^BNJ9`kwzuXKLXsF}_:M<xaxw7sF .?K 	
tqRS?k7z :ށE<j?LGaH4TS'Sw} z ?:\KjxP:(LЧ	Pqَ蓏AFivhgP⍾>ԛqhM KzP!3?J\/@Q~t-_Z nM.hh77z>Z>Z`FIuP?:\g4s@Ҋf(րE7f)> > )8ގ}M ;M S8oQM̉FO.E&hϵfX4sIj^}(y4 .M.idz@8)R_Z v(>Ɛ/ܟ97oQ@´F 1IR:\/@ wi/lRrOZ0(
=
Rhz~m>@I*p.)hPi*wH
 _M(Ӏ jo4j@P)aA=@? $ZxDKʜ##8i0j0 =<	F9Sb#<5DA58Mi0?OʞD>i4gaTB%uA +
T!<: y:,"u_sR \Iw;J,Se :uو1ֲ'[ iFncdN{(c'/Q7e 9v&Kko:: R
$i+s}S#)u57<	OT|OIOx%\V+/{{nl.^O*F_@]ωSkAt\ɁwK=Fg3J+<)ehRirN^@A.޹7r+CMҮVkiH9+֊х7˺=AWMy"F@^'I/}
w5 xוIQ}Q:qu_@]O_b;V+yTV'[ꤚޣ!
ZT{]x#uohכ$H$=հ+,!汞O<Q]?S]aV^Dig?ZOʺ=̹Do$#?MeGnb_!5t4XԟR i<bز?q^k3Y%ձUϏ?? ZѓZ,ЗǊOb߄j?ط߷?#\Mt@CXV*6k`.5_7܎4j#ԥk*PRw;$?*b~V)lf{HiԜS($@7 )ih(- Q
(J) >󢓊,΍:LQ@:7{ |tQEoΌ
1@?&M/F=3KM, Zn4ߘ.~ ޢy=NjZ f	ԠҝR`P1sE&.L
1iǭ7Z xGaä?U>sJ.Bt :xoƩsNwS\W4x?~SƳwܩ*?$LRտ廯*\!إ9.n纡)M%[KTt r TRі8k'F?u
!ѯjyhX5Gg"?֘t:9)wiW5S݇5[C -1V!Ӯ4er?Qh尩t?:捥To0T{wo>TIP  5ȘͿ* t)}]tcuc5ɬӧI$PN?Kþ]Qbnש
*?CIЙJ
Ɠ?z&J5F̿Ut4Z1USQ~.}e&))I=19ϡ!gڌhsIFhyҌџҀ}(ƌQ@w7(-S{Qڳ(Oߥ.Ɨq&i?iyz
v (iT&=@3FsGdQ Z\@	zZ6i {RI(xw. $QIuc/*ƚM 2k.]z.<ۚ/c-xTfD:]NKp+ėr}T/%ӷj{LVr0ޕQ>ff_θ&;nX5ՙWdw-XF|IdMqY_ OdvGS#?r?&uŉ#M>-'2iZ`ΨCM>.B3Gթs>.vUs&&s>,g%Z~`m=}H lV>=҈?i{*ki>.m
E ܊9i.9w,j}(;]IzKuMrG%O[慎ʈutG#C_7[~vf 'T}vH[I~ZܞMßAE.=ONv⦒>D!ڗdCΨi>~Ro:_
Qנ?gnnG]GGE4x{(eA޾JIu$N0=.A銥1wri	UY
7J(hɤqyf'4\P!(ZJ 1F( Q1E% .=ǽ&h f (~4Q@Q ~4~Tb (Q gڀRf1F} .)1E)sI3@~fK ;4fA/O$LqF=> &M. `
(X(qGQE8PQ.( %  b0hBQ z\LH~[?:E
'kcA5 Tɯ\mVMBY2vE{\T0)W.b ^*eO2W%\T:XDnQ?*GS>Լ;X9Om?X/
2FTzlGYGROJM|j5cE3SQI: ,ts ,?Zzjm -Ϩ"%ݼvx
滔7اm <[
:zF⯆
с?yw+ǱQ`EOGS4c4;?)p=?JM?H {Q}Pj0(ڹ 6Vcނ}tm?4vL3Y;8T4\\PQ@(hу u.}4 Rǭ/vMcޒM)p=&Oir)3AKgU֭:EZum~qq[$g%>)9fڨ_ytl`=PQnWBEl	=loʍk\(ѣoeSP4moC^4 V8xv/KyIW[O?J_^Ts1F=zH?J?_fmcJcXJiѬ^_s<\@:-x~Tá۟Z\]Ϲ}E8[] nKH_Wgqܚ_&153lE-[OGc=8BݥĽ1
  F{PzTvS]"x:ΚD=C7,zM3?*

|_5/aPrORk !=[>_ﰪ!{
EwF?F]yEڟxI [=2 6GOK  Z*Z^gj+o܎x}'TkӓbtىAV᛽V/2,*_ojWfRWH+ R d 
dtڗ)0)1]SxS?Q
kOھ,дߨ jd=HhƗ4fAzK3@	 tѼw)h_Z\ނqIzSSv΍-oʌ) ъMuSI{ʘ֌ހ4QFh њ( h ((&iQs@4dQ( Ҏhi9hQGHAQLaF(
)	":unv1f~.~eAp
)s@" 3Eq@4S F))h 4Q@
њ J)sFif4Pf@	KE f)i ~4qL.h4o`iQ`r)`n1VQp~%u<P}j.ɶ)7*Wp
hC|V/G}[Cu/^/w
Sg[ 96NP_?
3?Rľ]Z)*mYXϣ9J3]#趭r
BgJG֭W35H֡}zoU`Mt(	~/8iϧ]XPaU^,MX_h*tg~4oUU?%KjSqu(X}
Lݱ+@Ӯh !Er4T:R˪; z0?;&#o.Sxwі+:1auk 5ˑP)b uqEtIj7{R@
qK@F=8A)J~4dc<Z݀;2Oաh{N:4X1F*跌v?8ESJ JPSWE!1k=胔!s
<[H{~f71R7,ţ+O~R쿙Ci~񆄢;xbj),})7;us7.(o{QJ>e݇1 Bb_lO7e_o 4{9~ϕ * =.Ov
Gry$M4ݿঘ
}Hq צ`p :֗Z@G(> i GyHBj~jnzPP=1E4SzTT|p$A!?H>} &򢝼TA:=EH+֤\c♴qH;'S Qʟ<is̿4F(i6}iXnp^QM&vڢkL6
r7Iȇ?zj|uYY]#?fzdHA+[)WZoXBx$C˕SS\ѡRFc=[h\ "ze _z˽zk9OtXG_|Boc+<WzwO6ᅧ
MܳޙEdRRbъJ 3KIK@	E.hџj (4 8*=)h 7`o\џj&|Lrݣ43@ާ.AKRmIIQ&L7fn[nU4 h曼Qz!ъLњ Z1E RZagh23.( ˷ApP:
vh͙sN
aKG(S (
8bQI1@K% RQ@F)9(4P-%- Rf4 E Q994 fњ( .i( .E њm њJ(٧#qE [ЎMhAbS#g*qf$t^jpEr:v+1XJcOdW7Uĸ
ްqhI2r>Ea8Pc>d挞:}{F^ĵg8ITB{GnB|LRk.C	)ݐB5 
t`P{sVAI&*>l?
szB}Q3*GPi+kxDNs~kf~좞,w)GD?5~8Y4mOU䧰AL3G,E>Jv/c)~E좳4Oz={F5?i~R "excL7:P>JɍP=R;~_(Et|X} ֘YV =({vHiiqI(sLB=E.&N
)828K0;P ЏƗ'ҍ4Hi KFJ (4cޗua֗ӊ)@8J	t 2h#vs@
(#@ isΐ?ZLc ;ʞ:vO{)xsJ= ~8t'zS:t 5H$N HCӃ#ޚyT	JB \9٦nC`9?3v$ќafݥ{qT渊{|Qok`sUJODKZ"b"W}55ԷZW,}벞	fa:_	6x׷O3rxURnE$G&,rI'ތsHZWM%&i3@)RRf
949(( QE QE b ( L!h%&(L&hњ(?(  Z94 A) vi?xԢ!ԜwsixGj ;R;9#?8|RQ@;Q}i`

irhؾX4 QM{1E7 v=֛wzFM d( ϵ.i( .h&ih 1h ?(
3E-))q@hɢ 3FhQE
(K!9QK3@	KҊ(sJ
據(E㽑*.i8ԚՋT+VbnzɎ(X֒:bqN+toֹtxϷҬƼ|5mGcGc?ZM|cWVniqH}k?Ee=uKr~b}/g!ļA)@RSj2=.O7qhgڍƍb( i?3J>s&sQǭfPǥ{z1Gҗpc?/vFouoRAIӨ ϥ #ɠq &#ޗ?ʗRF:яL~2{sK&3ڗ ~d7}q@44i }
(yq҃ =\\SrǦ?:P:@8ڐ# FO4~ԣ$  sJRM7qϽ.i _ҜjibGaRs@ƚ1p ?  SH?J`\
p Wf	jwQ*@8goPzI Ov;i # cן<1䜝
(vtߛӊpBJPNOST7qB@5bj~%Oϥs׉3G	9$;}vQ9k#u澣;!V+rI4)3#Y#Sr\fqE'Ҋ (4P~)Q1F(Q@RPfQ 4b 3I1F( hAQ@Q@Q )( Nh QHhϵ94w	]GSL#u8ueчnT(b1riRE Ph(@3K@	EdPEPE~ QE{
Z(Qqӿ
(Of4a ) ܿp
P7]{ӳIǠ 2u(_ :Svz1_  ;)4eoU"_\P7z -Q@KIE - QERREf
3E- &iwQ nu>fs@3I3@2)( :*,iЊSWat5i*\u6(\wL:?XJ[ƪ{m7`Q.gOƛ߽ZIw4h_בˌFe}cFƮRzSR]H_H-{zOXAiGJqqj@?J!ofң6H>0hG#4;?JLi
zg c@
?iy擑ڗ'
 6RSz^G 8yTcSFq(<d&I)~cH }Mni@4 ~/|y9h -'R߽.s#KQҏƐ-ߚ\i8N~T s
*\c4R QJ3ϯ~R$t#@

.bM/'Gm<GFƗH zdCΔy9iiA<@<sڝO|it39 ҨR=ҟ׾1H38؞)B9GHwpo\qTcN?JBE!wGָMs^W1!"k
75˻b0#k{rĒr}&h] 4 4P!i3E%04Q@isI@E%&hRf43F}3G@(恅4@;`PsE;(b!
LR@	INϭ %-4ȣFe$(\dQޙ۩(G^MOmvqRc- 0D^iږc
?*( b(QG4PZ3@	E.i3@IGj3@Q@
&
;4 Z\q@i)r(Ƞ3@	E/4f\E %E Q3@GZm3@UOO-}1NcF ;4q@
籣.?4(U=֝PG  u?)r=E&Ryk vh3ã ~h3ї5MhP1z]"Fi(Q(h&h 4@j3I3@3H10ZӃRfGt}*=1=fEx15Ʃ):uʐ9I2ڱq?::qha
8zRQsZ1◧oƗk#A6}?J\џʀZ14f =I֍'
 ^#$c)4pzʐNF1鏥(=hggAK.1;bJ\~Ͻ>AK?ր ](ڌg<т;dP0 "j:Q}>P{N) Z\Pi2qy g?(n{f8#3xsNߨn8GKfܞ	(?JI<qF1GR{J;i J8=M!p
Su҆ (`O=I9b;hJwN) t?.=})ɠ	1 ySMykN=+k䰮O[YU7&]@.%,ƻ0.zyUerI&&b+!3E%1L⒀h( f 3FM9@hϵ% ъ1@J(@h𥢒Fi3KPz)?
(i(4 QIHXL2;t6F:ULrM=bQ@2tvj\Q@ךx
?(4tS ( (A3E4f3@hȠ8QE4uQ(  S>ԼQ J)h &)h sGJ( 4Q@ (@	R )(4 QFh4f( ( Q (
(j(='3@bGF<3@ă2Fhۺ<RQ g)C/b)JRyj{
 wgGGG4 JnF4 ii'ꦀ$y]PCM 'uV#g҃Rjm^UȮCwm;2FsGU+ ҀG^3GN4 ҏ3yH1ր͑A9<IzzcP(֛֔c\iIlQ @4J' M s\q': u=sp=0h vA)^=@pJS4ug?H:{K"nQN( }hJt
{zP<6}gqR g )>)E#j@dR34z@=)H#)p# \לC(l/=1J)7|9T}h0G5^KČ¨O ')&6Ü놦<FNdrQJ̟^$khZ(fc\6 3.33RMtC
v,_^ÞN*Q]$FwaIEE њ?*J \QE Ҋ 3EPAɣ&Rњ(AE 3Fh]Gz vhDӎg~'.SQSDL~=cU@
Lܱj\j D<RG@	QKL))sFh bL ( QE b($ ( 8aF} f9
;њ; s3 ( (4 qIKF()h
(
(@J)hPEPEPEP(
( (@h
 (
9 ( (P(QE Q@4sE QE RsG4 f3@)( .7bf
+э;4s@
i"AihzboƎ}
8䌐G|漓C󣓑ގZhax&H?wg{R>F{1>ZL9u sRv+`Ӈ+T gF=Mgw1L{3AIF:|/;Rb8֐=riAC>{RހOҗ'Ҕîќ   }/SjM^w@LP@?&Olu O=FB(>\iO ) =1K  \ہ =ϵ)ݚ@(ls? 㝦?B#)w(,GTgH
d]j?rؗ470FeJ,ߝs7ZĒY\I!cT0Y<Jmd#?d45TMq4CBǒi5fci2i2i2iHM%- &M^=(4(f ^)(> ~sFh sE)h(&Gz Z:Rn0 N:͞ p&2ޣ3zRIjEDǒjlڗ 1b; Q- Rb \RbE
)(`) R
8Q@2})E  -&)?*0c b֎h4 (Q:Q@	E.y4 -%.
 %RRE QE b( ( 4Q@} 3Fh撊 Z?*)3@E' RQFy( ~PE4 RI(qI(bQ- !% 'E- RPfҏ
:E QFh PR)(h%.}@u QQ.M %◚NhYj^O$izcA')>¼pr{~BpG^޴;v9&1OЃFW=N)(#;q#4 u8:R2vHOP Κ ӝ١s	ǹ*>@q #`P{mǶM rߗ/HTF=X} J >sƗzcN8xۃF?
:4Ӹp2O.G4_c#Ӛ]G:nJ*pzx ɹp;=};R E.=끊 S9uiNr iiۙ&hiϭ;z8 TA];g
 .?@e'8dg 擝)،KCO<T~jFN	 f]x 
i#"=~Qdk+>Ʈ4ڞ8Fc88`&F`OK!;X};9152sOؿuH
y]Y4uF
;қだi89 vqFAMihsIF8Fh 4Q ('K ?J?
.}(.i3@f )(
.h E4i(LH[RzSpJLdFf'y`v~vjlK@NsGJZ(J(h)(?( v( Q 1EZL њ (bRi(4tsGZ:4:@.}ϵ&})s`cFr;v
NE.
EP3Fy ( (9 `E QE QE QKG@	EQE(h1Eh(i( Q(@f4 t^ QG84PJ)( RPIu ( Q@4PQj_ Lњ?( (( }(( .(  b/i4:S]1MӺ RĖˎL	17);[>{mB$!bSwy)mw#"Ru>(=ޕm5MϛP$G
T~oe>k[H_h^.d\O|7G(*ƧsyE)ԮHmτΑ"p*:6k/,(fa~^I1
Ou>A{S:~>mN赋mV$@!IFd
r<k'ZMPM[	A
H sI
M9EH2.=
h$˃o  h2}+-xvŴF9sBhv9>uJ5;s]*Kh[f]+q<[+1㯮+*/vlQՙc<AG {򢃩\;kM61Kyig#ΡS9 '灑PEc5c{smo}itB '\wv<3܌4.t7&?ݫMmV
#(ˏ9zZUr\[XWe2cuʭq:;.ݧ i] ([_]%QpEt$I m$#:[dy?if
N3ܜc jzY/T~8קj=gLRK$ G8r!C3R$?vh v /"Ԓ[).IX8<>~>!-"Գ+bC`)=\11?@1NAB8ZO=ݒY^AsmxΑme
2Uγ/-OAo}
À̃pQߨڗ#Ҟ5ksgN_.PwBT/t[
ŬB#}uv
g$ ShUgW
41 yzE\0W'E.pO#k:\Is=F/.Nʐ9uk>"굕s@!_VKo"r)p ϒ㿷5Q|t lqڭ_*Cckq{dϬ\yI`
bLǪ@ez6
|g%EgltQ[$MYd\a^{GM6ю*fBlnyeiO8\Zڶ	;p9<RZjUt(:\
$mq\wrQ~TߵK#x,^=ŭo.܅e<>.4:ꓺѵHH>}GN[ʺicIׅ1H+<ӶkWĚ얚/d"ejs۾hWڤ/eo๥MIm9B/Vfͯj&) H[j(KaL
foQSMv<Iyo
嶣MBXe[j/g񴹮'&
 KG{Ҹe/e]Me95( ԯbټnwP-3P9Nl^9K[k;SG'.8.K*'Һ]/i[2ZyI/̃;uV)3FiZCM.R)(	3I
Ґ#Fdf
rR @ۮiMEvcڌњ`QFh E@	E/E %@	KQ@IF(4RR
CFh QE f% 裭ޏj CE/4dfP0ڊ){ 4 sFh
(? J((4Ҋ \Ҏ(ڊ ((( QE(4g4 斀4f4f#h@'KE %zR֎h3G4bƎ1ǭ QF(@isI @E%2hϭPPzъ( ( (4PIZ?
 :J)h 
))h Q(PGZ(H F8}ibf	Fipih4gڎh;?ʫ+?2T2FVlt-i͵d12pf:|'z4OdΉ|Cڭ]I-)I di[aֶew8$pA dk iW'<'N:L _j|JfMLfIbrNG?Bt~=o$9U6| Zw uOԹ˷4/3ɻd"dPͣB 9f9~ ^|O֪ f\8 x4ےz' ֣
A7ϸOjꚫ][DF8kr}*ҧ<H46VW{־#Jo8]9dz9|ÚRS׷VڄWPۤhD\eҸt m"ѭQlz+?龄ڤizee̶I!+
V߈4J]v9Q_\G<2,AapƱ?	QM Q>A]ō:\[kJzdz+v={Mt3{q"wUXC"y=E` gN?ڥl Z5殯^wv	C˩ڗ\
03_o֬YM&S	:;3?a f { Gtޱ Ts6u")kx./.5R8l1:v
Gmy<1@<VOl tLz< K|ơ[y􏲋넻f@B sjYAMjZjc 8m\6ӥ\d=S_Oum >p7|GiXZYIg@I
.x cz< {To  B\rT4֤iŖZF>y!#
 nZLt߻l-{wH !~=뎖Y G3#ZPV"6~;oFBʈr:6#S5o_j
?7^Ig='ٟV7sYvlmWpK~aHmd-%щl2	eoQN/QQ50k˱''j'=:Ogs5B[?ڿNGwyu}t7N$Y׊Cºub+`w
>'VF|=[iA>,sJ|2om%h'h~T}ជh猊uekB+HQszQ`:GL</<oLF<ƑFU\V~%Z!3<`CO\1[J;E"tb}0HY'$X
=VR}&\,uwAVmJN@9W~&欐jϯZ>;	|iou$qZTFOz={ea5DsIH_y1֩E!QݏY[kvw˫K	4h q}5N?iVon/|]H˵d^F	pf ?mեŕ]ŭmHx=*K,m}Kb7v{{IvH 5Sv"i:e9m XlHXq¹&-0)cJxP2 M=ah` ߅&hZ)? ZOƎfJ( .h> QG֒
ZJ( Q@Q@i(4}i( h~`w4)sIE .}IZ J)sFh );tҊZ;֏ƃH8$zQEh  =(h qE% qIG@ނqHP)
/h E Q ( ?))y4g({EZ\ &(KI@;u@=h fIP:I ?
@-&yJ (
9Q Q( K@4ϵ f)({E (
JZ(  ( CE-% 񢎔 QGE 撗J
'4P~4fփh


================================================================================
FILE: app/public/images/ptfs-card.jpg
================================================================================

 JFIF       C 		

 $.' ",#(7),01444'9=82<.342 C			

2!!22222222222222222222222222222222222222222222222222  @"            	
    } !1AQa"q2#BR$3br	
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz        	
   w !1AQaq"2B	#3Rbr
$4%&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz   ? ((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((((@?¬ V?ƻmKQk7XP\{
o}]E<#]ǐkזBW{3 W? 'h U? 'kUI.+,`_S)m.B&7E\T?b#ª ߓ4« ߃5;Ūݪ($o²ƫ{ =G(Te[9Us Z/Ɠ]b 'k:}d؛@Ywzg֏cC{lGs Ws AX ?U Rƻ>co$ʃ dP&- #FW`~\Gs Yu AH ?VRƻmA*qoo#
#.5}F[#O18i=`qn)?G*
C ~}&ؔ4e)`0ƍ&xn߈{LO)?G*
C ~Vڕnԕ`PdSNx? ^W\R/ƏUjzb>lGRPșb+vy*
 ~O 
ߣ5t_T؟y*
 ~O 

 ~Oפъ>G}nsͿWO AX ?WO AX QG(Vy* +?I 

 ~OץQG(y* +?G* +?^F(6 _?b 'h _?b 'kqIG(y+	 +?I 

 ~Oפb[V R/ƏVH&)N`n ° _ n?)?^ES>[ g _ n?)?^ES>[n?)?I 
ߣ5}N`n² _ ?)?^J>G}rsYO AH ?YO AH j(9 gq AH OVwF}N`n ³ ? '?^IOt{+w< Gh iq A8 lRQ:=uu 
p ߣ4´ _ z-}N`nµqߣ4µqߣ5蘢[V N/Ɨ C[VR/ƏVN/ƽ[VN?ƏVN?ƽw<Aw< m/ 'kh:=0n¶q ߓ4  z(:=0n ·q ߣ4·q ߣ54Sߘ}rsϿ[ A8  ?[ A8  J>G[ V N?ƏV N?ƽ>G[ W N?ƏW M? ERp% ߓ4¸i ~OESp ߓ4¸q ߓ5GԨu+'?I 
o	 ~נQGԨX}ns \M A8  ?\M A8  
(ߘ}ns \M A8  ?\K A8  
(ߘ}ns \M A8  ?\M A8  
(ߋy +'?G+ %?^ERaP.20PLG5 
F ƻM	7C]qbhS:8&x)A ~h #u A?ƽGG;<s` v ?Hvoc"vx) 4 ^E9.;* c WG"vx)C   c WQO;<w c Q 
B 1 بȃ; 
B 1  !q A UTQȃ; 
B 1  !s A UTQȃ; 
B 1  !s A UTQȃ; 
B 9 ?H]vocDCEƟ:ڴNJȄU?[O A8 /d'?XҔhૉ _ /+i'?^Ei:=3?Vy+i'?G+i'?^(ߘ}ns[M A8  ?[K AH  *(ߘ}nsZ A8  _V R?ƽQ:=0n µq ߓ4µqߣ5tb+w<  C-S>[' _ & _ z}N`n´ߣ4´qߣ5Q:=땻w 
qߣ4³ߣ5蔴}N`n ³ߓ4³ߓ5Q:=땻w 

E ~ 

E ~עR:=uu 

E ~ 

E ~עGVy+) )?G+) )?^E/\VW e?" Gkht{+w< " GkѨt{+w<" Gh cq AH z(8 cq AH ?XR/ƽ>G}rs?X\R/ƏVH\V" Gkt{땻o 
ߣ4° _ zEG}rs X\R/ƏVA43 5/OԼ5_k]r?.)?G+	 ~_/O/O|?o>+	 ~ 
 ߣ5
f_࿙ٗ}4?o*
C ~ 
ߣ5mM >OG_|?o=#r)?G*
C ~_'_ m > }>C/o*
C ~ 
 ߣ5 m > }? u Wb;G 
 ߣ4¯ c'i? uWb;G 
p߶u m]]5vS=Bnҽ #7^ \5>N\EN2 Pd}qǖ?uMjRY2ZiP!*
uFJ164{,f<M}pǃ)	x<nުҺԒ}1&e[\JT9^23ǷZο.-|M+9wùqDy.\hO\ gx3|j7Y>Dhd7@R@ "9{mEycݝ$ۭT[SN٭#yՖ0::sN*ѰSuwzûr][
pxǓW
K$Ls?&`ͭVSoI^yq +Q"Mػ|ԌW#km
> NPI$PǮ{r)U-6@ qe"iݮ~[\-L$+GpjO  	#}s屝/Zj}iocidV3:g=Y=&tk.V)x$)-߬6֨־%兕0=r߅_o.3 ,d$q[ Uo3Wn~vkza'=) mtZ?\+Kƴ_Ju%n`%PbR@PRSI@	INLSQ6Z()ԘRPRSF(RLchb J J1KE 6Z(1Iu )h %%-JJu% % )Ԕ (R@	IK1@	F)qF)n(;bE; J(aF)hbR LQK([+6t,]Us~\#].yϑWbQKF\HR>m> R>m> SJ6J@6vFLNhiNhhS6.E;ai6vFE<J?{n"oxd = 	^#J)hDPE-BQK) QKE %PbPQKE %-J)ihR@	KE- %	KE-RQK1@ R@	E- ǇUk >Ȝ έk??c  :f2}_yo0P2I)M3O\QRVV[bFTFEV(?f\/F13j>E> iT'( [x/R6 :S\zZqޓ؀ӂ0Gb(ǵkI0Y; :h$Gj4LֽzUKV`BOsPm-bEǡ
RnF I,GrO96 }FPoYp8,
z`t1GL_ ~EE[ 1uN|?gؼ*ײ&K)W/
!nQvj~!Oi]Y,:#UZô÷:@GW(d1\#+RC*sI%gj QPVq\;KX g޲7v/34ľ	,ٷ4SHQ5K
XC%hfD fPK	-E\gn=XYZMm:LJ0{Y:&	sLmWU  t&I
Z]-ŌsLI$p:zUMkÉlKAy)U+օͮiM[Zk$h3H$ 9U[?:qXivMʅ;SMs
ᑑEvl鿷%*L|؊?dָ#<J.eCK,QۢRMuNAC>ͮ\O4bB=2(5k2*%!vyW{>WEʓ:3m״gR-춷U<<x_Qԭ,F5-a{k]X#	i\jp5J4Z#$I~ivgtmsq<`F@zz[jTXI$g%
VNer֩ccXm՜.+ IOis}OR>VkI"D_`䃜{zekuuX?Qz5hYI([恢,TYzmc"dy+ucP~$֎?^t:?]9]9Ģ%(%%- R@
PbbPRRъ JJZ(R@	JZ())h)R@	IKE % R LRb J)i)R@	E QKE %PbZJ J)hZ((.( &(- b J(Z(x įw?ʺ1X\]޿^V-~)h( ( ) QE( ( ( (5"1¨4A^֔%EI(EɜɻcG;UzZ+I%dxĢbJ)hBR\PbR@RQZZ%P!(-- %%P Z%PE PRF(  QKE R@	E-f? Z'ֵ 1U/H,āR>ҭ9}j+O?N_uXc8b6k|O\R֎8SFӵe
Ӱfd<v=-!S8>uHN)vFTCv\uV}Sܨcf7g0ysj1ӭsFCw;kx+V3Z'۝,/Rg_c)
Kַʹ^GG^.$鹩SZZ4޷^6i9q寿ZӔ."֌Mp+3I 5qQ:3 L5M҉>lCgҥ L S]X[hhl'̕0xڕ45*CF{!aKǕ$`09?WM6K
BP12yJ=몾uԎ=
B󁁀+e׷Q4vfaRIzT7cQAsi i]وQ>iwk$J@DWR2?C]g!Vӵ+n,\d26=ꮳaot}9hO*7R9a'.8moo}p?wska]^)Ŵl2S9kb`1-<<%څ[ZK#!rdxCVἏΆryqھ-/; {5<@?l/t*xdG#fդ7RK4P" E=)-7PJ"16=2rֱCK-u1Ws$>Zg%NiQEQ"bZ(_si_֔3)qEl`%P!(E-%0
JZ((
JZ((RS((AIKE JJu% %%: R⒀ZJ (`%PQE R@
 J())h J)i( Z())Ԙ JJu% %-PQKE % QEDb=E /kn)Ŗ}Lcyῄ7(((aER ( ( ( (\fto/d?/O[5O/=z+Ӳsg2ڂ\Q]R JZ)h(
1E- %PR JZ)h(	E-%.( JZ(Z()hmfa2݇ozMM@$M;ʓykӴtGfė,s{
\o`ݽqL KM < Mvꋹ}'i~?5bEq <$ M/焟ɮ_[}rc?'i~u >5GTs y?w} y?*hvGkIh
RrOm>_#jÆ%~$rJLa~UI=*WWⵌ$=HW^
s#ʫ9vp@
Yug"{Y32{sqGI[Ln'
:T?!^ӥ խF#(JTbNefۨ²\29V 	CnUÜ-qYm[۳3]XSr5r7՛aQ5}~W#o<SMQQvw$n u^W3 =;TtQZ:~G \ 'SZ#7:ܔCa^꺎׳G$TNfii!LV7C9F}p{/~7ڤB)lS>KKvsW5R5a|~E6Ib厫ir<[9{2tnn2Z,?s叐Hb(Jw))h!(=AuG 9?ήu~%8VQKE %%:Z())hBQKI@%-%1%- QE %PRR%J)i(RPQKE 6Z(R@	E- )hQKE %%.(PhZ())hQKE %PRbI@	E- QE %PQKE % QZ1@	E-xX W f Fjyῄ(
(((0(QE QE(`U
b,I>U1rj(IF.L[;_>Q+ٌTR<iI݅RJ)h %-PE- R@	KE- (QK()hRQZ1@	ZZ1@	E.(+OIѧ&)CUQ ӴۍJE>=4}..?~Cտ=6mAԟSSו_h=ZuM]!R=Es`]`6 cXdTRVfQE QE
)h(O)G5_k?Um;ζ<Q   8DT~&sGSRLXdVs)]G;c<+MT^]& Sݜ00}Pܪ;):֎ϸBn.]v5<G/5!
{9^HJ,)# p0>-q哏Ni7\F;gKB8rZԪKF*>դ/ 9j.VeQSݺI()@ TI~AUt
T5'ѩu*?$?MeYya >??)-	+{  E'# ?- |\i
OoQ "V&
 4<ȣEn >ȣ  G#i }? G#  "F&
  Ȥ ~?QD¢#  E ? |9{HUhV0Q*
EvD暲Iu1KE %&)Ԕ RPQKIL
JZ())h!( JLS((%%;QZJ LRS1@RPQKE(( JJu%ILbQKI@PQKE %%:Ph J)hъu▊ JJu&((RPbR@</C\Ee^Y?:?¸a9#&0:+?:?gP Y}N}ѧ!ٝ} l  GRl_  GQ9Avg_Er ߐ 
? !}N}}r\ (ֿ St\fuW} ?/Q} ?/Q9AvgaEq ڗ%'I9Av;+Ӿ ?:?OΏϸ}r=Ɗ_ /R T}N]vU7_j`15K }Ujކ˙
iT&(A(E-%  J)hZ( Z J)hbRъ\PQK( bb~7;n=V3՝J"ӕGh]MEe-o1E
)ʡT*
 kɭZU^1
(6
ļ{n|YR9˹-HQWr,2~\,2G\,2qE(~\v0|N3u~؁#qjxAK ]W筏з"zD{1J'V^tw5JG$ٕ8 JIѨ1,@jG0պ˒/fRy6O_Zq@`AVkk:bcx#jԨ%k9*rWviJju:NN;	Z($N~* !>V !5OR𳦢ԁ(E- RPQKE %%:	IN mPQKE 6Z)Phb RPRRъ`% R@RP1))ԔJ)h((I@	IN%:JJv)(( RP!(% RR@	IKE0bR@
 J)i1@	E.( %b ( J)h J)h ( (	KE QE( () Q@Z( ( bZZ J)hBQKK@	E- QKEZ1@PRK@	E-JpɥHGTE,p ]qt\u' ^Z4ٵ2'BmLT?]=%-y5*JZ8VQE#2c;Zs{G'zT77.U>TMUQ%	ED	E-% ( ( ( ?5kG5M8eU߅M@PΩҢi]QԒe.OΧR4?ʨ-jiX=X֮}RշCe>C+,$d>ղE&*b6Xo;_vR
Z(=
 W<IEXU]#C/jUtѩuFYl7G oʺZ>GOs<? &JY}ꋹy2 7 M'.?տk
/U+z{(g+=䁽=GVЭNT1Z()1N
Q m%:ZJ J)hQE b3FhSK1@
`6Z())ؤP!RLPhJLS()1NIN )hBRbILPhmQ mRbRPQZ(R@	E- )أ )qF((RPQKE0R@	)hn)qK1@	E.( %Ģb	E.( u%
)h % R@	E-bQv( %JZZ1@	)ih(J1K(bQZ1HBb%
(- %Kom-(]۠]8kt*
27ߐ?j½uIyР"
DM@.H/j(&ss|=xEAr1EZaWOJI4=sYsXvv1$mZV3nE%-1Q@Q@Q@((*֩9X#0rvDNqKLr _ƹ8nX(yI[SCB?X9 ׮a]ާJꢶÃ}:_6?L wG פ sG ׭7,;m9'D2 {PĈ@c
 9 קc^+KJ\Sܵ | 9 ףy ?<CkO(#  }
 < zOG?  %9!ܵ 5M  s9 ץ.'y9 ףy ?ثCy
#CG<5X s Wl4F0(w⓳=LמzaEPL9z
`EEg|[YMN7*&S=3kyk2{WT+FGJeZJZ+S( JLR@	IN
Pi1NIN%Z)J)i((1N7RLN %%:Z((- QZ(R`6Z()1N% &(JLSF(J&(-m(QLRbRъ LQZ(1F)hъ n(b ;bE;b	F)qF((.( J)bE;J1K1@Q m1@	F)h\Q&)qKF) RR@	1KE %-J)hbR@(.( %.(QK((åzdM$oU4z.flޱ/j,d4eE, ;͹irOW=Ms{'=袩+(!( Z(
(
ZJZ ))iUIq[.doj-??ҲؖbI'5O޲9*u	rOU(#dpRRRTHR bBZ( Z%-PE-- %b:5}Wޡ͉_z.&WޘQEaSisEEh *c8ޢgn_U+XULgF29RVݜ/Wk NWc\*)7f6Z*ĤRb\RPQKE &))h0E:E-J1KE 7bI@	INBQZ()ؤ!S(R LRb%%: mE.((S0JumRQLъZ1@	LSK((\Q JJ\Q@	E- R@	F)h&)PhQ@
J`%P1KE %PQKER&(Z\PhbPQKKHPbZ(1K)h1F)h %bu&(QK( 	E- Q@ZZ(RiW	jyـ;,<V5{D
M'l
r| G/?s닱Q\/ =4}Qc2O ѣOꏸEF~t}Uc}?TyE>'t}S>Ө#W-h揪y?o]j1[WtZǞ[̍@:
F0syT`RPQKE %PE- &( @%-o|ߥYr=EbSG?)4fG~zHqqySw:aVْQIEAQ@.}i(qXZ1G-+^r{V%ljGaYC8q/)b9KF(QN%01N&)Ԕ :S: n(:E: m%:	Iu QZ())آE.( % bE:1KF(E 7Rъ6v)(bF)qE &(- QZ1@	)qE 6Z)R@
Q n(:PqF)qF(1F)h &(- 1NF)PqKZ(1F)qF(1E.( %Rbu 1N SF(PQ\RF)آb LQZ1@	E.)i RP!(( P1(.(1E.)qH (
)qE %-JZ1K@	F)hZ()h@%PQK((PbR	KKE % R@PRRQ<R@Gy*pNjw?>Eg*Q+&_Γϋz/Y8kv5_ΏC =(/KtizY4}j] =W]:ʵ1Gq}j],H#pl?c	ݍRL mE;n(bJLSE 6S1@
;b
1@((SI@	IN%0I@	E.(Rbu% %P!R@ĤQ@
PQv)1@
b)Q\Q J)qE %%;b1NR LQKF((bbbPQN&(1F)أ 1N&((.)q@
Q@
1@	F)qF(1E-- 6S▖ J)h %Q m.)qF((.(%)n)qKK LQ\Q J)آRъ JZ)h(E.( %-.( %-.(R)h
)h b	\R@	F)hbbR@	)ih( .(1H RZZ umPh: m%:P1SI@ JJZ()1KE0I@	)h 7bI@	LSRLPI_U
+*qi#(6웟?O웏?:)6Y}bf V e\zKq꟝o"o ?싏G dO :{yՠbc 3G4 ߏ5F(@ƛfӦ8qoj~;B1Jڸl|ʖ	!mkc#)Cr)hd6\Q@
(()h 6v)1@ĢS))PqE:Ph;qF)أn(.( 6SF(bPRb())PqGQ@
SF(Q n(;b1NSF(Q.bQ.1F)أ QV-`3E@UV5+r;XޕQ^'1]f6AVZ5i5`z
\J>T9MѴ tUzQK^AO3?.^CoK򮪊><W7G oʺ(T][7G oʺ(T]_ ʓyk֟`rL K <5G֟`sD G/MEZ}ꋹ̘dPIʚf+\oJ:Zi
.(L	KKE %ъv( &(b LQZ1@	KKE PbR )أ R@	1N bJ)ihbE.( %QKK n(:PiiqK n(;bbE &(1H.(:RQv( 6J mQ m
J n(Q@
: m%;b
bZ))hcO\E]s}unvx
z-t۹ۆTm}KtT>yyW9MEC7>&E淠oA@j?5sz
ějTob޴&+5dRӨ2tL'r w$c+2FW9ja&&(O=e{0PSM]n-;1bJb)Phhb n(.(&)PqE: m1@
b1N" 1NSF(Rb1@
Qc1NSF) RbR J(b1Obb5|;FdF 65aD J\s^}y^=,<mI>(hk#aSѶ)hEQK\mM %Mh(FQNF.hF(	AiqE{iGW=讝"r\+
81bWI&(: LQ\Q J1NiiqK n(;bb1@	)ihRRъ LQ\RKNN R	E.(b n)qKE %J)أ Rn)qK\PqF)PbR Rb	1N	(bR1N&(bg$J}M?>_'Srzا1W?tgK}Xw>_-#HG{))bx>L]jۍLP!J JJv(qE- ;b
RPRSF(SF(x%\7 
ebFF8ʊX5z+;[<J'\+DRQYEPEPBQETM"@a<<ZUn.pՙϲ$0 Ɠ4̸uEfOi$<=EuBJb(;b11Nъv(!bSQ e Qv( 7SF(Q n)1O&(1@
bP1F)أn(;b
&)f(;b)أ )أ2;V
3~gS`[vB@9梣j:Њg@r:Zdd9W@Am-.( &(;b1N.(7jiA R)ɳ؊劏`(QE QE QE( ( (nu_ T ;1]"J*?A =S}sG%!  }Q?~tr
[ǹo!V==ki^yU*.Nc
O;H]v)qEv<wcqF)أn)qKZ`7bE bbb RPbSE 6]>c,{ZވV,./[IsiEGֺE
 : 8S:g3.!}l;-31 kb ZYӶ殅4(f/?/b SU)YcOC1?~T٫ =Wϸ{}Yfdqޣ[ϪꃼS8j+I7b1THRSE &(.)q@
bPb\R
bPQv( 7 7 )n)qKF(J)أ7b1@-5ANG=QEIQPb{hp}EOIT[{ȏ5]tEjUks)P'SF"9fa:N:bQ1Q n(.( 6v)()1N)Ԕ RL;P\ }
]98oVn(g*q+N斲bH~qzUدc~?sN\1(Edn-%PES
H"E<7+WGcYF]H5L4vVЬ9PRhLQ=GOQU]Q8f3bLS$n(;b1Np)أ\SF(
Rb
-.(1N Qv)1@	1K1@	LSF(1@
&)آ
bPqF)أ Qv( _
^?c^^a]zB6 |!)D?"ksxckuQD.)qE %Mh CѤP:=hΔc5ʃTn_}̇ykc{Q@(( J)i(j9H".߀4k*qTmCiyST{kxEOʋy]Koޭ)p+xObkQ؟%Mp1s >jwW9Qv(1
bPqE;b1N 7.(F(.)q@	E.)qHUWw\*k8$hGa\vq +q-Xr\u!מ8wr޻ph\3G=qU*COWqw	F*.⏍ۛUIoe/Z4#)քE0dNySQ]Q\&Q#qK\Q LQ\R1NbbSE bPbSF(.( &(bPbRPRR1F)qK h#oժ+I/Az~+JPjN:=+#F5"ܷʥkd=2*&qЃNdڤv$#>Shzx$P駱J[-UYuzT84ZMKOSQ'K+=*9=J_=?Q<{UgjJtGsZSM=LI5dGJv(ls
bPhb Q mPh:`7bPqF)آ
bZ1@i"?+ڮE|ăi*8sHU66Rw<J1+	Qkc.QH2V&
(A""u8ֵdn\O;n(;b1NSF()أ Qv(01O&(?SF(Q n)1O&(Q n)1Oc1F)أ Qv)q@bSF(. #C5x,ψ$Ѿ:o͟?pWW\æ΍tqWcU^F)أ1N1F\r1F(C?yV^}NF CQ(^o?:?yΨQa=N7 cM uKbew.i_Ώ7 K1OC{zr4j֟$6*Ƽ±[~8qXF0m#Z5g9٥-qTqZsFPr?!YwIFiM%Uɰf \Xm	ٛv?Ҥ$s#n#̓C1F)أ\R Qv( 7b1@	1KE &(: n)qK1@	1N \R5)8Sӗ\VDucQT'vk
MNJi#Vv)qKT4>+>2_>T95ZI1ǠLQc"Ug-R3E;b)أ b1N !Q J1K1@	1N  7b1H▗bRڗ"EsèъMԹ Ɖځ4Rъ8&)hqE:1N 7b1@S0F)h &)1N1NbSI`6v(Iv( 7b1@
%;PqE;~ Qv( "S$jw7oΓdƛ[1|ѿ:<~tQ,]F 1F(;ϛz7G7oΙF(;ϗz7QNOZv))m{QwQ~)1@SF(?b1Nъv( 3SI`7b1Ef(?SF 7bF(R1NQ f(?SE 7?TzFʽgeUl?o|7l_Cb/%|lmb&C1F)أ Q n(;SF=b1@	1K\PqW\/TF*e%fT$ڄ,ř'}^(e mm7xU1G3BK-"ݚF,$Us)7SK1?b.)أ Qv( 7b1@SKj n(;b\SF(Q@7bPqE;bv(\Rъ LQN!bP1Q n)qK\PqK\Q LQv( &(.)qHv( &)1N.(Qv( &(-bPbRR(b,ooZ<Ⱦg_1h֓Qdϸc?%%; }փ#x9qRb#qF)آ1Nf(:P!LP(bSQ n(bPqF)آbPqF)آF)أm&)أ Qv( 7b1En(:PqI~)1@
bPqI~)1@
bPqIOC1F)أn)1ObSF(;b1O3b1Ef(;bRb1@bPqF)أ Qv( 7b1@.)أ Qv)q@PLSI`%yĻ/&~@خS19OН7e ıic<]rdn{u8ɭ1N.)bP1 Qv( 7b1@
bRQ n(;b1NQ n(;b1N 7b1@
bPqF)أ Qv)q@.)أ R❊1HSF(Q7bPqF)آ) R▌PbR Qv( 7bK7b1@
.(Q@
QNNbbSF(; (1F)hbRPQK\PhbPb1F)h&)b)Ԕ7bF(?bI n(;!1Iv( 3bP1F= 7SF(Xn(;bRbLS
&)f)1O3b1Ef(bPqE;Q\QqF)آ)PqI}bSF(Qv( 3bLSQ n(;bLSI@7bF,NO$U&?濕f4WEmy1 q*_*?/KڮbQTyiAw-?.AwݫQzʏm?Xz
q}t4Ur]##a7l3cڟ1@3b1@[ۉdQe['9)huҧ)~TaoʮK~bX(\P?UZ28ɡ1^s:E}>w% ~ Zz߉,Z}>u?*?sqDl2Ol\/K]:̈m wG1IrtY{LQ~I(vbWCb1GJiS67b\P!Q n(;b1NSK f)qNSF(R\SF) Qv(aRRQhbPqKv)q@Xf(?bf(?bSF(Xn(;b1N.) RN,7bF(R❊((1F)iq@
b LQZ1@XLQNQK1@	F)آbb)qEb1Q LQ\R1NSF(.(IBb\Q@	1KE 7S 7)Qu%E:qF)qF(1F)qF(
bP1N,(ޗE-M٧*!}=jJ.Õ}&Vh>`E=vl'ԉp+SI6SI7b1@Xn(;bmCqF)\bSъ.qF)أ\bSF)Q~)1E1F) Q~(Q.1F)أf##uZdֳ1OGdꍡV=|jNpjjɫnt)' 3ڏ3ڛ1Hgg6Po&(3ڐI(B}
gʞէsZSn0kbQ\SF(71aU'Z)i*ȳi֪أJ<f01EEZY݌"l報>B1+&odJߜY#J{-y^G9!kNXgҽ-u
|
kG5/V3l)Ej[)2*AS=HFg5*CbOSIhsKVQ}&)7f͍lw5+F؁aԱ& $~tdΦFj˚]Ώg0	:w
\{ՊVQv)qZ\qF)أ\,7b1EqF)أ )أ❊1En(;bQ~)pT'8=MO% JuvF&ʉc}T~DuGԙVȋɏ*?عWb?*?< *J(*3ɏ%?)gڋYIGR r@u3M]ʘ(lsXn(.( &)1ObQ.qF)إR⋀Q~(+R,7b1@
bPbSF(Q LQK\R1KK n(:`7bE R\RPb\cqE.(	1F)أ%Xn(:P+
RPb1@
Rb1NqI~( 3bLP+
bPqF)أ\SF(
޴bP1C(ڛ1Fv?ǽGE3
ke1E)a;b1NqF)أ Qv( 7bTR-})sأgbRk)s#*U-}Z v`e\RbkI寥ʸoOAGs#)U-)|FRf$=O\LT٦bj1F)0)أ R\Q@&Oh4b'td\Q@?&[.(oSI֟1@&)!Q.1F) )أ P\Qq`Z?7	qУ#ؗ$` 皇?k nxVty1@20+JR_4ݬmE69\kf6+G^s^'xO[~do
*sۑ⽵H<ҝ⮬bSqQsQ n(;b1Nap0F(! 41fĚJSH
cIzʑ"  )em.M~E8X?_zG/0)L(?mnaa)1EqF)أ\S@p9yOWU 4TG;fû	̓7\RԷԴq{
ij^z74FI#5cP:U$ު>h~L<sxъ*SIih 2SI&(.( 7mޔ\v".*_,QJ.z'=\RTܯՂA3* }錻[9e)0͑M6L1K1T@ 7b1@
bQq.)qK@7b1@
bPqF)أ RbQ n)qK\PqF)أ7b1@
bP	1KE;Qu RbE
1@Xn)1NVbPE;bXmRbRPbbSF(1INVIN,7b1@Xf(?,7b1LSF(SF
aQ tP)~G-34qآ)wRŢpx.xx4мњMޓxq٣4ޚ0X.<?JE;bbSF)qF)أSF=RbbPLSYZnXM"Mݐx{YmAgT#|P?#{TjKW-U Vg20iHϱ1Y1K|fY?Ҭ&ob {#D8It/b^IH*`C?CUqXLQv)q@Xf(;LPNXU]!yǽLʮT X|S慩ɦK;\DǸ)pO*ꤎ)זo]sM"Iz[nUT0HȮ7yҊTdw׾+|U'pD+pA^orI^!kѴ]<Y/11 J#+*7g:Ȕ,`?Z8TqbRLU~qEa1F*	5(]YU\g['RCQo1X9I
&|z&?v
\)RtXI<[?;-_vbjQ
cSbZ3sVs+[EnkָXc1jJʮB]Ʃ"@i[?JyfR\mFcHLS1F)qK -<bcHv>|ԙ֑wYQM}Sq@booj_11F)+SF)f)qNCqF)أ Qv)qEa;b9
IR2njV0ZsRnoZ,Ĵ<S2OzJ,+cv)1L1F)qK n(;b1Nv(aQQ\Qa1F)qK.1NaQqF)أb1@Xn)qKKqF)Qp1Nn(:PF)أ%Xm(
 QLu%R@Xn(;,% RQKF(X+:zqp!~uXL uD>7uU`ci1$g%}+\Ef9ZhLvx\wۚ;Ն\Q@XLRbE0Q\Q.!1F)qF(1F)qK n(;bXf(;S
,&(Q )sIA xq6^ IִbѾ*eЎۂR2ELfZ)[oRUJJu)أSF(
RbbP+
bP1Nv1N,7b1@P"xAEa5N}M?ʴ1F)=wmlsxJ1K,G!gO&7?ֻ,R⧒,VkxwUsnoT%"e#jk"(aFi{>Ɗ&-sڜ,BEzT.p?yiFV]ǃl%ɊIb'R$ZG!I
ZO Jи=X.bq?X3xKE/g"^-:%{_ʮ?"x䌓e= RpP}?ٺ ՟L B΀I+y GT4lc]ѷ>6pdgAʨ-IzA	=*(0;UHcKLVS ;Uk]RUr|>aPNj	m7GOZ..ǫo_sm,:ԨX08#+8SZ\8ID''uYo
"Y	pp}jZ;iG4rAt&VeU
gϩlx/QC 
ַ:3~4ZL\]NDJ?2iҿ^o]2#V66 mOuAMǢ<
'Q9Rp|!̓3$C+TRyt9[YqԃdŸr;jU(fM"F".)qT@Qv( 7.(QqF)أ Qv(avb	E.(F)أ \RPS
b!LR++U889'ž"kVIp'l`BSF\QFIYNMGet(FGiKe b1Z6\RP;	1K1@	LS
(	1KF((- Q n(;bQ\Q@	1NF)PQNbQK1@XLQ\Qa.(a1F)أQ@Xm-- 1NQv(!~)1NN1NNQv(0LSI n(;b1NSF(Q\Q 4ݮ5q2ȱN +!;>suk~fb=2c?#D)zm]LɸʻF	VqN&)%P!SF(bPqE-%8aaP}	W#L3@M .p	xS7.(;a1F)qF(XmbP(+[UMN?YW+G\vmmuΖ@C+J۟)mŔpOXNF^7ۺ6,mH&YnG^=68c';>Πg׌U}gX]^541X6pO89~:Q` ~e~h|moS^GIEdGR *O5n=_L_۟D9v.QH/c\Rl>2%Ů(b+
(Qv({Qv)qE1Ku,3b1@Xf(?bQ~)1@Xn(?,7bLQp1NNcUkaFk>}N%TcV(ۚ4	^hcҸ.342L;ʩ<d}+/V8ĆNff?qk<~adBRVgTqԞԻF3RD 3 Xjn]AO
)7EF͆=3ސGi@E.Sۓ"U;X75EGVI#΅y!qִ]I-+-gkk9xFc=1A *ZhrJQqXn(;bbSF(Xf(?bbQ.1NaQ.1N,7b1@Xn(;bQNQOOAKqIEG-ża rGjShQXxGO ?SYDKadK"(ybڬg~%@֖wO*/E/i;тf`ːՎ+?1 {%KV ȅ/q{'=s][{_Kh,tYl^K(Zb PZD 鑟ShEQ1DbU-y |9xwvۤsձ?z;bt8U1U]ZF)qKQ\QbSIa(.( &(;bqE;b1N,6v(ab(
F(	1K1En)qN7b1@SF(
bQp\RPbSE 7b(1@	1KE &(-F)hU;P1NXn)1O%a1@Xn(;bRbJh;bQ\RXC ~@?:{4[Qܦa&[hſ[QV6 v5".(.)qLQ.)أN&(bSk0iXqiˑyzܵI:6#ly6?oHINr,&(.(,%&)P1E;SX^<ng+Rڬ^nu-;	0?*߳vۆ
uMqV2u%2J2d tG¿T%ov
2(99I>On#dI9o#vV.ɦވ|83zgҦȵ)>5'58mHA4s{}r63OG"<췍	+Q$Y?>B5
.n#Z
6CYxo*azͼgoA\}f9#
7Eoe^[Km	1ast2Hѥ.<GuVzeD¤}1VO{%?Z->z]mn J0z~[L i?<K?&r੢B{+X,mklh>g^ 庄mQ%c:Qź45O_62+BRw[dk˸F;yԛbObT7?o  Z0G
&)m>eܗ	.1Kv))ܛ	LSF(RbXLRQ@/GB\98㯵yf5>ƙ
Mo?:d5:ĿۀFCtzKyP3 YL3Qrα-"³.U]aJ4\,M$N圝rHJѯ|9&&e**XhLO	%Í23ҺW+23g&\s5f[bRLQW
.)qF(XLQ~iv\˹J}bS3G̒*݈JTn(UZm j`ҝajbSe'" 1 _/h'缷!ԃ57\#jܜ*$ʗ)aVl4퇿j.U/c|2
[Bc.膨ǫ;/S\FgT"ȷ2ec;[H>uiq6Ոͨ3eg3Ye&A!e<t%s禶^_XG?ΪL bP	NR[e]*~":kc{cǥ/e?n#QM{ltrOYf@
gfyLRG
FEƯgB[&O jD*Ws1UʉsՃIo4h[OAHw1?mS%>x`FMJ?bn)qK\PqF)أ RbQv(aQaQ&(.)hQqE:P;
QhbQpQv(+SK@Xf(bQv(a.)q@SF(Qv( 7PQZZqF)P;
RbbPF)h!1K1@XLQ\RqF)%aI[E,Hyi[ѡ*&{~)+ÿ=/TRA2?¶x*[sEx"GJ D)+='VVG.&N 
s ! ~S*W%݊LW^%??<H[ ?Td{^):W+r\+:&К/xDHDWG+9 xs֧**5	U,7:.QQ 0  i	?  \ޟs; 3[ń˨:+QN+ͮ|Hìl@7$>4>}MS2XZ*;R⸑;G6_8>i{Xw믲οW*<d_&; axF{2jU(Ԧ5cy<gM;W) i1TZ3;3KoRao >bgKOkɒT] 'a ϤЬ+FЖ\"{ž L>. }'i2s MurPbye	u/8Y{VlI1PxùVo6Gw!@)ד5Hxi  ?{#֗sۃHf?m mqQ73đďU>cWR{lIWjU'#}/GD~W-2|dάH5{E55?bCq
nTATaQH,cbZ5-ȭrhRA"bRLV\\ VU
[!d?ʐ~(0i
.DBI<Ҷvj3_bHbi
	Eb RKO2)VƼTL&dƽ^msoi{1;c敻Ң[ӽV?0?m:qn]l9Ay4uBFcN+KB^Yz`<}9۩xBb@5*Yt![
T
ǈ#qSVav7'烊23 FME@g t1K^bH഻_Gi5vԥBRO5._ROi"<~Yj?뭡L]HuW#WRЎ;`kϼmCeum=K2)R8?ҹ_94G8X)\(~y |vm+ ً2yU3~!kX!o9;tc|Q9SЃ4?g Ct)+as$wnyyi V~)Ҥ<2?]VQYy(h&
\i725wkw,-'=ku;>&blzڡ/29SRr9TtFcxFbÎz	J@ɐSC`SUD%EMiY$|ǯ4&v^-t%2	[)9]+õ튞~U?O}H{`1؈ҋzz]z)ߩ+D)q#:˞Lt:z4< p's\D/cJz?'|U$2Z"D,E 2~qOF?[ ZD?餀WYk겶CkN8EY24rcf	!|ɗ?S:r}R\\ MzV?@*;ʯ)^͜Zml۴Yx7U
;Y$z1mZFN[o=3h'
]rBP~Uryʇ<@~磓k;Tk)nQIָ^Emf2>;j$)g!:Ff$.p;T6Hd#+%oA H42رR9\Y/eu;b]?o^־naSE2ro{"G=TԵRn6ӱF(
bbR‰Qv(aQbRPR@XLQK(Q@XLRbqE:bQaa(K\QqK\QbRPbRPbqE:hbPQK(1E-,%RP\R1@
LPE@w"ąYF*$`  ~s)~uHֱ3^Ml}HTqa:k6Z%\KT1ּxsS q ].qڪs#7?
_jr"WsGbE?p?j /)q , dm{/ _UAQ@z
K ]zB
Zq)ZKg?)G v9߅?J۸}t:-%Vx  |U.fj5hB7 q SppU8MMna6xS/ Pߘ幷1[,GS^uW7įjE=Hɗ \ᱼ^ 5]Hc Vk]Ә1gn}q]8VrJH4捵/iE6ᮕD,a g9$AAǙ?cɈOЉ̘ga4"RcMtfyD7[=1O2l do'/gˋDT[GUfRGֶ^ʬ-#?Korey! [U{er^EqM<SߝV3L	+K3\a tRWʉ>X89NӀmkRK#K8Q-ƷFV?;Fr;8A]n>&_rF+GF{1fl3r8EG5^%%<{jZzLToH=
7}2qҺ~ID142qWtiZmw.[*;{VH6m}sYo2UtQ}{ ,#}% 'w/מ~cj6H \Gc{`|?[22?uj ǯ5r/L$kov(ʯSpRn"fф#8E>,k}2PsOE
8K{4"'7u;I\"^yzfxW"@P?ޏS.# i־a95oh?/Q__X9`: ׵x$H]Xjٝ῵+.KH_-mn#$? M7t"fSf2is
S;{ߎ?5RVKypɴ<?DO,Yn ijo\o 
\~펵a = @O(;S:u){jËIN/`tYR?R-t͹  R}T;4' BG =y }R Ts L Ai3\EmI+^sڷoM2xU?Jw!Ţ+Y5:8:_O ^È/`9V?S5tU9rOacZ&in`=O˯zp<ȧxsϐ7>G+wNՅmdTN"k$44bɧ ^ɤDXcq,;W3kcY)`]dѨՂ.
ÊkVVVg\fjD8IԄsGJxi$+M9Ybؐ(ɑ :5-aՂ>֬xNźR9n?x+2xGLVRLb6)M	!ȫ} ^M?NZ$]?(׋xnO $0PG|g?ν]<cQ q{5;``ixfeep #Ms>6>L<һuvI#YK~qY	@VV!
=I=h[|?U<mp䰋jz{SI=>+=+G? r>?һ١FrN	lU59Iw\Y7;xkR~Lf,b;j 1s>e8"Âr>|7se_` Z5L M \Drh
vVW#մKX$ĄJT5e/t/@x^6.mlTeV<VPa\ס+sG|D?Ƨ渞`?R!G7FqYJ- u0[Em
kkT`T_"3uC<7aey-Vgbm	(3Oʹ O"k$z 
8uSJe8e#:Q6)}Đy	>n,axUUWP}Y9֋FA* NGNZI/|O cq+~w"gX/~j\Y1\5Y,oL	
IMkp||= ½Z$~
Tt:ϗ1mdnWa5λLҳnե93*V;!N8-.+KM&ڰN֧gs\vҥk@^s/FdlRӽz(jdi6y19?ғT\tўHoȡIaVjHc9p
uP|)u!t{7Qe>Vb|-snm"g#Y42KSm*O9$Ҁq\ׅ|f06XtvVVG=Is=u%YRQ Z( %()h (QE(`QE 
JZ)R@	KE-a(	E-&( )(Z((EPEP ( Z J((\Rb
)qE %PQKE %R3742Wy\{;u߉qk\<Y2eOl,vi>Ǥ*t:;,Z	҈9wxH
0I_wcȱC~/WRx(=2:
BEw~wk$h-a"c*k3KlXg
r
6X&䥫:[YXw
7ϣl>?|Tp&ۏ 
O] [?w#QVmFM
#a:9?I-	Iʼp;K~N(&A?O{# 3ga x$yVA"C"*G N9~nѾa=?HfF<㏼+iLk}blIby?CXj	'MAN+^;$k눏z_@OeiC'5K iO խ&s[Q_q%ŵ<.\Co=g4fQQ9?SETK4,Q$V<[ɟjWQV3RJWw4b	%v}xHB+ y?*_^ŻU?[]ywԉ:;	}O Z\D,fE]^+}? 8]/ g}:[GBc"-Ԉ pjʤf&kC*	Aߝ`28md"sdz~ 48!'p__3VMvhew`	-a&}"+,AwΓ~qk/YRG~#"hX0!	
F#&d Mt0Τ	5qO 
UOcsn}|ؕp,%,F1jC(, aeRID()ʥ,a\c֑b
΄o]imV\j^Xu6O="&?MX6#nʙWi'pr:MwFR}w;I@ϥ\D3ƒ3U<3$vǚ!3	)_Y*i
uQx^{N)"+͟p_<:o2+5t
~uinVXZF S
xe͌ T4rpw_q~udګ`ł8 &C >CpsH봴8xO<
k;(Sg+: t;8.bFȭzllxZG?6?٠H꥙P'ڶm%vcf
U
OOy=ڏiFׁ̮cD2k7^	]5Т_?Y}9 1+):5YYP,jQilY[jg ˰P

α$B3 N8E^7ڀƄz$qȎ&vJX)ϡJ[FPqcT^4gXB ,Iq]j2.O8jݷ-|ӺU2TԡԉBoTwZ6IѤ-0NQ5xBN˥sjpϐŎ[ uǥB.V^?ʗ4Jk =i^&Yk5e%	K
ڳmt/Ѱ.,iF*]yE:Ik6-$E&mp}{Txf>Aȸ;Krdg 4 |UWqlzUy<!N&n22e/$^0p y+=Ugs(`r>j`,omb"==;M\#$yk 6m
 :wbl|zZ?:APGj+Aa֔dJJSXӼ#Y\ILӒy:W_ĺ{gR,1	k~*wamn:#K69^e"oؤAY]8c✦Q卙C\/XnmURNZ2mF;՝X
oil.]G 3)ǡbiө'dEoXaَҍZ{㦸d*#3tև彎*p pi?,6m8;Fpkki"RzS4Fĳ j71kUs_MM'Z5etAԅy5E3l8p6GT[{MJVq%|ە8!65|ONkINZڢj |o͉  |K2٥f瞙g1<mfz;4[<MqۥUgvxIJ:P\dIuXxC^ P sn2j$xO46FwoPL'	 $MKhSAq,Nz?2k7xq<\Bb3 xk.2&9R>tRIo<qOr}|?LХd7msО JO\R9b?^ƽh&*ֆWV9҅%vyf9)$F8c9+-D6,qV4Jd3ޜ`ژArrArphQ硪J#$sֳ[VETdKt<ncޱ.ǨKis4J	>Stң|
b=
4,`\|ÿV]W?!lcxgx̊w!truZ[Gj\lLbħnW뚛A+A4h?@?+OʶܜsߵRS;!G$V^I`nz&;hF 65G3?Nn_; _J6*Gg,F cPo@Vz Kdd)$l)m )`.l6
k.R4SXi0w`}M?o=>Ek?.eN͒wMI^v"$!3\;r6*73e6q?P}B#'?(ԉE%2vg?N8*%~SdT#	f}fkRZhy|3"q ʣ
1Ql6גB yt #99:dfjt6љ74$yd$>3&"V38.Ib6snnmxs֭b*u,l!,,Ix^YK-E [^;&LdNߧ&"/F'tzUO$fo^ټpc,Iki 1<GEp3˔*eǐ?
"`w`duSݹ֊"LLyqSzH^(sc]R9ުTهGG+oRmQ(smKޣ^'EEsM?_{GCEs -?߭AbtW?ޣiG{Ttb /zc!ToV/AbobV'{//zc 7(??OAbnQX'Կ'{)EblQ}hRknV'Ͻ/ϽC6_GH=M+cޗcQ&({)Edl{?H=M|QYG{HVGlj^A"x?-cS 1% F{ߝc#;Z ƏmW? $,gTRZƸQEYq5~+5jv3\j%彖X_T W*6n`bm;7AVO Kp::°vъWa'}U ?KO& 
`b5tzW'ibVFe5
k<K͛rI  ?O<k$q#h0_a2+NeD*ɟhU\XhUv"[]2nnIzjU  Q\>fpsѶUEkіr|{ʢZXA;.TRl>Y6v
>,rGOE j>7&wb{d5y`;a~mj+, 6*e4t+mh/d[?vxh# _;+Kq0X?.NtHwgYEFMJ$66ہBפ$s[̫ebR0BT=kMvM k{ܩ6
8oOpKRM5╅QcB.ͷ zz[Ee|>\c\cDd
*U9ҟ3"h6up.!0Uy[uM`
zM6ݒNHg~lʱFq[U]qP#f
I.8MażtrQȪ=FS!PՐۏgCHXdk}"Wv dhq XקL۶fZIn8ԭR.ƄhEW)pe m9)Hd9tR
8zP|Ze;Q ];Cf?.lVH#/0҇H%Xki&T]٥]3,1]kTgy_Fhi~`;1{ŃMsvqsGIpȹy;ׄZBI0f3)Iw.K4J=')Aa m?ԑ-TdᚚϹ%:R4]WO~SdL1P't4KfѓץZk2ZH<@)<(y@嶐2O,z.=t~c⥋V[d8öE>]ʞoYiKʂ#ye|Rr4	'PqqR<PXjGU9XaxE@t۩7DcM[C9dVied122)8 xŷ!{0x9ch6ܴBU@I9>r8ֳRjZ~%5unYc#kmF:&+_گ#;k";61hH*'$yE8Ջ`ͶylYA	z
<kՄÞkRg>Xv>ҩI-^-9#W-$p3`*؞VhcK{U@;$b/}9kMFkn:楶jc]dSb<ZƄ%*Ep?* 㹨OuܑqzgKR\ߑV6F0۹o{iVЇ<[d
TTlx6Kb9aTi	>)h \*u=Cb Qqg4@	8RBZxR9R0y P*$|=\֫2@OsRjW8{&iYBя|*o#ꀳus
ayGYTj&f&)!Jq(,Lֆ8&v p*8"YkXٙ	N~b#=IkH5?Z$ȮH 4CI12;ʱݯIuXiU_݁V'&Mj]9^²]Y'rQUdzݭy5H_c-mTY2|xmzs弑x3J3?;p;Oq3q.#oaMITF
Y VguhV#YW8>ǵnȍŤ۽ͳdҦ9Waak76Ia,GZZ]1/E)SQi0mOךtj1G5ָIniLcFDJdV[.T40rzK[51)kӵ7BpvvkDnq0LiYأ	ޭ*qRl#H+Nii g]GEjú<\ tqY?g%uLV#*a@Z
R(ZG|cȬ2SZdT^'4}RfiQ'!qG}eF9Wauk} F*ǐ	\/C\BAOqfV2Ȭd&sOHͥqq'I_FJWsoVf"\nRZKS猏ӥkk2mZenwoܜ7&:&,RE$aweT~!Gm	>0p3I afG;hhtJ' {z̐R0郒KvU&2+N`01D&/T>TT?12F>I5y<:䑽3TIL 7,Ov_}7)qGsb3osJr\Yգ8dTa;]T/eHëbrI5F=N&gI1'yUwŰ$s3U%ĮtUi<ōGY*3C1=vqTfSpl'+HTd֫X'V]O?'QZ.NBGAtcɏI*.U,G.KGFA皵q%;M❽;g'ȃ
t*H2En1҂6aYPGgCևUF[\gF/*},Q2&KĪd"
󤸾
T,>V0G}dت&^tވK-$mqPI $5-$se61 ӴY I>i'jH<GWl?y#ӹ"sque1wDl?.s=ZVh8mrn#j"\>yC;cǁn<u.s=Eh*U[k˸'gŮ@.+H#^ONx-a/IA!0	]qamP!h>h>3K;HmҴXO>ߴZ>}j6A$^ߺ?ZbD%8$F+X⨾n?/gHO3Ozf֗>G+}hA;Ebh>G̢̣b h>C̥(}hA>a(h>}22֏ZQ{`4>}hA 2̢cC'֏Z)|, Z_Z((}i~}k?̢̣_AA 3ޏ24fs򢒊 _ʓYO'Q[>h74!hϽ- N ՀωA? C
d4&miXEɨTV<gҖEOs :qYZlr3KbHlTc$ta&0tTKU+>U'' qEb$%󔤙g`EeF#;œR:hK6#
Xe#KMӹbSVKU}={⻣Qtd*(
F}rwU5k=+SCH($83CbTnkHeTu$#ˌx5$ZᾅX_ink&VSڭh!jKk4ywǷ"D0,b
SE"P*3*erܶg:zDOV=s[@Ď0H KÑ|d
d$Zkry?:͵VIة$gB+HHa,t~~(U_a?3'&`<`TI"~-g芽ǔjTPhcp $t_bys`KJp^/Bu$
A&=7D3j*!7(N?1CSΓڥ\P$0
Ǯ8RXA:WO 	+yrHU_<rKuHS`})^LԈ^al288$'6i9+YEyXw̽	u=/4-RsRgmkF`<ʹFK-մf''*AzuyJTAA^qpQ|R{Km`ԢŃIZ:,ۗ9Z*2N@@9ZqLj"(	Us6D83Q;&Cه~+*S{ma}7*qϧJ=&gmO֖Eތr`:z)~c[Zv]_Q|܈銞=FKnoV$		E%^8ҢQBǔQS?
pFQM.:}5q{EK-'Fqqi%HQ[xM ǝ'??TK5R"pH'p1v=bu gIǩAp<&HZuY*8#՛gk ~upr9	̳^}N0Q:֥|Ms{*Emd+
>f#bX"
oiǼ4+.[_|HI.R zU_U$id=Ccp	%VI2zVlfYUx:ւsݛ%#\rN~9*2mdTl0bLz`VOzh͒ z?/ϩg?iŮDjN}{yRVl

vՋbRĘ{y38>kx?aٱ+X65ܲSxә֔0zֶ4#9Z<C뚻)<qPЮ:U桎TZCWJzi$3O^XapS=`(ޔ+??΁=X8A(e
9aJD?(v;w/$bLtR41yQG5O9砠(8pFǀA$-u__H#r Z|231Gkr6@<tZu
V2Gm処I\fw@y=zZwt+?:٦<,cec&FLj)BɑqUn1M3;$(j`z"$9Ln^eg1hddװO>7~%+fq=( kiځH6$}xRA*k kfU^}(Җc<O(dy2ұ!`񃜩F𮝬@%R82>"Suil-#N5̏+\%
ūq`|{|\}zb:"\7E[I򴪏X`oh?uQ
9e\~őr=
RRO'z=
E'5;qQ3b *8<PTE@cڅ
]i^jD(H[PLe]@F+T幪ңT3%=SB6Zq3ɻǥD`Xə^W1ie
B
	<ǸX#\FQ7U{)r5]\άҽuCz0?ʨ]8GϷwuNw}YWQ9bçM˜)_S(5{2i7
" 
,WUR	QkC:ah fTڧ?T'5Ta]yG Vi-yxa|YY	y07 NjnW~¯a\-gBr#Y[E$d֮M]OIJ85
uWf9$Ӎ	(Kb	o|oIrRLn\ޥ]n||АG\/ㆱCQҩ-ĉ|wlTuLd!0U[#' Z1F"WqsmJX"4B#pټ2n힇R^W\0y|qx0JSyGEj^Ew3ǒM[}BHm]+YEtʧTE6[_UqUN+^t%7ot;`Oy֯$EKzUW1w9Ò֞iX,*Cp9Y"Siux9݀v 37<VьiC"X^}Cc}><L(?po޴vo|Gyk i@RmlO#[¤%ƞ'P j	`rIk:ԟ:K }5I~L}]㣁QZKe!h搩tw!4ccE<gf\IQՐ}MUt?hcg\0=cD<ckce/ذ"F0s[M͜QeNȭcS]Ydk}БiQHHd䬃?enuk$c뷺Fm7
٥cjz7{֪%>Xv$bK.7T[@nuCu%Fu]nwQ67T;@o}Cq	QFMuCun	wQF lM=q٢wր$n҂Oc@
icQ\\:*QG@
zSf*u5bPv}0o+N?
	gp&88$9=JhsQʥDo<ݮ?:洎,iU~j<yY	^cbYSRWyoĢ.
m1s?⫙"l8S
l+m18|NY>])?֏hrG?uXTBhʌ|î}^>6i7(o\=gP&|L^ZۋIv892:5Y$K4SGCenҕ~^Y n?Һ#I [A&UbTD  :RIWhSbnbnmX9V {c/\j6cژc?~$>E&-G
RiX3OW ~dK}
vXVaT#ɱb[wU4e" 㰷V
Y$sZm 'X}

DӞ;#2G.
hϒIUF#m?M-1x &vE*u0}Z}Ri8ՋxUQ$`V8 l$U&q$`ʫM{-n{)A:TY
דFqЃP]>i|mUٷE(;_z6qBEוrCoi3|vZ^Mr$מ\Ds[Ktg3K؁zڸgOAVQu:;@UWYt;{\ e\X7:L]bR8֛g'#?A4_r4)`sEgee%ε*E  Lw~ 汷O]![ZYPFRT+BgR= Us3;`~u|
VF$o+[0οăRv,RZ'1ƟzDjDWJrڌQ)q m-KsBSQeOjZ"gVS(|9GTnz\\*ZkyAu.jkqV v9b}>n$0cv˟湑F94GγxkmH"ݟSKs#)LaYcy?fk3EƕS>҃&۩R>n*K2oQM3{SI7^oGig=I<~TlʳrNqRW#I445r(	4TPҐmZ%K[t$b;xvҦ%,ZGv	[8#a19Uml ӔL	tP#	V*¨134A( 40=Gvc1S .~Ҕ`X
n H3ƘӖ8P< hq̲}).xmSlEYAX,sګH#}h`toS!m-CrTd*Fn
MsZg)"5ˁO$Kہ
7@̍JCqq?NMsҴ#ljK벹Drs5sLǯ5f,`UnN]:)W6LԮs־e+_o$Ij"PI~]q$rŘ@v<	D8g
:*2@K"h.HJ4J[9]:x?Z;PIUO^kԑ.@u⁞٧NV[8d }s^ OnV0W?r;n{PUl5 W/7=R,*HȮ#"iW-pvҨU$涡F@sր7Y	3E
VJ]l
$'0/ SMƀ-<S4#Vq hphU%TE"H` qӚ<zE*PRwBbVG 
ǚ5$c^[. evyaܸ<Ⱪ9'L@~ܣT\3%a3I3IPEh)sE1(ا4~T\.FB
Oڿ8TSRٔMlbc>5;gCH#FjiUu1Fʐ0<:L
',75IN"1[	AQ$dgM+O [	^~⍫R%TEڋQ9ax.rmLMl41?@j鶲uFrwe{U'ygrSɨ3H̹$xM&c1sQ*v@Fi{8teZEFICEX, [-ӖS',!?+)SAHj(.Py";=)rrO11Y!GZ؊bQ9R3d32m dWzU7>j(TLc5i%YA0){Y)0nRO9|,92)6*si99bGLՉ[
cjP&/+ ֗ufCt@r#[uB$!<׷O9s7M7Q	
8(ó*p1Z)N*W3VEn;5Z$4<ѻި	7QϽ	3F4n4&7Ty4&7{{@f3@n4ѓ@fy4u-Mnњ ~3LFiJ?Ǜ-Ys[lT_A5Q_?g\ln_j7R}0?u<zRP9eSKQx'QuC܆D$ն>?Ujv -sE1i l"aOc[YQm?M-GHGӊcK+X2ڭ}6Jԟΐc}N߂l: %W
+T*7}_ 
ZSRtAY)gw -g`5!ӯɲvj DMFuy?4^k9ԩ#IH-ܷFQZnTwdY\cciZNVwnsLJ<gO途- RQ@1ZS67s!L̀H ieXP[+df>C*S2SMn5զcFŔ?J(9 \ fp[jf0[
ieCъDfo,4<*3xǧJj)[H?VR7l)O╾ ТT㵞_p E&" Wa> Tqj?`SM#Jک2:5  h<~p=f|F?OH e {gwt|;5'|ȫHr0KTGUZk+=1BTr9Cmc8mQ] ^c\2~2Z͒ eR> UNPVE:¹zqZrSn4IH4~u4M9F qҵ˾.强]ҹc=ue:O"Ű2y}u/ߝgRܖ_^eI<1*/)uH45慇y¬kK	9@ݎjG<UZ6ֱ9-َY>C1I#[5*Jܓ[GR]
Boa0 䑌V!b-* 5
	-NҲJ]v@@bE~+XZ[K+t$**p'ڥ+!=FP RJ7iX~zTou, _E1M0MMLdăMc)@
Q<֡85uu,Ducj758qFUYGD[qJJ~wlzf'ީɫi9z/̒h asF>( 
a׵_O2}[mLy}s+nݦ^ β5=|C-TadMj	G߰Z]jK\H~Bϯӭx-QLHI1+ߋWVx/^"#U񐽆$.P+o`9 vl.WF2I7knIɨƚkP54.TED)AKPTqNZ^SL/(ꆼ9H Z֗rDVH$dqN
_*hzW.'K? jU>?7OcGw4wL+H[Gc消	r0G#w&bI3k ձcGvt'CG+
Ǡ楄k[sg]|XCLW:X׽IT"^pR()ȇ=5E# {Rs͂OT7컹Eq޳R>:9":2Qu5qnQïk7Pcon48bf6N Ҳ_jμ Zc_H 85=q~2V+rkR贙Vk+BW*{qAAc2*1rj+v&hҗ	
(-%_ƊOʎhh/Fi9AEPIGG@	P1ޖ2ZA,,q*)ʇ*"'*,3g$#5oQZjVR2!QC\D k݈W *BWT4y1BN*(V-Lc<}´$`AU 0ZYSk)*qZTChף&^;/Q?ĄZ:a_7ktd~\"ʊ0[iE[뵫NQ%TɫhvE9o,>5$>c5
u#tuRO>&O5d?wF}雍 ?w.}雨( 9qnɠn4CKޙqF?45M Իǭ n 8n?Z v?JnE=vztQylW?\p؋MxMZo$_6{fRvY!Y`FsVWXvĞ -ǥ!A&G9)* ?٧+L}.6ܛ=iU5eoX^^1ssZFmzY/>Fjٳ~HAϟH AW]@&j?
j>Us7q=Petz
mi4Ak%/'m+̊O =
σ(p_Bm'6V i9_,\U#!OΪK]b|{.PftH ڹ.#Ѭ܏$~	/nf?W?95n{Pu6jK; o_k:]oC5; M& ֹliI 	-'6=S *kS#l+o	8x.&M/5/RM̷2MQw&֦Rlɦsp݀\ >AlfP[uaU	'vFoL;I(*3x7`)icLu=ٛ7=X&(gRџ(3G4?(ǩ(S .i;u4 N(җ?JBw^>ԀM*ʰm
1YUсU$sH83R|aRHßz8i}
#BVn8h#0U->tC	Dp_֤PZGm1s01t^5
:~WDi썣c+nj펕}~w~=+M%ʌ78sZMnRbѴ#o2l} je\l%nT8cQR#kȮ|C-Ef?D 
e;Q+=iםhڹs+y+)J
gNsRI@QE֩Ij}Li'Jfs#.CCʂAEyLjXѠ{Q5wqM?Uu9ϮhE׼U_q *ƹWk؆HEXUcҼWׯg9`Obkn
Iʟ:AyɎLsi1 LG8rn484Mo擜u)GC _ʚ*',Fy9jh(>siwJT<{GhT*>rVVjV[BOXv@_jU9j̱7(B0CݼeK,c1VF׭y4&Yw4e(#'Q'fqE4FE-%rA&NFd6 gt0NxVX*#q@&
kOi[(~mBRWsxBt F;KnG+-G;+/"x TZ>!H+ 9QCV0?ƺN(Il  ZG4sFp#a5ֳ)}Y]M?b:;ڽrV)I=f޽S.q5(+%NG~>cQƪ [n9pvɤzԇf1Pڀ/[j=mB\@}Efiq?zM:d>\uEshQ9:ѐ=nKK!nΩrPYUʵ*êѩYIno]YA3A9Zt7q6讹4ڇF$y:I00F{汵'2rF?6$~)N[=gj6BATh#/Mcg#kX(Ft}i?:P9U5L}ms$TdGY3\ĚOfiŗMT<<R:,<e =,} RN7>^}Kgފ_i&_ |Q7qCS즺]hf/ /`}T LƝ'ݽ>N]Fi
9f9Q `i$\E R~Ts@Lђ("( ~Q@ϭ%- RQ@E&h -4f4҈zICv?#M6وsFkLv 0 6aQ?CVfg !XUׂMA^Ͻ,Qȫ(TxLƺah,UϽ֧6\"mS]0̰GџS
4^WL+ҟ$`.O7w}kQsFG7$h1 j>8p>H@~͞)Az>|BJ@XOsOSWL:K  w1? p.x൐e1B3-	Wwu/'٨Un$iWӡ ؘ&[
}_f6An
tzD 7eZ8G>" xUSy4P%DY2iP~xj2S;SL 3<uYٛ7&~}+30zRgFM /GI@(sE'4{PQK >Nhڎih Z(~4~T(4d}h~T cRwJ(ihh))
?R4۶*KdTc)l^*$(^ㅛCxfЀ#AR?s(k8h-:#Q5NhWDGKDnJȠsQ %GO.vg熗 D&< *c<:	g 6OOiZl~uݔ2m䴬B]GsK, XrߗO\y[v+$a5Rg!^Ҍ)X[IsL4 &4Oϵ M9[i
r֗mǊ Q{WTa;X8S3w #O[; tprj9_ֽ &-ASJ94 Ryq@QzOh@;SX֘@\\$11+ֵ	.nv⺍r5 \^BIր4de?:z	qj&<Iu89Ti_Bhcз?c:%O*ȥp#SHGi02WC8<Wx2hsHbnX~$SΫ&<˫aG-붍)ARd<dhxH"5E꓏VYdtE\eR1hb$V]-C
nROQd{
cnɯ1SGw2@ǯϳ hazJ='Z7XO\m{E.F>du>G奣
YO7YTir#o/5I\)j=Bu	 
Var֍זY"8ȇqb9:VZ(kGT84t?jҰ3\O:rM3g~Mcyd.2P
f<C$&4\皖O2wtlUaZ^Ni<	y\r>V 
"E;lG8,GQ@ NadGW-Zy&EAj7/),uKN#N/k	=^.Gƀ8җ9^t 
K@c> X-ep/oϧHy݀zmm#~t)F2q[*&5gꢯgҌް/myak&֐()JdCXzXzmL4e1L>[E	Vרұrtw2|ȷGS&_꧹ '^R݋ Xgl ?*G}:N7}hFEAA⌏i Qg( J 3JMRd
 \dQQQG((h((4Q@sG"
?J;L}43GGNP3GE )i#~ְR	,?aULL3TvmaQ](t9$Nnzo}/Q'CUeoLKWJ1 u'-ٟ"iOpF)u+]܃<U|ԗ.a94;AYP:mf JȮ#
]v뎑\^lfuT(1Yͧ{ҒVfbG~434sh@P?Z(9= =Rg?S@GQG@F=(( ?:џ{ _
LF
Lz \tR}^hqFM/4fu=?3J=i&=xF%/z^ MN!Q& d&o,WXRT}㚗'>tk8xGΈhUQisiB` %`+tVѓ
ja9~_ӭuy#ܿR>  yJ#)%sW5:'oʺ[Db12?*~ֹCǷ2,-CkJΝU?.Z m26??./upG_ |YS03qX'9=i3Oʓ> IN}G A8=GFI4 zBs׊_ʏ }(q(('֚O#h4/})>.E '')981Hx4 J3ϭ'#Ish=)P}?Z1s7`h 'ړ=959+	(zԒQrޤoj u	s>kE3uo֮I+J(d'Af
ځ( Xz6|rO4 p=O`.V
6zrxUȾJr]AǾ)
uˠ  n 1~}qk|Q}$1o8?Ҽ`VgSBsֲ>
I$R3x5QSҵ5fVFz;R}MNwӘSC`quy >WJ23~\7eP>f+!6 E!}A]#R I9?S G! QLQ!r Fa?M5)t:\B:v&{fvoEJUѵc) gÕݺxL0i%h/-t楻 E8M)vKfE 7 4~&>d㨤Ͽ4 vO&~ II(?@(X$Ѓ[5[)\F?^^ z-407 ?JhV2z=JPF?ƥ̷q e.S|.--d!&uto𷈗	[+F"Vogp~(s'7.#iܿ[Pvg~u! >HH:z14m֘aqVG
c,=7R)+}
.sVϡbSҹeK
>4H0M$Ϸ4$@#Ͳ/ g*{8Kk>ai?\})
ds>Q=(qGAϭ<Pu3;Gn:uh ڎq G> >g~T~4Q_J)*s@	Fir}(>~4}:.M?J Nȣ4 E2((Ͻs@FOҀ#.ຩ,(0 պd|C]}* ZNZ})hu!\a4*N[ɔ5
aYcȟֹܓ&BiQOfTcm⠱p@ Y#7#dWh	B&1NHjyF"uuR+t Q'޸A7`yh}F}ǰPttqGNv@
1d}hڎ 4hOҏ&ϵџڀ3җhO@CӚ6
R>\
da7GUW4%>HĢ5{SmĆ5SdH©SgRnQ[~M(T%^q[
#i\<S$_SRdOtF#
q `tPsllɩn/$ok
}pCȖ߼@ajfv_<-i7&qsst_JFHY @z_ܓ L ]V:Fp?壟'^nK8?~f 
nn绐q3绒h<ugV&qG_OQ><TgYsRPOΓ'4 !ϥ):fqӊ;#PI'4ry9@ACG4 zRAh8=.}h@FG(ɠd(JrxƗ8@'L<f_j{<Ѵ1A$3TlBz@&4LrN@M?f{nleYq-I-<B7b ;?ZSjfnؼkݷӮ{V1?{#8=^>\֑yG!y agjeƢ[A"Dp1Ǹ֐sMrV Y/ErmFOy;}k֦@B;LZ"Mθv%?ZPrK˓|?[nq)7	3v+` ?JQDYE LPPzUuϥ/ 9M9@y8 :T}jEJwm}`--%0#}  vZ]3Nu?1≦q.FXUGcgVA[o
{2QԟjƁf
OL m5K_\i%.f{tlG#~UڌV0`2c@W?hƀ,9#M,޴:kq$2FeaU"ҴD\2k_=-n-1Et6ܫ8#co ts4n W2x  h] ^ƀ:Nj^i] 
/ysIڹ5k<ެpA(٣G\3 
 \(<~4 ~<QzIߊ7c gRs qKzLށހށRڗ ֌8$ .
9N0qHO=)9Z Ѱ5-4]0_u:MB.C\01K
 zM,oq0oi.Zg+5d`+rź
gᗟ׭ G}VjZ`UGDƟqVs՛O5Ɗ	$gPsסPdW/jzv~j?rb3t'$  5LhMJ[&e*0Ta-Y֚}8*'a,'XOeAƧ0<QMsʍH%FqڗsƓ FBsI 㞔r
 O֗?~hE JL)ϭڀFO 
 &sE.2z9h ɠ=րly ~Tn4 dz=x?:&iy }3F=( h~4 gh !qҗր}qR~"4/Iʀ9WrXIFNM\uF6[cl͈՘ZJ
jiL~ZZ\blT7blJ_gU?. eN	8N=]58RBWOܲHG*Fo }J檦"hˡBnoMxтͧOp?5Ӫ\( {
Sh`>l.nFD-wP*=)\}f{{= #K8 ^4~PI׶h9& qKri9.\g4 gcQq   :}(b99ǥ  9sN
T,}OZF4dCWnSU=9;<utG	4OΝzRфvGLh;!dc3cZ
xh$qғ,4mGQmde?F~4G$$uO{qG G 	c)x:Qa}>
trqWڏ?*f?J5_Ӵt s-X@faoW=H9٨㌶(SP0C ,_eG9K4 gڝLS7'|sFrAVtBQHs xTq]hA	!8j@  3=r)#?   q$qҔ61]:-֬`Pdzn|9 	 '>qHГJ_Ҁna0Z|3}m&ܞdq;M n	?<t-C O )Zxs>b' qdk:NDr~p(?MsJ8r>m'(<ǵuzs|Dp1L}?[LW@2.}<FAԜ,bLyjxd<pĳ)oyN'PcCrʤ9tڗ,46MRNtnNo/8$}i$𭜄b[Y!b4I 
nݵty1&7.~c~j{}=," $!g;#%^[wqd6q	"7-oaJFg>	4=JMQ4 kz[[2#8_[gڦiqZI3?
*@LuT$3)W7V)5M${.8yщXw$V%/Uy21Acf6dHWF[> ż$mmМb;;^<'g[[巤,wv5W0mp\#$27Pj0hT{#Զ|G
^7<c%}7Fjb$"io&= H$S?,*0{ׅ=KJ6,U7*(ntDX}9oRmxȽmbxr;P/ڄq3Nzt3Pne}fm
vQN%`,6	6æq^* c vZm9c|?3Ccһp׺޻5I!BH8@$UR@8ɃZ.Π	0Vol`Ddf134(b)a}JVI͌ hj#TLVlL\{|2?j#ɠ
]^<)[kC4lH\	zPY]K6UDabu\1k״I4+ M*HCeGxUK3۬;,4@\x\oO!e,@0>CTDs@){R~ (@
5!%W#h`1YbȠ)sS+*H<VPqG&9=Q 7}kS }:U EI }׌Vn"99q~hK 
 y<cA5YNkѥH	eQ 'J7T'on: ] )88ȫZtcQyn_>-kPF}%9Q@w ^Gz3E {ROa C_'5N 2 ;G^*RÎT
g8(I#wv4<ӶksI@l:I	@9ir?\WA
%܆YIG !W wFn@E'P6TuWx"/e Ïk[ysF*Cz4@-0*{{I<y'ѱUNr x%ip+u)u E!	zW(zs@}+QQ>d_):/ܬp>ʰl5KN [\8Q_U6_۔ r?* 4=[<UNx潂QXNr
gGJ$FCQp?. t_Aƹˋi)<OΤPX\ю9=# si
GZqlK<
S$D[5FCg­i8
a,$_ya"T#
.GҬF)NkXz0|y/9#4eqJOX֌`r84) JIHsߟIh ϯGNp~'? Ϯis@)9<g4~ cswOZ2}(Ҍv 9(>џo֎s4gJ֌Ҝ4zʀ1IRȠs}(>	?\zΗ?@~db~Bhϰ >RzG ֏|@!$'9J`7_Z8qQ G9Lƌ?@	@ qRJ zƃzAGJ 3IKO(2h:֌ڞԂ,p#[FIt5
B3NǱ8 (95"L}D!OR ڗ>Rg=I҄vGDiB;!Aѻ@ۚ]OZ p/>?})B`pzLq[u[7n?N]/uƀ<[v+ u5i]ȶ7W
[a8c +'Pfaץ .M+O<~+FNu p	+ԼmnK`-c
\ܳK4Idgs՜uxܚ}i'\j:?hbYڣX}iIa@mS2q 3I٣ ^g#N8)B{bRcޜ}kGMе-Q@D}a3	 }3W& Rm8.xQox&zNz ;Mit
0 rzg&)ikmAF(-4U$ kgie+0.gd~= 
 &+xYX^ WxT4:Zno?\j¯Uywqq{9VB9, =U 2O/Zo\ޕ6ُnqM+督=<ٯO7P/GemaXzO4 (   )i(Q9U i$ƽI]t{Lm? _J ck$O_y%7%4c  7 bB嘜 Zi'"YcUk|=h.n%
^RQP_B] )E s"`$ r{sYKooUrM|0[Zs~nTRX?J]#X	'>\-0nۓϩ&kbN/o =th֡f7U麍4Ó@~},S$kOirEocb3yh֪of郜cJ{fh)dHM?2kR[yv~f\3PH6~~i"+LyMʱG8OJݭnm #hҬ9o.V3 yְ-Ye$S mޱ T z}*֥9I76l]4}'imAs63PUkk%֛[V q\_jbޛ =|û&Y%`BN}ECS?a; g	I}"+IdUwVsp1/"O֑VI,T{Q)) KiDo f3R*!2[JOhcAkKYSK|K
[`zQVƏvo=t{ o (?VgR[ǳ~b߈}69="*.rEWh%@%HI|PsNJ ڲmFaqڀ)>:R	qkzHs~g+@{UE?!WJ Cgs5Mԡԭ/(\gUȸ xTv<U  w." |:?팚9hXvXֻQOw4Rl0UA3E y<!-84uh=ErDrG9g_:,Csԁ¿ qWtBMZc#;b*+Y&xgGE<
p+s{5׉tD;-5@˯fYY#=GqE4k"0XdW1i
z\ #]66sW4r ?^{Zj0wP>_V&.O_?S%Z\[+|kms+J+
l1L=iIXđtnC)4v}8kYަ2rJX٧=ڀ:zyj캁$V2e=ihԼ
Fdg R C\݄.x?:
{/QOo
F)I  cz<?[͙4Ly 2+4{1snʹeO@?J1i@Ǧ;Rd ^swL;ѻN"Le%Xw^1[uK"1\ cF㞔66.W?1[n7,717хx'=jŭ݌' e; #5_CU,BCֆ㫸+ĺ^RC ,O ^<dr:nPNM{%ޝe&.mv$so&Zn$ր8j	>SO%g_0+'_z L'wSHX /@?xȥ	KtBaL1Twya`m
LN;~hyMOZXY9党RM'?Hкy?Jf+Q~$a(;=
.AփHBgտJ:җ9HOC@ ^J011P!2 z3F1 N9])r{Ҍg?֌8qCp#<=Goz`7Q)I;hC@
ߦh '@{cK=4go@H?&I= 
:v'?A@uA=0(<lQcހgMґ} p( d?Үx7
 w-RZpESNzVԗChKS<F1S xa"&tC$\S@>tFc4p9?֓p}3KL~ue#>
9IJ i'=zR28Mmm=ӈW<aW&K\a[d͏9Lן^+BG5f20E)X |>A:V1ITA@^.j<u ]EkTVon
.+h~}+|gemm cր=R}D;y?A\ri ?*dIi%b&ct
-C[u"~ŗ 㜁q@ z4 ֓ :R31JXtۊ nx3A'=?!N<qI# !$u GSK/ږUf -%uL3ú˄ Y ^}+zve7wV9/upn(T*P  E- k:JJNXa)Fϸ3{W# Q'z!5$O| |GjĬzDֲrA}Q:԰A5HQh3iZ%(:pҰERjm5p#FjIP|o[THX*H u4 xFo2r>X
`Hy
7aidfCG噎Izy\n_##u~DcI:z}H? <NjՍΡrrz.]kB8}vzn+usՍ W?oû.X|A[ 1HisIUOSI{ ݏOyw
N#AMyfͬ4aN#@-RmNglEX62)jB=֘[$fl=TO1NvO ]d5FSs.>cC*F5izI1>Z02k5Mt |*@^=?ԟ cbV0)6`@GS\xX5rE fյi1\[2ʠZk%p}TG?٩JdN$32/;{!lɄs[15aUk>@ӷ,F{
5xb?M +bY<+)Du8|Ӱm.h,xoP6-;S]}egysZiBn'%b=*Ɯ?co!Q2,yeXG<jtD*b~Qޘc <YZ>}BRzV`#SK%? r-HA۞TGцu tQ4{5P6-R.j?FUɔ|[O=X0P$0gִ"c
#DqNsgrˑ|˺vuޥŻaSчR}^M	tt=Tאr;]5K*'`ᗳC@EgfwGNkF
(4hv;f]%Gm[H.<	Gڽrݠd(4s
tZ 43ӹ_sP;TҮDS[؎'-u`HD]c}
yp+;kx# ;Wkm!	~[wo*te9	hVYI=v8?pzǆTNQڽC4A<L$^> 2ڑmq+}Gju-JmL?+U%CJaywG 
4jbs~ʓ#c4`AK^WPXd <9vO,5=}s5]JSd\E sڗd_T7S֥^#4C2>@ꟅhĈ'%bSS𾙩e/&nE:?jV9hT]E)Q@wSғN WI  R(r#bJ	'X(z հ mY?Zt Rݣ'ZGInnb~YVZnQ* TFy4s<m*ø8"vYYnc ]w5a </t}GOȺ~Sa=2jZCW+F$m@,T Ez I\ o"%K|d~TVnln[eռ6q\G921G=Ƞ 1AgLPss#
	qCFa qҧւsGXKN]e.FW'W3=}iF8氖?Xq=:§0Ni:sʔ9Jq(hyY ќuJ	n21M S1 8AN=RƘ8<Lq{g 7osKZzzQn1^/\8)AA
s@Hb$jPÀqSId4
'_(ݞ'6qR,`w޷o}
Ю@Ҥ\#L~={Dp[tGj4Ft$q ꦟh8Da쎈1<Rv&ᏔC6
GP)xL1&o =($HTc~
QH-a gޜ J;B0& 9 X~[["~f<O𮭨a㗏ӭuzm= wM$uDK\M6)kh_΀7m#HakC^yxTܩ*Gظ?`v=X<zNӭ \7w <~K\z  {P2 #<(1M.qi IrI4 $F1sCn 1tGҀ'n R
U?t_o0?r};~4΀r),xdykc#wfK!'y V ci~t4qyi/'(
(5
pq(j鐙nXװ~=[K?6{;ubIVh<ҹwvBܒNIg@*x q֍ϰm877E_F[.nW(Ѽ)}mEkR~Yc QGE fKk# "[q=>{}o۴2A+ϵꅡ0}²NT3]6J2NFn#M*H;`d_?{`b/\kn;O!}]Զ\nר^Oz0oE
J O[{hF5dQF(h2YRI*('+0PI8k<QCHvsP_Ϭ\8~56F9 uA$cn\IcvǓ!s\3}rzMZPTz
}Ozd(GqLCq⸻f'u/(ɮ>Q%ԬI=k x*A8"27pq@o&H??W4Eq!okZ eN&Ӝ(@uI \Cr]^*6V\=hCeۅy!!֫iĉ`ҭUUXM,#r+kƓt<k	N=gᣬ1`GȿVco:1۟|^+}@s+kk6QqQ\^])-y޵"FBO cjL}ilc؀>ur~2FKGX[38 UNLE[[gg'#ItɿW@T՝WN`~hF1_MR#ޮiNX!/#gMq	N}:XzH_ALB6 U}Bw"e' J0+3YV?1lڀ7/ZhbqZB7gxNy#믳4]^}b;Zh>"T䑊 M踷`1çfGJխkE:}+2I?fqݥŹ)ހ=4f^WYnz:wSW@QK@
e<{d֖=^_»Z(LNV@Atcs0}k5[fÁ}k/,.Z$ր #WfH̶Q߅g Wirz@WPsOZx1GW8"ƒBRTGL#@3Eq
$l2NA( 9hEtn
ȩ(4
Vc=~Anm.,1\$ȿuVNbYbG#hHP w8X]ͦec<=JֹcFH9GJ Si-O]m?T
O&s ,y_'S62~킊M+ź#y_K(\shR(ȠGAAD.2Yړ~Щ(X_d/5=x{
gGѱC\Y2i X֍⦸O.	!|* ]`QF1y( l|ҟB!8$ʌP>ջ=J@֗ﵸ?S
A''ǗKuw>Һ階J ג.0~r}3Jd@,QOIcIa\2-ki9_ʸjqxu6:j_Daci/ uK\An#σ	"r\^k{k{in]Xަ˛x- x=tB5k)ݏ̿\ [, 1oӭ cd0"zVFVWNxg 83P	c:R|ޓy>ޤ'<)n3HG i&aޤb3p> r	nF>U֌ 9z}s+zSr0r5dĬriL*#
ExF?J˃7|de89?Dc<
*o}fЇNI<ӄCR;@Z}N`@tg<
2yIWBZ#ud x}auSn z449'F42d@	P)3U֏=xXjf'M 'O{+zZ0xMֺk{(ϭnod,{"O-{V?>f 
ං1H;"⋋mc2*D(+O𶕧V9~+d   =r,-%=ˎ_ι=GzU0/=h5
wMM3~BmCǒd'',HBnSL{xAU79I ۿڂqtHKt- ( _J2{␒&c?i2w旝	n> m)Io5ī,Sx"rjy1>Z
 `w' (+}uK sOltZ{ t;
)qm FZ ('' .i"Ey* W=N7Pk5Y;xQ4j5
pq7Σ)fS}TsQڀJ'یx$hf<`N#k_HU|3̮@	HB@Wu7ړD*~c=|?c'S|JJ 8V+x8ײT (њ 
5Q;Q'*m42Qw?Jw4H|Nݾx8?/#nI<I$(ǹ
 }1FX?,q"FG$o gv~HRRR9HOss~o5Fz'޺(BP
ZL揭 Q@i	\R|[O6ma   /Y>Tq3W\ZknF$tn'N'?Zi'qۥ'L篭 x.}WbnۚrO*
3
2I7o}682<)G#w=$9Y3>O k;4ۆ29@{?J;}F3~wc1hfU*z,U>vz ~zukQsm,-;*MSQy(u;5,0A(('W]VmO*(JFG֦H$iw) /5} Zz% _j/4=7]
ٖ3˚C/mYabT:ֲDXݞs5,
;#2k_[V ,#Fj(2Z$<hcrB XzWgJT*jи!S$yI Z-Qic<񃴴hHϥvc7D7qc#2?: 7jWm`1]֞ /p$q*kYobC,vO i$Kt>Xg}~ _iIu=Aa\Y;[Uɷ]99Es[>EFzr
_Y(11/ꓽȟ|TށuSNOM,g+͕{YI=ױ14ry$rF5$wuCd^P#}f 
Dl/?c  50蚭L}čm*rTK.-%ct7L .h\5u@GAZ+5
BK{;If/9^qG}i[ˌpH.[R f0xSYe5Ksʡ>ɽ{u92Idq/]MVPqRjȢ¹ʯ¨Ps4gX ֮k۔dӟÚMc"pb 3,<c ޥ
zU]:]@YFmky#[	a}E<vhsi[t1]懬X@gӮat PW9sFBLzUXJk!4NĮ=zSx tޣB)v>/izƓz7/Pשiht=Tאv^:WNIY?Ĥj
U5@J;YkSq)5zJ mk@Ѧ"E!cL9\}}:Wo-ȯa^,CKmՐ?P*FKʞ <})v	 $C@Fy;2~h½HO&>Jts<2ʲhھf/et vȲldx4 J^h?Z Jռ9aT>I@Yxr Ib̞tAՏ1vj 0@ _ַȋi} 
 4C 5j KfuFsY<E t_/l}}{mvNۆy|)H/ `d<|mwk+8p?v~eEusz0 E;7]c$Cنk
N=|]jJ & M}6<7U?T;gڽHT)"+OvWy{F6uOڀ<ry('o?kjZft]NWk)FN@I JNOϨLmw│pAV?ŏƓ%	R}qҀn<,r(Xg	wBAƚoι=;xN4ݨytC#SЩȯ Zc_XKw? za~6ѹ0ߘf hkΡ䋄;\ӵ>t7
P_xT3HP2`>Ef_xL3[*8SPq􍻯;L}p?A5wVX? Qz217 {R)Gc|?ҔdP1Ƃy3Ҁ9a4=)~:ځs$q2G8<jeDĆ㖣={zQ waTP>ޜfH;sJ\`P YB }hSdz暤NsKz * s&g5jA!8S]%/&!n|9=@*zM#?3^a+O!K |q 
 b8F
t_qp?:촛=qkl Է7Q.g$ݱ\֡Xr0Ïo[YZ45ʳg皏5MGrrR3 ,@ٹRܻ 3^C%̭+zT$HHOA SLҐ9#F>).8j M[$ ?G:?/J q$zW qs( AF$gӊRAR`8n3@
W6yJ0U:Q!GE{W[x5ĚsF6eC9~sMFb9P&K[+k(VФH;(Mހ*֚|^]	jPEPԵ-."3=r#Vvj!Ҕ$&rJ5ꥣzFX&[|'j2sq4 0mzt#末Rރ)\|ޔ ñZaFF9WVD%|=j.KEkA?S@/cl	"_ZU*U (@x 'Fii3Qbx -w:$pX ~
7WҗMےsR}Rr圎/Uc#
ctN$z@l qKr1քN늹i:Alz mi5AI$p :B	ķg}\t+]dct=MjRƏƖњJt{3#ҷOP_!Qs^c,i],ܱ/git*p8$  R3yx d8Hǭ 19sp
79Q4vr*VmGM	չ|O|8Il5`3S^i@drߧ1iּL[ܭз#
pAncRD*GmjlKzs8I=A=ޞu;{pm2J KI\L&/;ـc撊dd8jRҴYn1	91?lW+[=9N|%UY& X)hp&!Y2WN(yP9Yo\u?V"O"n컆G&7d,IS})W>QRR$R~zV5nBl;JrkR+ԉj)ڂKL$=h2*A#kuƨk%Sw3bY$MckGn֊CJ݃E03: ԏ 1]X+M[+Օ+C]3G<K,LdI
.b:2Nv/]åE|-kq3	cyArUlb1Z_;)Q\
b:,:FV{p7d8=jcjWr̩H<5ssxn%21b?:湝9n%rF@8P}Y*$wZ^s3S늣[,cHIf,I$I2H+&#X>W+ COA]j/8=U
 Ga$_Pk:$@p`hs,۽=qZw^)P 4{}HW?1e텽[]QY	X=3ʳ4htu]LM&[VFbBzbAjV#[Demsyk}y6B?~T$/u,O4[&E
se`ecqȃvI?Zk4GGv)bBj </wκ tW7QZT~¸Lr}ޔ0GjÚi^${V:xP lCo{%_+/ 
rjQgQXa%{t٣^6*rN5rMSQh7i><P閚nf+vLH;G 
o}ks-i0.MgUJ˩:v#ӊ
^=7/Ԁ}m 5̓\M{2#|e9:":ٞYt;'j4"o;RTnI* vKu9.0%Yw;ab@p9$48<*?֚Ӝ]qP3SJI>CH5:k~ğAMOmz2C@EfŶf'Mh Z(G LdsKAG>KZrsh=
pSG$R<REᔯ"5[k1n Gp }hV^䁌zѕ m犵]w^MeN~R3L?_Z PX>xGj-?4Lcv')ŷX`vVe@_?yjx2\,^1]ΉH
XN_o uRGz^( 4(n-qȇD
.嗩? Y`hd1̎Xt ;^h:{na]xaJM
$ Cݗq@PhߥI%z2
0&q$c^9"Q8YjmgIT t>pyߎkɬH?fRhs+|tFص8 !-*s@ъ1E ! kS𖛨q⒀<S𞥧e?D9/ǸXa@핕xwM@^G m) }>j^o2~K&W\@	l\zC ,I8hNG\цz֛rpEzPA}4NQ'qF? sc lP%v40 ٰ>b@I̱kŤV&r> Q^zvdR tǸfIo2J6jVUJ#562[ѿ5XxQnnw#k~tKKV#o!(ҹj佬rjt iWP` ?>S KW1C$M9ݟkxn${:+Vs/l+ v HQpOں+ jnc돡Hd(ўAh,})~n`zNl$@
F 
!Y Gh cm ^=8ONҜ",ǢO^_ Y8?[v?|KHzS;SECScuVm0qּ;?玗  R  J(11h:*
~q_5 ~0SȞ[eyU5zp*e/}r/7% {7WOOgh ]?  9eq#PZ?X:i2?I 	Oƀ=,FsߊRvڼܴ gh  X6Z߳4霟cT+
` gi??0F^  9,2F{יq L i ~㜒&895c%?G,
d?@ל4-Գ tW	i ~Զ ux%k	psH~TMWKDPϖ
?㿋"@m ?w/Ͼ  A
B("XtU.k_~. }+  狿I w 1GzJ    ; to/ ϶ ~ o~-+o o.>s2Ƹc xtؿ'+¯~(xQ̺ki[g Y v  ztIq+4FnK7&G l ;-?  *H}G4N}xx XO0&+6m Pi]?k~~g#
w?4\ruOHV,z*0 o_- M'? @HzRc/ Ϯ ~   to/ ϶ ~ ߋI v <_5 w_]ߋž?ݿ . Q-{;:|OsĠh:x /wkv<xc˴r?@`AM\Ǩ3? ',grK0xp:m?H~ k'?%?@hzȎ- ^i]no4eҖ5wҿ V }x_U// 
+  :j  ;t<_ <4o.>֐_6ҿCXi_] }jPiOs;aTp=OyF\jג\LGyƭgĺ˫]}*}HQf= ߯ zrd;xy$`gg9k ~^ Tƀ=<1y9.Jb 4 Xmq \_zÌs?@ss(x>xw885?u7+oG תk_ tJ[?ﮕJMVjmNvOea+w?i?/GO }dT}_Edj7?ioO }lT}_* } G o/ gz/@b7hѼ7kR}o* ҽI~/T}_EG8C<]tQ}
^{SP1 F8N57Sdvk_#krď*#ExGO/ǺφZZaE: iDǤ?ٖ]~ݯǟ wL c R t?U }.P.+_^1  ߌ1 ;{ 7zw1C#Urp>Ly
3  \mW^kĵ_.-N'Hj&xSc:QJs6 /o su*C}1@\pwM+GM8߷MGۦ g
dwFʜT mXowB* uM }c_٬_	 7Tڅ?fB  ٬{)G% g
]z45lT/.H5$3#ְEæʜ5+o@=qQotX),I^P/Sa8O z(q*Bø,_[ ߿I 	ޱb Cgt1^e 	m ~ Ǻk ~Z^svQ`0T5[}Zgqu>,
kvOzU-l`DJ3I_5 ?}xxU }++_^/ :_ K  J v J1_5 ҿ?}x_U }iAue=u>כkfKw?,k ~xxi_UG?_ml0T=@[ nW-h`A zZ ߯ znXAIY?<k2  }[d/ {V$fEO,_z.Zj[YCy_{_^!rcGǟ 3}w/-/  ik_~0 :_ G/+  3_5ҿ?}xi_] {k=H"g5M*Jm8Sd*ߍq_ <to*㗊!h6*ă PVBN>n[9"OZad`ԟuZߣ4郓}jݝ֟(V~|A@OƏXZM  }QjW]7Q	`dFs_$z9iƬXR.0h#=Fh:J׌?瞖 Ta <to*>%| K v }x_U })To-M6[ч_< ҿ?}}o.=_S4tju߆C\3[KODuOߋJ v jWV<ճd} g$v( c>3oZl,מ ?+N?  ڐV )^e Y c]\ ?@~g{/ur# ghu0#s?@iw(KLfƁZ;-?  $vKm#> u>KN? _XzsOpүYj{nx rkakXL#4Zߣ4.R?	t杩kf|Or?@Ȍ  }yP]Xަ˘#_2Xm}Y̘Y-{5w 熕  x\oƹC,ЙcZ!cם ҿQ Xi_] y]Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@Q@


================================================================================
FILE: app/public/images/tower8-banner.jpg
================================================================================

 JFIF       C 		

 $.' ",#(7),01444'9=82<.342 C			

2!!22222222222222222222222222222222222222222222222222  @"            	
    } !1AQa"q2#BR$3br	
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz        	
   w !1AQaq"2B	#3Rbr
$4%&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz   ? zZ@ij-w4Z))s@-'j^ QEhKIGj Z;ފ-J:E RbPf4 ) :SwQE3u. u4 QFh){E ( K@q;PG֏ʀ\( %.(h R
Oʌ`e@4̃#xm0GAalGN ֎2 Sw(!r)xq )U֛wQICN ?# Z{4k!u`P U Y ^OOWI=0^ێ{S{=JkB|.)A0F)>޵DW(V9ǭ/=j<$ R${O  ݩ7 9nuӃn^;J(Tg4 QGj^()h :t=i)z 'ޓ QFy@~dP9Qڎq@?*^(~ހi(hf֎ݩ* JJSjL( T( }Hd{
	:@u\'4õ}:jsCmSվ3𦪗:@=BHB[,9)^s|R0@p>YZ MB2vW m dfƽJo'^1f?8%F1n~[@

XڜTߕN[4 #Sy aZIS@U4ɤ@	E- QKғzQ LQKE 'E- _ʒ
J(LM  ;:SwnQMFj u%&M )ϵ -%s@j(QaIKI@%-1E 
LRPIKI@Q@	Ҋ(ACqMG-GEbZ*0O(cL	)yGwnE&i{PEuE -A^Ԕ QE hirh )hW9Jw4~ igmތ|ӶM uFc@ b;ӷn߭Ol!:}vQ:QPE-0
(() QGG@1Iߥ/L?
 1F8(ϱ3HSzQ/N84=0H&ҽ:*qRÕHa SG$J)" a U/РIE0QUޘA*FˀH9I+ACJw/ 60@#M)"4M sAÕ4(P#j|gB)#L	
cNF?*o>R4 Q֌\h?*>Kc@	E.~g= %(ϱ>ƀ(>ƌ ^3z\C@?Z3ƀ
:3b\i3gg@d{ё@)Uq7`} '=Dǹ҆si?2PҞcj	n
5W',@*s&N)U@ y]
F.OݡTmR}KzRmGAO>d,z .̤/)N&
G@
OzS
0(-ɤsғt L{Qj\@	1K ~tQ &>bOƀ
)J (>ji u?s?7i;
\I4m>m> џzvFz LfRfR
 f
.SOQZ(RPEP1(IހIKE %Q@	E RPH JiAI(za$RP$E QE  RQڊ( ( cF(qN)P8{4KKPP;})phf}i{ (( Q@8KE% sG@sHI@dbњ ^(E( (EcL1E 
1K@	KE/9&;fb{&)G(ǧ c4c J1җsQ_c;яz 1A֌{P 8#>穥q@z(M>~`4 QF=饰pHPRR	QE -ʍPL}hsPQGjLZ u n : "ێRo鎴 Hi)Sh s{P9ϵR 6Oz9ҌRG4 qG4 ▎O֗ Lb` qF
 _ʏM9 x
J^hRw4 u=())p}hGh( J)*LPj4dPKLis@)0)i
 !QFKޒ
Z0i Q( րE Ɗ'f w4Sw/';
 }%0' KIz yqiSh,}MR(񢁅Qڀ@	E- PKI3@E&is@f Z((zKE c(cڗ֊ J)M途R((iq (bZP)1I I)DTtPiZb3#P+Q(h Z)J4 bOK 1Mɥϵ 0;Qӊ~ihit@
qj6Ҁ 46縠)
 ;<Mw QFO J1Q-0R@9/)h) QRg N}():(?
;RL
( RҀOҗ4QڀҌO^x4aސ
)P?* ɣ g5=82O?֏?֣)Z  f5SG=	G1MCFhX<#i9 N9i@LB  c FGKE :gږ O>쎴q@	cIwj? 4Rǭ 'qKG8guGҗފ m 'f𥣌
)޽i;h
)4qKCސGzBðe'4ӱF(?w@;Ӹ	ZLRHhRQ3@!E :aڐM$˱=hRu"xzJ ySK O\Rh֜V n(~~ 4bQGz J(((4P1(( Fhъ)i( ( 
ZJZfE :is@3LQI3@4 RR@/PE{PEPE- b((-h {֊(a}b%P{,(أ$t9WަoZO)sP	[R٠	h*1(ր$3pRSsK`- -:\F} QE LRi:t &E--r $p3J$ (phqM|d QM =Gj p4p;Ro.}h <M8Jvi?: n87Ҥ4Y4}U^X.T;ۚVe/)oƅ銷Gz,o6:Qw)OoΥ&qSҁ n)@KޘRPbGz㱣M9t /M.R'@f: RqAeA qI
^~4 `QE `{QʀғtJ3@ db8ȣ? .yϵ&Ej 9EJLy4랢Gjʴh
 HzњI7֐hcܾh4.*<Q@cޓ =;@	E- Q@( NPh( J 
 q(I )i( Rdb4 CI3@Gjn:3@Ţ3IE .h% f)( ϵP0
(
(hRdڀ(h ( ( E- QIK@/zJZ ({S4f(j]Z vh(њe ) >fM.M ;ڊniwPwR)4 c((cPz1G c1KE #naޛG@0 RvZ h5P"o5}|( XԡǨأk#=yT/> Zj-iC8hris_1 LɞGin[ڗoA@*H;Q0"yZ_;ڀm?tA04yޘFqflR}hWh !ҜyG$0H|'oG⒗pp 4Ҁqъh  9z7ui7j uǨx= 8Yx& 5~4ʠiR_Q@
>U=ɤ~Gޜђ;d;毽 xi9;y=ɣ_zO9}(@M;CRyҀ'sz
<	ɤA?&5X'h;Uъ /j{ъ \w4h*0(̧Ґ}6 ]M%@ƚ9((4fj\R@	1KI@PM &h!"
9(Nh)7P
) :fL }̚2hf(٣49cAjiE 8)3I@hR KE %Q@E))i( 
 Qf
)3FM -
Z(hE
(Q@Z(( B>cu\qK;GF(BR(sJN(ҁړvx.(ۃ@}sFڀuF(z`0iQ u{FE)$ Z)2}> Q:~n4 b> w?*^ &P2i)h 4Pqu% nҀPKse 3L@GҀGze/4uܜQ@FM >fM.M ;ܚ2hRdd&M -F Z1֛w .)qM=)w{P .=&KzSqE&FHcFh =)1i7PRfu ;
MncF)w{P!hnQMEԟ7}& SwRdn'4}%3&>9 ~h2 ~hȦRP1z21L MZ vM II@Fo9v(i( % .i3E QE RR搑@( ѐ
 QJLҀh 9(i'4;M 
)M)ϩAZ ;QE(F)1@#ގm NiOJ\Q@	J0ɥw)
(ԴQ@	E-JZ(RE Qފ (QE Z J9	AZ( (  JZ(( w QGj (- }()(o4{cc@SE %ڒF/E &{:R4 SKۭ;Py^h 
u 7'?Juh2sSϵ&y: B=()Ԙz\F)q@G~`QRPFEQ1ڀZ8Z攎{P@(#4``
Q -E `cc )qI(
^яJ-w QE RIIy9@EǹaEEuo /󢛎1Ks@6@ PhaGJ@(⍹ёF(h "p `P121FE. (ǵ &q@ 4@N:3ԸF9M &yHjv=4 ܜ?.F9.( !>Iz杁E 7N/@ǥGz `Z6ӨN})h4 ( LsEPb^)hF)qG@	A QE vtZN?*(?Z:PIKA@	QKE %QR( ( J1F(4 bmZ{яz 9Z0}ip}hdѓG4s@MJ9>ԹҎ}
 .FI?@Rzz? .G.E7\ \uȦG 1֏ƛǭR0=ip=hإ晁F= Z v)i9uZ>oZ Z;|޴eԔl'PwAK@E&j7{Pzn4nn -dPIR QFG dzzGj2=E PhR((R((F8B}(֖Q(b\{PQK1@ ;R0z1( -LQih J
-4Rъ`'J: J)qNRMҊZJ 0( b	KGz J)hi Q@
J_z(w֖PQKE R'JNL J)hiؤh(.(?@	E QFG#PQFG bdzdPڏ#ލހ
=h=7C@E<t4 QF44Z)7{Q@Gjnq]ҀMڌj (&'֐GIIϭ00}RbRG) QIG qG dQIP7(FiiW!ݣcch\ktѴ trʌCU(\?:F(\Gg`Q`[QǨ8hX.VRu +9
nKL# 
\SP:UFB`XؿlOv)v>O,+6JERv}=(=*ǔRz~XW+lX?Z<h\z6J䧿Gz6}j= :<?;}}XW䯩.Wh}jǒ?hG _i֬y?<r>c kILs}rxz}*RqQoڎ}NA
ڗ?(_j9c?A@\ϧFXG?*~})yQ7@\J0S
([P?ݣՏ%E'ޢ 4~?([P?ޢ%{QcS-G*‹q\}iXaHZ8[D@ix5/-?:`A^=MM?\v !MzTKzΏ)LshMM?~t>A7Y>/SzP_&}o))x"TB)S v#TgޤyO $ |Sv"Ͻ<o '֌ I7M'4xF'4yM@QO-h#ϸ>'4yMHFO?o<di2}i
F8^*O-hM0# j-iڣ?TYa'Ծ[tM E ctѱh, isicp\zKopCǯ`z7HYm.#҅#TqٙZN=MZ{yoʘba,fd+ހSI<sJ}(>=.~Tmo EǡCRo67M EǡCRo67M E?Ro61@~}
Kh4ȹ食Jo<\Rsڗo<J<h|"ڥyo\R}jRJ<@NR0}i9H?c vуRyo֏-(<SFRjO-[z
,{xi6zoj<r=h|Q`/ޢ>(ǵIZ<,#ǵ<<\T_WE/Zb~4R ;KIK@-'z^ b;Q@EPU]Udr""23
pqSsڬB*QK  [4}(.( wE R 'J?
Z;GG- %- b
;LsRQcր+/+Q8jU4ib
­S1K;Bb)h &(Kތs@	E-J?-uRъ J;RhL~JB2
3T)`He)hQKF(QKE Qޗ %wbԴPEwW
qU: AҦ~5 1F)hPbRQ@	LS4LQZC@(PId?'lzG9ΤAAC,Rb)1NQ^{PF)i( ( Z^zCMVdm,I~VYxH"HaFC[9X\rռgk0W̩U޹	9\FčZjҗ'ǩwe+1Q)>Jb,[
 
ҬS)h-(KE &)1;% wP0Gz mh4ßsUל9ر>E8r$ySR 
4ih(4 ZJ ))h4 )h4 J ))~P0-%/Z )h ``ڊ ;EZ(4 QGj ('w>TPYcۚvsޥrBdn}j_cQ(XOjSupSBaE- qEp(?h xS;. oz)qF((sJTdui鎔INr}(!xLPQKޔ)#=Z m(+!^ҍMR/pj>"C5@A1qHbZ110P~=)]w'֚qR6i}H 9+	Aiq PQZ1@	F)gM/!B*e5y9;DȤ?JD{aqXJ)~i.%jI D8|)izcS Gz(%- EAR${]˟694g={PXm-9N<~4 Oz)# RPQJh(1ߚ^Լf֠U@	2{qSOҦ? tƬcM֊svW4
 ;)HZ N)FIG@	EvF)}<4QqGҀ

I"`)`DOM{QOs@RQG^Pގ(Ҋ (QI(h (64 j3iR툏!Un=irI<>3ڕ-<ԊP
\s@GzZ@ݩqGz O׭(ҀRRI/^v? !ii?
 CPNS'Z#n$4 H)F;FiaLej{4RSR@	IZ((?JZC J)i9!hbJZ;!( (H#4b=qG'ڥ&n657#I662TRd?ZVF3Ph(i ҝ4
s.A唎3M#\&LQ@T,9&QN+
O8.rWi\v"F=]^0T bn 4c)T9=Cc߾rTd]*䲶ze&֎,i_QB#3BqӰ:SF5r,늪è*kI&BናZ63JGzLҙ9 nOo5E0?0<rvҐ)# fƲI< dnNoB9Q\!q֜[:SK'^mVid	J9;%=iP1@N?tdTsyM}
4Ρ4}<3EYM'jvwgir^ˁE45emԮp@OR<+uw2Q̅4 pSԩ6,6s'r3N*qӷhC7bS偺Fۏ'+),r;mHُrGqZxie*$A˞V"HXe܏z\m+ШLp=AxRK}3YgzP~bJGj{=1EQ8
If+sU2Qubf c'ZH}W  qR\B-dqҦ]A8.f0UaͶ
^!e;KyOnNB)m RIP#Oj7O!Qϡ~\UT``EFIs	a5M;\-(#b_NkoKR^XEq &{W }DzήK!瑌uTb]
[x3HEYωb/c R[[\ݸ[4*Ev9$J|)^aVn(]Q+&׌~nxn-9#E6_N3֥ܥc7`*FqڜE1xnSZHwFF⟪5-ov<~Znbn cm7|Oz}o<kn/^A hB0\<cۜY{_6h+yRYq>2vz8ꝙ϶b[OjKm*mx&@ԧohhVTH955 8[GL^lar1:k>,NYzsH-S}ÒNEh,WVaHUZB0|Ǳ]ޕ]7`mdBTv9NOarǩsYC [7Jп
=O${g=jmjf}
1i1eÎ~%0*Z= *#F?t8Xun}B9{VnU/F0c2$A S#;6Rq^qdh`~qb9{9i'fcE`	i q:X^]:eMp+Qcjw (3	Q-qk$adPq\1/r`ȲzzGoJwS3o$VkW'f	22g#UPgC1*ԥj
g$q,Ak^E"x.lS͈Ȼ/'vzj%QGpTυQkrEim$V!Fv
*ܺ&g[yWR&gbE	g:pʳݦ6TV4vf
By*V/f'MʅIҪp;Vy4$ԣ"@oz'c<0zLE$WڧyShg2(crT65ovQ/3L\mvGN1֛LMnP 9p}~z19Jhޔ<ecTyOJ.>vGd]+;:Qx\'*Nx-5_\pCnWĒtb	]C:c')#8hOPS5ı0ݵXB~)O4<MsuЈT>zb:f$WWuF)6 kӽW1,Kg}GE'J9r3>8rCK?ҕ
g[.6&,9 Vs($9<v$T\q\%#va$HsV𾸛i>NIk6ys#<=Wh?!S_LSq^kA?ޙSIU{QάIޟY\8'񪷒)S#8j5n6!^~΋2ύ:ޮG2dE6J//)J1:I銮b;9)w*XkD	Y	w ydm!wNץG>G 
͏L?
vp{51z@8*9:85\i'Nؔꤲ>M3o qG>nݨW+FXtҴNTy,Trzb$7<uPбK lZ(eWѵF[m L|uD^A=%)tnqzwNQQjcI!,N=&$`(ȧ3HxsRBq2I_iګ6y'4`zv6Ac?eNI$%ԁd`v}9$BVwԶy@&8L"#asޛH#`؈:8ɔ+nw@2P0zUEB+u @ \سDQ@F~ߓ;`x <K1(Ď[KR0sjjjU:={
"JN}C%#rn-wP%9)>#.i]#jy}  ~s=cw$*gheX"(zfQXOĒ噲sy'Z6ܭg'Ҩm\=ZtdRdϨG$I$uҋ÷ȭeM*)a>1U;H,U~nhԬͼ9ˑ2B<5\RO8qΙy<`pyR=/O{B ڰ	 7stIobÇ<nG.M6JN ȣ54s*i_e zH
BHYEVm1ny lUry䴙QuJq*Mtэ6\o-)Q}b?AiT{s$9N¥}ұ<SvQiXfLs>?SV5GT=PqןN?G6ui3rNqYh^/{X洎p&1)!}3ҭ5xa79Cg.	j
AAZGY	؃rjMJ0 >'|u6vinn7F7*@+zp9RSOa84FF?:23җkF:r}Fj+ʬb;1O1iLl2#JgOGcNK5(S.1J&A=&)phǱ#F9
I	8.^G*Y*6zJbI'Fr>YFaLm9}BĒ#j[vndPZc6*	PziIyqK+ݤ:DĎn`֍M..-5
bkke VCTsr9l? ǽ>.C=
vc} M/ʠmǿ򥶱AY/^5{|T:)wGo<ɘFHq~u5匶7aHtvrbYN xJ-cv FKGp>IpKFZݣXfp[>MgKXZWD22>ky3er U!zλYfR)S{SuH(OvbxsWVoX?yJ}}*
FG}*;d봎+]EGN	dD;֫[G#qDؚ͓9|f^mH|Fc֘22,hY\#Ӄ]/ :=,16\Jv|6kIS>ݲ:9gy^F$KTccǵ3C4Jr09?/H;fB8<p+DbШɏON4+vT oZ#=j\g(Z9繱tڱgҭ\IyHK&
I7y}AXeE o!y8Zs]^XAjn+~eyy|fc(l{U<8%JlC91]]14o	F=hN)voRYY31s9i6:sH"`ʯܘsJ}ogiVpX]7~P:>t#a( %cὍnigyE-Ͳ	fYQ0g Fby,=1G:}ܽJ^S*E:ice8gEUI#@kve,YXekz YxgʡQg?f$o+ٻ,vWRH	.wƞ}+˳v5Gkm:#EN1<
ߵ_k;ڬLE]]rS*{4[-ձexO!b,FX TOdc$@rH=8
Zjvs]YFB0 ap$*Yits#wA
Q,Lx)6siWk}
R
p~iLa^2RGQ5\xJB^I2|F5x;Rb<=!Vqf)BFff(s,=;S-D#W{e{og*m8cE2*G VeggeƏs%Gϐ
MV~Wďe 2'RP YI?昒B6vn\3  FY<RҢv[S
,gaԡn s$d4:ai	ɭco2*ţgS
y429=ꞹ`I*90]0##<OsjN-RYPvbun]^IY6E}gnUW_aMS9MC9Ȩ]x5s#no$^3\/%G>oko<f`IxD[ԓ\-umE=:UBP2tSd鞕*SS)^m:#LP0qj%:e2q\׷EY%f<	$_%Է-2s$$#; ©RڼRڇSe<{v#`81jM$k`'yvyxxsB [f9=1׌~a[23ɷہxT}OkAJj``8>W[$RP}:ް!	)wfy\{P]UxZ/lP3qZ$/[1՝% 5QTz߭Gz4ccZm }OQu<hJLo$1v&Ӟ#.<QuVE\$"bTt;$׼=_$3GcO~
H64x$s2y<¥^O'{
v^]Χӛ>/Ϝ9꼾 pC3 Qb{V%y,s=}iӐKd`Tt5HKrz{ZYv`rIw5X5=Jrեϗnb1+G=:ZZo^i|A# ZǇKT&RE/ Ee{(ʰ9=^ݩ_,`.0`jT:Pg qϧQȘs4m!6]iQL6'c^!:"ɌsY]r9$~4[r;AqqbIFXU7 6u ֭CoڄWW"890\quɫ?oeI)@[U?һOMGdбednbflq+#
9\9[+{@&@eIAn`Z H'i?('t[4FL%8FwVF`R0>	G<Ԓ_5K4 J63UzU^]\ZL-RD#	(
 "U!Q*1 <`
oRI{-ӥioi"1.	les6Wt-Mʻ~$åv4$#Hd, W
s$8*J'=ST渚fw/+jJv& 'R6ZX\3ywh,$'%zug"le
4޶`8*Uo5̋o]975̲ 

s6.8ROuWQ};Jkr?QJwm%h]&dT;_SfS"DY
1M_X'#qn^Y{8˯	qaTIdڥSZ_NrO}=M9+7Seb"	;Q$4[Q$E+1s،tWW2%Xs)RjhZh+#	.G1F}6J1]Дkk^22C>G^U펓"I9w/ }~aQ7˻susӸ>F-mnZ;DRdh'bG1.]+-Ѭ2:1cci!+b#7=IխTRZ)c 'G̰0l$ r+K2/Ԟլm\M! $׍G"H#m<oSN&d[X< |
j_KYz\|Vw%ӜR9 qrjR| g`	؞r$H	1ΩCpdUNpH*}
Jz+ ֬ռa(	ivX2x>5->+.^F#=ss*\4Dx

9&{Ag-V)sLR(Ve96BUZ1mq;W!m b%$N1kBLfs'R~p9I2 mtmHƂx#S\PƽٽqWVo\dm=~T5*:DE*rUi$gdS4V<DN{(W)#f~s
"K.X[(V^Ǽ[s]KJL{4L)C,2I#A <sیZFi+A3ت6-.fD(>^B}:*/: 41FUrߕ'{\E^R~;r>q4Ҭj2㟩Fs	F3
S7(=ɳF8=?j|jO$1%p=\IDm#~U>q cfę(Y7gՋu
nDN}:UDY eAxTK1Q,{zRXinSk8'ݹO@Gi6Cp7q$zS"Oy2J;sK`WYą=0,_|w3\ =3{f73f099)-K4dlnwmVFC2$1cx3PLJ"KO,UrN1Y;Vz\q0ܰ['w&WzEuxTdF]ĩ=:~t~	#ϥ*JMݍcF"2IFG'*D* $fnȎ;PƋGEj|l8ڠ*ʊsҫd b-\/ύ)YMon3+?!2*n܌ژ 	=NϸhOo2N<Tg68c|GیOV[ID\<
?c?LTY/o;0N{Rr/-z݆d8"$8:Z}SMQܸ*AXDr9)d\qw&Hh)b"إUq|o' 1NByCc[3 BU<zT۴I	 JKpI&Xԩ9;4/QNGKphJnNhQc -_F͘<g$ԯu+eIȪR9$TL:Sצi>3Ie~0_ZM*-sm}E
q~U{
7ޓȮ8c#+<'X]*[ɵz0)4H3rYF3Sxt/ֵ]
aǘp{v e$>#8 _Z$e&1
ۻZ,2atbG'oZMJY WqU!ΎSQBe~P*A}>-ί,	h'	P{⤊#`ȉrǊN>i'$Og`vSl`nmwfF= <`
b&`|hT)'ޤRYPXҨ$O<m!Ijp&UIv:An-8A)9 'K3E "2RqOAhy*hds}Pu$wk2Hb?J$rDdR9IRrOs]\.o  Kd)Yq̔N9Cog>iTGJ^X|5ؑ8;c,uV|seq_Z<FlNAMMA-:r_@Ay<rm*b;a!栎/07̪g8ϰHfrLcVvvz@qR<o77!?Όt>~oSlgNUƉn縝Fi\O$bbF軳fѦ^&IGl@r uhV7rL9Vb761n_8jծmg,s&b`<iun汦v3q!lҝ	;b򘅚!Fj C;Ю`T)J?˽Mrfa'ߓάhx"S PH!?-lrGU[	Ą*PF.4"IU
R=ۘ<U[x)XJpIR}Nv1Ua)ե.>^QwomU:l1^$`}F㜖b:WVqc3 kYpd sKun?s<#4gˣ"}v:[>.&,т֕5ޡi|iq;"ֻc @aǥq4ۚG'槃TɢFʮ@jSe)S;H IߣseH0+|<SI$ޣdfZݑ)'㸡Ocڝj ]%49am5ΰT>2ˌtzIrDшՍZHtۜqL,Q+mpH0Aׁ")~1K٥|Md}f߄D1>l{"ԓ87dFܷVM$4Nuxog+9sިٕ]Sc4V)lCm5ĮVo>p}*\(b^vZs-бՓ'w*+!s=jQy!tO˚P[;smn͔v5E
)>fW%YF܎@  NZp =OHGH0mʕ'ԦUҸi;7cR8V\X9G֦ntLUHU_ZCک5fBNxR$`zfLdcHX9Zb֓4P?Ƙ~#uҐ8 $`@ީ߭Zj oz_Sڗ☉cX% )7@<:VnNǡf{yt}yl}-	o(T9Pţ##z2h\piyEFJy0Z(j\bbױE[S8>'eqwb@?l7*k1VM<
\k*d	3.`
_5a8@ 
 OP0Թc?5M@isIKq'Z(sFh^=)lTڐG!2q}3)yP4,xs8vg+ѐ#bv`f9?>I$Ozbv;fPzm&hL$2ME'=R迥IQER E )@ ?0} J͐hRrh4:qI֊?QRg{w)I`挱P߈VE#
XzRp8OJn	(ګG&/
~}4 RzY75#/ETfdc>͸~f7c<7wy94QG$=$xUPqL@?m+ :3օhlsfO9/.,ffhe]ppG"=Cˁ1SFh66<g?u.6OjKy!]ҨSW8?$G#&>G#QRrWLSu-Ƞ`Op1JʠҔ#-Č zѷ18ۭHUI&PO㚯3a@""r?*4u) gxݤV*z*MgzjR5ʐdފ`bF
ܸ\Tb+ɡh}2c^\[KC)F Ҡ"«c5&eViC۳ugj2[F`z{(.Hr NojrOZiG8RNMdyJQqչn/eWUEFAFHk3?Wwd3.O9uDf85bΰ@AaJagmyA?cĒZsOZNk8! ;.*{qP'w4*CV/wW/%݊^Pܨ
·*F^-ej⫕v[KHIq_ƈc{K'.<2眜U33X/+${cK+dSp /LғA۩D 957!mUONU%EUfFPGQS4;
āNx)6./nPeE$]:J(渊Wh@˼.{T`BL
F v˖]Ku$֬ocst>]KRK:aIm4LsTYPB F! 
JBN6ϐ
:/׷֥fwx$BŰ> DR0֤w{i7e*Jd܉Q1U:Va`R'^i,	'<j $hC1mgjޡ-Cd?pHJZ4$ dU_0)ZBn)قcBg?LcA9֚i'X!r<:eelgA7ztQҬi@8+4X1jDb	4R[Il:6	V)y7eqpQޓO&54rī(##:XNz/@cqOql8;/ z'"pzfkɄl
/ȁF @)QBZ[pL vu18LsHQDW%(:?74Y~j̷~mQ~t@sS4g4ڸ\2" Qriqxp$MS =B=T'&eP^Ma?3D̀u"?5&@o"A,3*0ҟ"ٍ gޠ.yek&y]mE17lk9.Ռm*@ø\qjΉsinK-\#7斗
R+5_.9 ꎠyLP1=!ʯq;X|ReF ZM2M>KFX6}9?qj4m/-C+ڋsf
w#>T 
,cFgF],Q,.ڤ> -[bkIVn1Z
qbgT-,ܽyϯ5mq1+-Y͸mlҥdRAyrF͘랹U欵bw(rG^:ԻguɈUpl>LHE܀qQ
Zih&K1c+~P$
 0,H?*q}ՎuLa)l8O4;%+S4O 7i61FQ:iCW<5I/+o3wzaCy럗ogqt42K}sKmn3*QK  ?ҕA.vNn;b[kIn~b
htAH`juS$3xsߥ1J<Ҧe>jI
br).o+1D׌JyE<DMP)	nN.40ynoi("bzډ<5^NqKO4Q*'ڂ)JKގ:~lq9׵0s@Kwn:ϵ2Ȣ@4h#lݜ|sND RQ1s&8r;ڢڀFs۸6fvl34<u	'
SB> eA	e#|F&vr0o^*!RXg d;Tw]E e'4wЎe,~K zQQP46A8~4Ұ$ #]*0ރT5=֡?i.dPh],y;BM2@#9([ztyHRjO>{+-bh獊0SBpza'HTGJM[z<KE%*"*dct)0=8.*9h S  >eD~T_+z}iH,
R˙\m>֢EmܒTb0̊WEKFidG|ޞhE=ͼHG3vmOQ תdӹxIP$(r`JF
D*ŵ	&E$]kpèvc:̻A,㚉i	-TJB3(%@#V}Ou*O)!qߩ59eBKQ/
-1!WSy	_7]rG*XA 2C,b.lLǵT!X6YQˮH\(rN9(Cm;OC
0(Cз-][L@>%
AX[\<BhqTJ drq3Jv `v_\<
$r(rlzu4fPm_Bk6hZHܯF5 RX|Ǳv*awHTtnZq#K&]ǩN*J}>5n# e${S@
[#i/]ɵ
='6OЎ1O
ѰɌmL-F{Ȑ$cQz
M\KA) YdJbJG4ReO 
B9	:bdt@5z[D"ẊH`ɓ~Vƒ  %H<vmA\x$qszjx4k(Bls{qFqӛuH!}g*XϧcRG̾ Jy惜}i5t	ؒ-A6 +#vnǶxMȖ,8t'5\gvەI![?
m>Vnʣ1 T9h
[.cLPQ"#Pw?ۿ<U<M)<&pv{)#TgFP*HD27Mw)i$pQ(i^FS#9j,2&ɣd|g1B1OyFޤJF߼1jQҀM$8!:m<,[Sc~k<6FY0rq¥KM>[ck<NIހ?J$Hʃ	KWЫԖ[
ǵRNDCo7lF-=8}0qC=HE7rC4߸ 1lS
ι'>bX$FG#)֥nheĒ#(l<ffB#TpY1F3\Ky~cyyG'>i[vQm'ЎVyLӼUK8A=dHRrcL_BzsBC.	gֆbI$֝$)G,@)`GQiApG^>4fyZIX%zXfh$FpѭK3nbORsR4nVH8Ɔ%kBi@?I+ۉSY
 7#DM$b% ĪE",i1H*_H`< CR6R Lw2^M.${+y<P;$bPv	<HU\a?x{)ID.ēiS l`1vm~Z	|e#lOU(Kpɢ^ZyF0%( N*[KE:s} y?M2[%Y#QPi;RA$Uo+9ͬq]NӞ"֔63֒4Y;TnIUdPn9is@.H5	;[?vFCqTh8U]x05
r0z<ʬ+dg]׸co֒-;mrqm[7q?	ߌ}޸UA"V,$mxc""#δSŉ$&h𢖌q@Ev]`IzdȄ! sVU#"c.X2ۛ%A7q:<櫲lQԫ=E%9WQ=O^!bsaǵ1+Nh)"!d 3ڞ+QY<WqLEd18rL+Y7Qq ~hǯj#E(6*rhyYIbrM3恈84P{C#*`<}(l'KҎfSEw40M
6# zQڠ\.Y7K1p3Mr1U Ok5M,9_i?(=e𱴁~cT9o+kpd$`BßWӔb>"̱	_c@h֋itw .	$`uPBrW<S(@>)Dʜi${ъ1LA֌1@We!GB)db9vbI4Q,Qv(ڊ\Qi棔*-G(T F84RD84Pa?bE;18x{ӰNF9 
 65ѷIE;%y+xPAsR[LG#Ʋ*J8ocLڸ<)zͩKylԻ	 =Sgw9f$1IzI$;4qLDM&>\c+ƔCqN1	z[v|~{zbrS;d#UEqy5JҰh	a5̢(e!A@[19zzU䴟j lێI=s{TTQk җ⓭1fQ71*ECd'ʀEsCNծ4ZKus)F )W|SN׶?hY#E׵fgCƥAsV^{up>)jTؐ {Q T *ݍ\$E:dar*J(jr̷>c\cQw	9T,}ݚ)@ 21d`J3E_^ݢ!ʁ0*%ݒ9-ª6dtc#ׁqHM$vrYG0F˸=99XO6'3F!aڪKLyl-$Yt+AC4#ڪgq9~uw4NRH#}7r5yj@B
#{:P	=3S̿j24gYaźĈbKչ	UGmfvI8ʽm)a;'b<v*ŵM*Ŵh6S֚IF̑!{r{P!XNM.~C}zӰq)Q)8<~faSJAQ(1N'v5E {gV,<F֨ 5oHq}hlٞ5zu✬r)%`lVqJX=O&L6̒{#.6ZA;W\+m;B <zVu%
\}c^Y U9R>߭%`b=@8&`M1$QXS{hh@) j#UX܅2h$dWe)45b2p1;kjn>qh`jʓqٲ$	,(.c;8 PyT)vM139)RRRKIK@/j1Kΐ	KKhڀ_ILAGZ()h vPADml9@
`488ȨNTKQD⥦A~t /QG fRQC*?۔aЃ2ｋzE-  ǡJJ`/i8 ҩ\ˑZ8cҢqTc~$D# zN3җ!=hzzsN~T FF)1KZ-i zϭ z\R!4 bfɥ# M;9>J8@"sNqL4Buʗ 'KRҁJ oK~	0R$O+D-CORʩq?*P%nudM#gm$ӚTJ=9F<*V_¢۟ *Sy ~] >cKO;f;b J  ԧiaFmla/I[#׊Me_2G˞޲IRf#"rq۵DG@
LSLw@S[4\ p*? )1?}h❏I;ғ;RuҎ=
P i8h;Q-'M.)'\f+jES$ZF2ũsMA@ъ:J 1A? tL:( ~PGHMZ(4S[h`CՓ}(HR$|T>Rq֡"1,1a8Q֩gp;cʐI^PMKc41yjP %5ϭ9.z2M2GhȚ )8L
}ijhDBti-xSG|Zuk
H-e`QVl>cmr./?;frH3b8 RP0 ;})}
IKڊ&)>PRRP0EP'oz\Rb
Z1 f\]m'uf09n\ږ㧭% bY[a)iZS&K3 I4 4𤊙a1˲Ue tI}Ja3iQw<f2zsQ9S.ScaۚmOKtf
^Z ޻Ii3.nlS|Ą2z'&t
qM 歺Y=6l'2'C#Ԏ9Y[Y\o<KK>-㠨 9]3Yf4m8ܧ>՞ܓ4hǩܬS]%I@H5F1k{ˑ H;o2ƓB8]G;ҾЩQw0HV!$+xja@
>	_SQȹAc~r=2)VqU@wJ2L3v6!I, AlI*Z'z1REK`d0\UKN讼÷ۺ;9S<fqQpddU9)pM?(qh3E?nz
aw0\Z T[KԦi1m#RHGzT)- 6!@2Ejid]bFF1Y+Zb9X"v
Ұ$ p:VԦE j[KSUeLq3BP2ϥ/No'\kaq{}=\fG(y }4g;}c(&

]MS]$@`zwf["ً!=WTwo#\9$r1 S7+STrkC^xrp IHgKGVd.
! )j{G0T r8PGkwp؊> *ч¾ Ǖ0=,(eqI ]4<M(N1 IqRit{+Hǖ_^(/Ҧ6<=1I(=
2E4`"GDg ~Tg?9T
9=hvҕ#W  4mpUᕆ4o6FIK;Y&e\LF[TVF+*5%ǅukWDKh=	0aa@'rL{pq9gIZc&?,J1ߚ~֝oĞY]kʏk6!ҘP^xwUmkq	X>ƺ&|+xv0|bf`Cnfv$?=j%'nQ,79jL:
A+|?ƻ˘ ӷ471uN
`,mQGFyʗ2_Χ''>|nU.1Z^[i-"?.=Np:!hu99W)mukC:a2  ?kM_  .Ooq>T|A3DIfJHlHf	.r8?'N+Nqԍĕ3Tmk6J6̫5VjzƟfD(pz[oqu
ċy[&D-:Ex4/--OgOjoğA4UuΥf2\6UR]@<?rw:[,JP + B<P7
1{5,7:&(A>+姕ٲKO).7H 9L'=qI?ʗfU۞Cjq4|̭n$3w63QI-å^Tjv8+¶k4/g[/Y1
@?0۬[yDB[@wqKڹnSB&ݝsCZoOvHNzҴwH-bS̃NIgpO<؟^!bH8f5+oWqzh%G<O
d}i"@ .yLfhWO4n
迨Ymqa4EC,J##©m&~M7#Jw'o*B8q3;
쪠 9OP*4ak;<mpO5#2HN(.r\Jz hVipmX0Z#9R~ӊOiuuep.-ep@t88#"*զ-WF|r=
A' FHJ՛m:+`-̕D\&* _Jc=*Mػi0)H˨ǽ*,g,d$g#ceNoy!FOPI8!"ԁ)M9 Muesc*u(p)Ơ5<pwv qG&~""ہ&*}6y%C`ds59h=2:SXw>F	gK||)bٌno WҞj_ң5쐿з 3KN UK_2I+\0*JT^ ^˩4 " dB
H)6iZv|$ɻVq랔N&7ϹoB=&4H# sjH˚@,@HI7GmrEp$@@oϚ3˫hf8]#P)$j<sHa:=*kḼX-69XQ		󧥖=< 9Wmⵁn4*ەmR1ǹ	8 j{+3yp9p8j&7 7  IeHu Fв}"}yyt4
#'95{jWwzC*q'q3*I^-Spy/j{kA/O[6s\-cI Rtv\SC/Z	S5W5$4R3)*H%[ G"3Qi$w[,m$R=zbREi<Nꋹʌ!c' 6X%)7M2\d J %ph	<ӄM{O;NTMwu5彼/(c) G_ƪ<?4$ʙ_c;)L#6λrq^"7xڥTr:5'IN]FkB
&5o؊B
>ƭ.<G߸7{Pmٮ[bS9:dmtY/Aga*ͺIPc$Ls,uQ2$u|nlӜU>bGu>Mi*cJxޓHF Ӆ;?JC}.(YA~&<cړ=[V{jbih\uMDn\CUm2sVon4[-m4:2qUmpBβPG Au꺵ĲFShp1sիQIrtRW#dU_~y
Z}at'ꏮ(T?CN
Z+p0 05NGtF\,+
q=
"a[dREn96TPt@<̇(̧=@&v8HGjCV6m
Ny/⁭b7y赥
5Ym\)@r0}W&șiRzpJWm>ݭY0]mA)L35Qḑ[W-Z 
㊌m)3j63r)hlQxy(e;
Qiz	K/eigDX ?zHyF:oe 2Sw㰢Z3V;u^	ZI>SJ~jkf;qP3gZS&%I<&'O.ǖjզw|m"Bʋ"HPZV 
k]u h-W~ZxO_'eI^Pm-ċ0+ucj鵍3HGӾ+,̒U fk{KR.*H{7rԺJW{# m,{"UxӥEZb#"iOM{,;7n1ҋ^iarhɦ+mhO31܀Qֺx,FmHqW>k{#08'ڤ0_7nXyaCsK1wߓyno5I0uUO>֙c&.}ZݷnNLVV+h$zQ%5kK;
YXPd/!<'=Z=BbOѬ8R'~G^YIh%+.[-Uۨ5u%q eeY.6	$wlS;;_R'CYK#Ű }HV-5ؼ59?
EuyRd`]Okqrs	Ti.BA?zJ\j*hd^"D1t=N0>b-RFw2&'aEڪ:ۯYwMf̅QGE6mI$=4E?Kե,R,Zԃ:ьvyLĲj4cnF:z$:4ܰ*XTo9oZ1|39啌D$ffpHLx'QIF3i5ɑ%AvIg$Xgۂs.O[BJQEJ)EVF
m47VH|	eUGs4e-Q}g[w)bBzTB<Q0t:/
I(C8׏hsrmR!O6B|8ɮH<b	I&C!E9=tf:eF)3'W9r{VR	X}xkBaM3U+4$j	lZId߸*#i)=?"j;_5Bٴ-Ճ%x9)ۯǄƻ}XYP.~]F;0sz֪\ZN30(	s5ZsRm#*}0XduL5.7:H?P94=.{M<<
Y=N;כ_]z,$=W4`2FyPh'5jڟ"0.ijLeI{SZ	jk>iC ]
էxL
iwP{Y?_IcqF^ǷJnRU.P"@^Bz}*tk(Si #FFIaE5kh%g Y68Fʗ5irҏ4̦_Z+"!"	+M\T\]VM!`u^"+ˁ42BUQf
;9ۓun0d^w6E%.h' qzTG-k
uJd_O,0'zTvbJb˱)m^ qX![ɾï@P R{dhxPFo6kCY5ʬz|uZw
 ;CO v\ͽWRIo|J78=+2Zi.7
/¶8QzEHρ㞀l<ssoޏ$]	'b+{Dxհ͎X([Mi_,27yfhe(t5Ήixlq}5]C֒^xOy$<4m<:YWS'd;^xڙ-'`\(2C` O?)SW˕urh 
ԧXm$LSdׅ$bkwv<?Y1{Jhqӭ?HKRiPÜsjYuc:e}>\h?Uu,FXg)b\0: *n_֭oE-V=y#5&Fm)U5*VkC.Y[FsvEp9	ۜUVHfֻƋ`nF&r9t:P1Eb$XRx\Rm]IH}OJ%
®:{⻳aY:}\*$FkY+\V:OΫF$z[\iNV*!9T~4mzqe\oZJ:yUݲ3]ǀAh<d<#ӌ$Y2d=Az\>u+Pu>\dS֤Gp. {i.#a*T$|GIaI),E֌T[zRl p
T&@XnyE;i=Ob=J68>8>]ҥd#4ҧҋ}(.
6Mҍ@
jv=Z ܜ~t)OH 
b
sMIZ \Kj6ژXOIN}(2UHـ$.qLhr ҺDS0)47&&A !&IPA 'zLK1 OH2`}A`у@D͔g}ýZ-
HnnbҽlxҰn>8]MV:1KyJ/`Q ֏ĳz	V)hIO4hsLVo;2l Uphl{TdҐi1L	CQ?:P\Ƽi2jQ&Q@H5k?"[&sI
AR޴Y՘\?C7ɫ<q{Vh3aƶ4+De]&ұ*){C	6GUKIo*9Lqǭ2{g1MWRyƶF+ZKr^Z֦5	/5Yn9sVp9=l\#14ޕ,Asooqk5.rJ촻Fc
-,Km^MU1H'Wc	v
A#rp:'+mEzҍ3>DU*:e^Ӗ_JM&Rr["Wn}13cv'(<#d`#ӃYʜYjor}@
DnVPC9r~5hڳU  AEDPe8$S~~'\/*eEf^F)x5q̧Tn9>zd{ՙ=ydU3:#(@Ɂ ֔`8)#
ǀ
ijWMg:mGb`Ya|P3F۔:G4(- nj[y(g$P{je+'>ޜRފOʠ v(j30M0#{}(b@}it2~#m-QobbZn{[W؞tXmx!rnWx;OKIƷo.-gɭ_ss%vݮ$ÓV9Ċ"uPV6>py	Pv`OTv+6_$6R-b2m'35Gl!XA+M89#zl07=#x=isNSvLN4ʬ F%vkĀv``:ʒ[(ȗRI2 uQaw{3#;L6GY{ڲЂQcq =V֯H!c)9lg!f70.co }GЏuZp%=% 0Tܬz{ESC۹⹴3=y$`zvC֓o;^Ehqqc8kIn7K$~wKշ`qMI=coWt\
23H5̛Uf :Xt]ԦF8 tckg>7xSiϖM73u[9-Z[:~^VQ3( s֝/{wF9 9sZhKE.`GM* W>Prϩ?.?Y EOpn%v\zp"ו˭Z]=Vy[z|zG?-dq-P5lgӊvX9<]\ZO Tet@AZ~5G79UiǙo(7DĎ"RBX*=uj.-/h#l1B4}N%y|&Hр|sm][pIhN !<BÍLw,SJJ%XZ݈
#aCz1$֛y!9\` %GN)_PiEYg
j'2G0+v)4I/cMbdq޸#`|J*RS{tvZ6,"{+1SAs5uDٴ@S\񔓒sH$o}iS B:GP:O;MM]I,' `/qVSSt%jėLk*ysգ_tXt=8f<£f,zR96xBk2A^픟2	6x"\3+xCTWt(挐q׏j&Mpد$=*3 Z/;/*10q[s;Sv܃츊hu1LL9#]NIy÷'z>iw SUtWY%jwCcU
GNѤk96CqmM$mfxIm1lVmd*?Q]4lIn7e psu+E I6cP&V*)-0ٷ`sJO&6o6Jഞï5 8+;dPKpx U=;aƫLs3Xmm+=+ GIeVC' t+:&zb>t~D_vTuoۑ!ֲmmut׉Fg~F:t:]gVЈefV 1HZ5K{}_T*HwgRhˤ;rvY]&6M3["(#UU9 5yJwvNsS[	Ve 1;uVkIgRYuC9hRNo8Ȯ0FHHnI5bVQ|/y@G$[=UNz.9[p!qWSzƝۄey1	,~^?nnVuٍx@Z&1"PIR
޵PJ1*TcXڬWө>tl둏Zeo\T8F) =}ǭiy<LV_#l/j Q )y.@-YV#؂H|
lj+hirDJ7;o~@T\［n^[dQW<F1Oj	a-%RLwKTTg>VmŹKB*(b<" ֡a;  ZJY-װ11 xUcnwC ~4.َӬޡlr<3=N4gFyAHV熴cym䃞p}+0o;Sn6$T6IZ@n;ATjk	VM_vfAR}X4.|?yNxҠmF;
PFV۸7##քQ݌ a*#5_QH!"20?{ELC=;~7Osi3;tݽNFw^=*%I6J˺.={Tzè5Á, ֝``FrI" gzI-mHp1uRMp9Mj0HK-BA.EiYdU
##rr_S/`۷uķQv{XV%x܅b'ski份#`qWMo..ZhKiլnjC4'rAND6#Xc徚G8}G'{Ӕ`!AѤ7ױ:p"I:p1ޫ߆)
\i6 PҘ@}K$qڥ\.0>6H#~F<ҋvrb,ټN-E
O'=k:VkK?9v4BSVIm'횤g4
$,Ȋt6ǩj:{by# ~u@G">[xYL  *`p*ۛP5mZ~y)PROU*?wGG\"pvY'؟J=f3AOEgYQq :⠴f2>	+ӭ'MU
=bsqX3YFb7fSKfF{Qx9΋SF$P*j>rЊ"[?MA;%
2@_=꠴?:ҙӚا*eRe}C]]b/!X=Tz qkm5djn@=	^JRM5VNXsk%g̃<`{:֥$mXѿ
pXaBqTN]CG'|݂9+P6v
AFv\y~omG\_֞.mPyOLuW6H=k9b8Ƴgʷv~@hdKo\ܤkֺo쨀 2XZ=ZkS:)^B*,G\8H$e1γòvm.K;Q4dn
Lި-;fҚFX)'K}Gh.Q^ˣ[@aP&wڭE-Xqߚ#?9n?ѬMѷ+Fs DBE#Bx?#Rw 4485]H]ӗAn|'{kEe6:֪rM1}͌H*znC*!_	<P7LsRPeLA<7[c1hcEt0|(!'>նmđªxaR]gwRW0lT85_ǥl=l4scӓT2;FkR]$)V5ck櫝Ȋ d]4/*!0]{TV{Imtp<
tR.Tc}>y#Γ>y$J?di7,Z7HʄkW-uB壆vAE'9tN&VjEt!lb
2yrO?N*b<댏) Rm(E+iQ68?IUr9p](jEAꡚ3K3MozԋŌVF3Iҋ)V6 1њ5T=a,@֝8H%l2vg>"<y }SO.5)wcafsEkq6/.uVsXgjڏ5O٥'ڷ/\Gqmw%ъT63[ }w;}==(7?>F^Kiai1>.$thΓjyAE٧Nk#͐4ܚ==V:HM*Y=i7sɦ&}X 6SasM#ҫѸ>1>r-4gv%@E獧9>D*DM'#sNmkii\dR)"7\CHAq	N{wh=:Q&O@*qq\j	ȷeY7He`u5]Fyҁ;w5nv<dRM1XȣT7t
v3@Xi۩#M>wN{ĎG&3ܔX@wI*Xvv.0i_ɵrj֏rM0H܅V
@ORyP_&Yp2<:{;X"9bV|drxuQ7-eqOoCǭfèd0<m?<zeؚi>ζojXea꧂?#ZB_YRNǃ[oji0N@;R.1j{hQG{M!-Kd̹| 
RX!=	Ҧ\K*z߆)	iKBj, /,a#E8%HajnKO._ u{Kdo.8a !a횥ezȄp	 <J>7et'dTcjg A>,-=*SstGc~<_gC|æ:ݓv;3i~KWnrԯ"Io)F  *ƔҝJkh/=#`s4H1G">[g #.dx%ɜ:XuI.rzsbOLdVnM^Z	NA=3QC׋g\GV7[DH		b300:լ\ө,%6?ҫ[Yp3s.]@zi;'ҸA*|S?<Z9^læ	lS!,_~H@1UీEr
BHF	~X-dXHrHOMͤUIFL6dEEr7}K:DW7olb0~^ ~+Ѿoqco.8F3
Mp^J`p! # hPmӨeR)OWxi.y38'\c=\iyl
<)n$$@#t aE0 m= AڵO%{Kq3I¬7 %Ē.W3^< 0$<
[y-GPFOQ5X\~	/' s&'Ylh9u;`k^<Aya!;y*N:ӝU]^*9}Lfh&ecL־a'٢&?JKdh<H#k?HKdKkIq$E%{\?Qdo~$Xm5[-T[~9{U
]0vE҆ tQPó m)o~b|k#ߏDe\que\kT{;/~U?KˣtTۿr~&^.nz(`ӌ`qcYw6VN6d៏L[wZ҃7mAXY{ugiod6bX H_RR_-EedՂTgެG"dƛ(V֓;N3e9| O?Sf]`!2p	?Iv/s}lg`(mF?agn)Jw~pxr+#<ֆ0l'0z3.aU'B=94I-DFk!]#$lCkEp#qѭˏیtォ\bLx'}ϧOy XY6sww.m1pxCV)QiMckj!Sy9V0.pjvLUN}EO:ȬMiCͪ[*
o_<zVRɴcҕ4-&	RU.tVrU;(>~mr6YDAvf3}	C"4V$j#$>jmKIG9~YzJ媓n7sZ
(k]#QbXo0qdxMHuV3];b>K{>sQK7RO~Wo|uIAÒg>0NkeYas	j-'<!NrM]kY g|W3:cbc<\H8b3wjs)1}DWX3y.sF?DN詺K'.mؾE}鯠O2W|тȤMQy#rB]cK<AX3N|aaYI8{W;yyBCK$q
d$zdU{6)hHYO]qMYrX<@V=?.?*&m2-Ldƛ:5UiQ#\e_%C;Wz8hVIvqng
	S9:<3in)q `'BTQ+"_ǧOJdWb\8 T8X)l[ʲ\;29s)Z+]=wFf.?T+qb$Al^:UbQM)#,lW  Ԑiq6w mpy[QWf
mH']ȼ,gwӚynɗ #OJ)#!H0j)\8?ҚԫdX	e}໿ V-UaqLҰBxNdaV4!2$3cpZ$m!i xYT_ՂMȡ}nrl#  Sec <Z}[՞	6玅H3)#͍{L֖K	pN
2gF1"N2*{Zp~)Ϯ:ˏmc=28UwQ\/RHOȬ2 W|3`;28 b܏"y--Ub8$dv5UhrrMFvD~S5FK-"FkIcƥj
nI~]}>hdrF<pRkW)^i2^IPG,OteaVH #O?OnQ^yV;|olg֎,X>etq;~O[xg[D#-i,(ru}]iu9SթԉSWD#ZڥޣwKh a
*
r֫I«,@5"Ν?ZRRxIgP`|/!2<lrst]94lZxHl#@U=VkS3P$"W1y%`01ABcޘ{Jsw<
r.ڀ$qK)s@\~iD5z><Ӛ_=Ȩ{Jû$37kz]h.<Ê_5ME &Ɓ3?CFh3'stgT4Qd̛|IC:(3&C xLu f7J:لY՘;ПZfu8ɦQދ H&SKV(|ߏl-Es2C; xyj*NYyGi
+ drORO&frh.تjem sOSޚ`		:Οi6yј 9ŉ&KLP:Zͨp!!i##db9"Zw)7ӭInd}H늵ZY][+GQ,NhĥcQ@ZpM4gր/i*v1ǼxUtg%PzP+i9@J:Q_ƀI:Qj BqW\Rx"`p3DN)P4M	 %I>ߊkLSt\v&
M8R}y>􇃞Ƨ03@'N)qXW+875,
Eh:R恒G!ÃuLiѤ0Qy̧$tZ;Vu!AG*篧g5qܪF1Sqt&3?YO2Id7bO'ҙoXGs?/bFo	dCm$ U[X	XiqCɒ9GZw1Arc94LNXp:U{[9>AR[]_1Kh$W }OjC	$Eʔpq>j?҃ ITfͷ9-$(I2q[ZtV1%f|ȔہN1֢m$ȋI I~Ybc PZx=::Yk@lߎ9#$R}4fFAc'HtZSQF xE2p5
ztYG#Fq\ݠ2v9%JR6ƴ5żMpMz&IF )g<Nޔ`r	x68=2 ϧzlRu2?{_NGs2hego39<t<ժ]XR	]zT$3/רȔ_|20~"%G~j^)5-#xOQU4ۛ$w.#Ui'G \,=S 2G=1ޥ;Homh%;8#~+rqpIYs#M٧ԡ[xL~'jc.#@N<VڇaE2</u<V-7Q^[=bW9tҽMAC9>Bw0w#Q]`m;o ؎3V U:-݀~d?S:ַEJk,=}T[n-#̌7ppޭ6+%|}WGA@HY3E	Ob[H~If<;|Եcz/YOi.^I[BO9=)NQ&E -[轾;j	ı<7ҭ]$2y$nĪX68BX$kCF}ϽP'Iq4D[#,Ы
>߅v6&]2ĭL"2J A;xQx>ukLr[qM h}4
~u@[3-3s\L{= QF :2W}ih kUx~dBlw'\a(+9s
]	%7yUdҨSGJx=)u4{ki7nT;|@~I{8 VO[76%t\^STej.eHyp=kA}Ǟ7~RF/:ѺW'?#Olo ²,@dyH^	Cc51J4T[ٞv.<-a:H=Z[A7qߜE_
>n,LfU
psqڼ՟$Hgfz,:ѥ)th|7sq k' c/sZ{F.ʒHE4 ;W5<{pmܹ̃>*iwrMo;3ΡlDl㷽G4[(-DIS`u?uGnog*}OF^bLy8zV=f<c'jjr.ϕ`NCQt9Ci44 =jDvaӮc%u]+`@RSֺH+S,aL#c(cqUXkW|&(
KnsaýhJ˶NtV3nDѭgK,!q	YZdVrJ^Qe@QoJm@\[CH{9#Ӯml rg=hEF)!%cR]F8mmhFDnxT_1
\e1QA *	&gxTh{qk>-g+0۟=1_:;ZNB."[C&&ѻ=^wr*3_n⥖x$]	QoRՖM$ȚR g*S M,H~w.=Pr^Žn.S*o*`Fxc?jg&:B8v GVWVyf`G)_#zzbOMS5,OYHofm[s!ar:ՁJH	_#ߑ۵v0Z]i1T$g@8O\/q'mV7s[(Z|8nAXv< umgrݗ'^S\NڳWZ$RXI#aNT4y(&\_HV2azw),\Db{֢xn6 U8`9I مvlt&ެд
ƒB6Ys1vNδe$ے2cy	 8GYqREߎnA}j5td.ٴDѶ>V)*}p4
V T;,rOªXj6&І3g
ܯYGnrL| 
O;\R{h`M8$ }RzWSfz0GRޥ!uao<y" 0pCYW6%m`Fp:Ωr-*}*e8306*#:aetr1 zUcu2nS21;A=kMHāe.HNqL#DBRCVoX $NNҔ"E1ֲ vC"ԧ㙃#d)o<W<unL6ئ${QRZ%ZFy8)ZMKryʃ#O>Mt#=g^F͉4gXGMDhgciY8# Y쒪E$y].^U9#Vf+E;ZW1	hLC(Ļ Ju?ίf>IZ6U\grKr[0BD#lf9l挐1@X~wS㰨bpENpBb)PS4mޒauqo-VQcuBBH]o;4OEJҧ{I>v^IkE<"f6FCR
7 RhwR$l 	&T0hQ\R~)){~ RZLPc٧*qɤ1{RHy491=G~(Tl <TѰ#&:)
%-i)bH''ޛK@Ւ2br
 zS>	j6.u|NIdhNz)7`nji0X*35jܬQ[؃=gb4=鴅=*a=SKԊ &hX3M.Ǿ>l >ǁtjڥZ|ŝ*
@ҭ`uer!pqƥ 9a%Km_;HGzw]:T?F#5F aJƁ^q
k}A6|t,YvTIE
\I؎aϯZ3ZpvQv*)$ARA: ]=ye]w>m$v;F9lbT)|,d_z{vg,  E*2[8Zh+9	 7Ԟ#J0Z{GcR"wry<jM6n6YmbGZ+J=q8ǟʩY[[ǭk!
lgU}5{lQI ji澺QX- ?:{gH$l2G'Ӂӥsŉ,ŉ<4.mWI-ȱ'#J'cHѻi-[Գ0qd+=)#臚"yQd'HcàNVP1֐ƒ  vjMxSoOO7w8M PG<zܓ@VM _lJ<{ϽK}modWq:#ϗʾWO_+Kl*0:jrވİ][Or#[i~ֽ֓kkm5+
y׌)csXh Ջij{OXo\W5J.U.cQfd(E,jBCpOj5'YI!|=!MĩE]9
3Jιo$b=cZICdZQQR[q*cL`*HnqʌpwTv;o 5H^xTDyJv'ҦViG Xm~I `&,TQ] U 0Rp;jCn0sbmEi[4vYw4F8(w]*?ƤnTdpj)<: aKmP	(ؗ'#&8ʐE+csRE,xc6S@5GNE LH"O=(,?Jb*`洍ݎ]-3ގ=^=k$0١4^WqD?u(c$バ3|R>c޵yodb2KmSom6ՕH=kx:zZMl(8*z1ֹby|K9Mw(v|8(Z*]?
ha(uY@\]*/"z]t'qX5tWk(
ֳ:5	5*~ݎO\ AYH8	(\\-*E|WIhR)K럒wnFFa<2Ԥ5si aQzS9i7sM
֎ nzSX屎z
r0G\%S=1ChHcVͶwhsvʱ5zVb֡cfB;jdյ.7&O!,1jI4s`@+/1M~yO>l#&F@3ܜްjrvHP[9乌oy5kc	[pU3u<8湒v cZQecfG-#tduV@} O.ͤI2PHMdcpxA	1M0q±I6M4ζYD|e%c#dYMo\ '˸L²lnU|܎MvEwGV!qG"0QZ@KF夅Z\S?qPmiQi9bzgoCCI^S S _9 t~>eBma·pR&"9JU(J#X$`OB ~t+y 1@V
̢4	hPϡ45؇q=[SٶJ-U>'-՚n`!O- t^?MAԅ:;p\TLe⠷횼qU~NIE\ĒY:|i#Guߵ=.X]Mߓ[JHGb,n&#A 7%vٕqM4
p"geA{0IVHL[`$m?ZJI$2ª"Y*<눷ljnf<g&%ya-98=?L~u#ʬo[6B}ϒv}z!斓1jՈS),qUjXS@#ff>ִ:ӦA"
rBndx"=+)RݚƢȂS4ǀ;SUzJbı`{֨2E"Cp>xsR|x4-_R[O?8IW8aYVp
+)%dTǙ/xңw%$T??2"RC$gfe'xƯ[C)":ԈRƝOҮ-5vbhG+:ҳL  Sѿk8iJilNHԑE=M&t56Vpnn__\vCPh pOqk#/b>y)Sm汚J-`H.Ew0eޡG5H3c94z;Yu{J:ӑpڠ"l䷕q_N!Z@ ٪H<H4l9.M5,poִI(`8nj`j+Zx}}F;Fyb9Q*Sǡ:ͽ,vX*yvא?
̧ԨKV霊ޤ2ucQ5
"ʒ=҃QրQJOj "ڜ ~t0i g@ppzR`)EFҤ$Z;ތPF(@QIJN:΁>J1#vX95	$ؐOAi$$'҄cqZ5iB֑rc5PO Z\x¤W'NL.MeuDkS5Hm+csIZVȼCAbvRCl z$rY+9%Ny5\7PZ9 dTT+c%1SOMS!ri5UvX⣑C@fuʤSZdg1>סT:6}juU0A&
6Wqk3C:}FgNI؞IMk<fOiipu Rv@ED)
F2KA޵,8cR9Lp? Ub-krW8`[`}I=랬]K|ii a5vC$W"&8zMn[	Ǘ3"k5DB(j=lX^]^ߨ		Mt}j%mielOw2GRJ3#
Km;-TJ{ (>TCNk"ܼRG	%I,|g~73[FQ9޺!gNW#'$$`ī0QgArzǊmefrNED )Ϡ~ְ0>n
Ha&}axAa_i#u4oQ"1GELO/αQ95sЗqs5%&XSֵ	a1)8	ϿZ<#&h+wQn>]<Ȼ`u{{JpN̸Ƥ6KbKIM2d8R24r4L9^T.9Z4''0('C`:<֚xb:&c>)*rGQǝ~8J o	%d2#Um=A.3SPqx&1#8
*&EyuRB=kCNG)c
)ߍ5вݸsQ7cP<Lf3wzmܔiIGf͐X =ivnCc%)s!&əPPjP=7zSH!
rh3Kނ9	(7MƝ厞 4nFSZ n4p#/_Z	HpG?Lҕ"}FNI4v="yNBvޙ X'	aybDF
fޕ7WЀ㧭=m4*=lP(\6?8{4ݫ`5ؚ<9Dogzc#D?~(952WVeE[|Mlӥ=|>8O:6oğ.GzW2Xstj^U\cFwFظJUS
-Km2#mp֪ċnĪF8U.Ӳ1 u'&!p%	z[(H'I@@qOJTl3oc'
|؁睼fMߺÑM{)1==ꬉ,F_7_ά%M^ryEvl܅~s}
=Y/o~ק`Pup2e;HC/#4O,ğS5u8f=|؆O ש0_݈h }hwCsG?yA\*	V 1#9,:zUݞG,I;;8N$l{j&4Cod zaw`Wi`!ޤSҫj<*"M3A
~ZBDg%{RMcvlMu,rCw
d|y".)1'
 =5sђtY9֥n_0׭Da(/deMȌV A\ZشI;YRrjZܕn-`?W34$ L>Ra̐0)*̂(J0{sUF3ӽXYQC
3کŏcU$hr/ zT(sU?>
HIr{<G pMr0E+ jUBsjzTixfcJWRdf[VӢLCRx/UӗPkw#Ց >ԭU\a9_|}WU𽖟Yj2z^]*)!3)Xvyp>{yYFA(r+e4L~Tl˜+4U*rn(Ԋpr
UY L+tn})44Ίlw2g`~R}qXHI$5ib0Qط6-FIR!i3S7
&i7m&iR 0ʹf'iۛ=G&R ;Ӏ@ (E4}Z8sE7N@ý4*Ja4
xS#dcҠ<sOSE	j#'4ɱ1 ux
/~aF=M8FǷOXh*pF=:()xt!@K<*oz_@nZL撖Gj
 Fh 瞴fGJ vLC1U0$>5]n$WK#2!;QG@-% sKLOJ)- =^9MNRb3mB
@<{W	4$6nGΣ`>Xiv*2kao#vA<楙t1RMhZ3ӵ6[Oq/u3S}mnf-BX.,rminRޥMs3̓;Iwgj̮:Egyc{I
ԊJS5sQ \O.jשii8NMmt6B|sާ0!n=[Z,Cqt͆.>Z` ֔dZ0TӇ# S`d(F}<@H)`cǊVn:_kGqk9
S &4(s⩕^{TѬ*Ozʥ(ͩT GOL񬌇\֤Ef'';H{s
כ>He П^:UAuc(ɩnV,x8|SrwOZ{f'(99W'KZ{ۯ[ajg5b쌭7N:w^(Ҽ'i
K!WqxE <pqޢeV<}N!I]ږFw=["џzaa!qLDïZxea[lJkGBv4:rk>{O@֩dT4d`HqM)#ooSQ挚 ;z;<1XL<Ӆ*3@~?*kJIAFh/H?*A!<H,Koʏ4I >3PFhWrt 9XڭG<d	4Az.fVWn:
gr ښOGژXx4ffڀ$3O89-7+*[g1Hlrk]*P;sYNJ;SwY"觮;Ժ=![rؐHA}aÑYy* YNs\ukFV #)Z>]M:$hwT}jߺw[^}7K.WO#:
F{z% `gtQ*hg^)'Rcn[fRp=S
nr3j&mԎ *=h "9-ӊn@<zSD$Wa})yF*q9K֐io%PۃZ%PHHlInc?Ҕh~cSkcFDRy  Vg2}j2A (Amf|I<\: ;pP^@@V͜ed챜{VD^=,EHTz
vpzQIҘsYoh?v]#13XܱM6%60>R sE%!RN)Cc֎i8t' =WSNA SÓqrq.}t:ՕaCC5bJlo fO8I$ijOI|NcJr7Dxvq8hlUrh݁sR5&CIpޡjKȓG'ʸuid$=jОr(pT- r ?MW7,㖦sV$\s⏳26{
or3N_zXW!k%nToH(VҺO.u !yl94hhԏ[_Ω0p6cV
"ю*E??*G#^4[+>]iUzPfY-<Hހ$ ;U|ޟ+V'Z}(w4P0)h'WaMPI5( 6DcM$TT
Boz)\cGqJFE ߝ1Oj֚ :(KLBQKMFi)q@RJF9@	KA4 Pi@3LiwҢiRXfԀ*&5rsE4ɦH%/I@RQKE  Jm- :~4*rֺ2JzRCWV`v(Ftk<];.'(>=̳0- x.;,kb
""4
qONkBw$Ite8"-@P\xIn< )=
"|ր$JwJ@4 cJ'<&=!1z|Nv=E$zۚb,c"\	^9b;`zSQq
9I ^ Λ$PiŘ'֛>*ZC$Hq'I<TTnj&liڐch|k1⒌>)^wj lp5BN&6VOց	ރH:uv(٤ҌfʀZfir}hsRy2i4 Lf<)3E4fQH%!ҚzԈ֣~3Fi3Fi Q@OSGޜ(U8<E^7 b}MgL3A;>BG~a}zMMb816z]c9>Z~-$++I=>+ݒ:KW
s
sw*o]2+Z+$WRCq@b{t6[0' EB-QWUz	MB5s~Udj)SWJ%aAlAQzR9.+RHG P3ڥF#@
Q4*w?Pc@WRu'#(?ƅw1_tmao\ηwY?1&ssӌa^זd;[cUZvw/goҵ?UBlTɵOzN=Sc:k6̝n;)){RSSO)4'j?JZLq@sEhP!zQJ(zvNܜMYNګʒXGI]8VV'=yV448)܌z28KE_fGCV~qPgOm]@<YU.Gr'<w%2퍻}y4$yRԒjN?>r=k>Y_R
gRx;PC搎0EXL.R5y[ ƁOlT-_?XR3iТA^UZR})ȕ~bCwOoBbn1Rｋ|&R 8N804-0cSsa@E#权EZ)=LGniX.WۊPJˑ֢}B1NQNV(#itReH Zi
ZJ^){K@sF)>(hE1Ea@ UvNE׭I[.>S1E!t/GzZ J;R'v4T >[h<:@zb3MEv=讦.0M?i'K5al;LJodC8\sK/fLݷZ'`=?R?,ʭa&c&q&F-7a	MۿhcKh-\Ӛ[)<?krtN]vt04) kn|Ljw%"nr #=jtiNoMz #LO[Q O5%`eiO%s	IT@>+i78ߖkڲvq
a9:uPS_ߣ^*  eTcSE_"3T64>	WO|R$pB㚚_mRgRgxwCp_MО
7p#X`/9`~5"j:+䴺so >v`G`7B?:pL$
A'f67s9_\MX Ǧ)TR˳ y@nO=zX,0Qg#(5ᛛU3Z`=W#<kXSJᲭq$ST@xEU#߂ h	 NnR
GOAJ3VP)^#W%F~cUQ&yhCFfQ-Qr\/jz,4=g9cM玴9~[n<Iڀ
*xN}Q*k@haRQ@KJ(ќRRGҐ{4)yFi(~4f4t4 w4Ҍ .
	zBh1
?ZCE -%4 吨uPi(  ;QEi9$F9 d }iIym%vv3f!E*è4o,Kbqbxn^OQV~Vҳ)UX<v^*WVp{OIU=19h&y]Fe^[#4oٺk+cC{)<=:XdSAM9 /^i r7@p'm# S\Qqd}hyޭEƳ~||S^>-5ĘkXʔl^m-QIYj?w	
~샕ok?k_xru'!G6"de^	)we49p4֏´3֐)Rq@
4I0n*]W׵ 3Ni
<)1@
sF(I~(qfQ~Qh:3E g"Yzj3E ,>/T
rHN)V.z,i.g 8MdJа\I <lU({h-r,HH
ڔJdigcOz`v0@T$?ZTd?';:3JIbe:T/D<q<;ԢeY\'9jyV>e<KkN%{P0kdI=JX&$nE0vϵ5*`G#֠'bI&995%!@֔ҨҝX `cjCJH:^@CKUJx4"J^bS*7\Z6Az2O@9R3L##Hý 0qSJ<Ceh/lqT@cu^J'P;2 8u$撋ĎÖ2%-P IR(٘ uL~lH:;xu{	9p	TY\\n1C#U' u&
@MJ܄b<:ĈmOv*8k2fnQ-۷z4	n&bW	:px#EwVqeޠ H	OztaJ&q4Ǆ|b|g}{
یZnIg㧨&],«9%y6 w5$7zsG7dtċA{$J9_gBusfizM 7cSS4qXkX3qY
J}#Lu`D :ڴ-<)KbHC̪N?	RRAR ^ڔǇy(U-jd0Y)P>VzC/nּGYOG۽l5|֮jUe-"?g˹
N#R5 V&L |5kWDȕ om"z[?]Xӏ_ʷ [)?܌ӏ:sX<K+fWMĻQs"Rz'?(wE~B	<CڎoWKkM^Xm/lȤ8[/1>4|l.*YR1k.:ҌԮͭ}*7o/t{Bzu&hy"#H#U.꫓-NFxSȇc,M8?ij,[ǒwi Ukac?IWkOIhRPB8`9r	H8к2q8Q-י<0tAly\j`F
)#K2UDlXv*,j Z9v-Am/0m,(TG/>ZH EKmtwjNHҩRܕ8apwHt9*jȰ4@vZ\ȍ ow[MA$,%Ao?_iiRܩMZM!VuST<`j>Ǚ3y#cx_
GoOa+Nv#`I~SSpٚ8F{! ;XCIuF}23h7am"ļm
:j
qvnIU`C4|mhdO$s
444( Pi(Ͻ%}h
(
(J ⛚2ME'j(}isIE0nh4 Rfڀ<!zRN sL@Hh<aE w(  SAIފ i
 ~_4⒎(c6(iihIK@SG3(*/2hTF 8q}34i#"I[V^oFe;?N'%-*MݞMw#y+^MLPm-?xK;ucj>hOc5Xxvܢ|o_ݔʂ#ہU^Gwڠ5'T
h%yq+_XbNx>gcHx¶GN \5ĖF!N3
襷eQt65ϥ֬r	^qdO hX)K˜R)
ɠJWl^1wM7:B .p	
Sң? 9%d]ꨶR&ۑduP_aaU.JOlF4q'r\eı.-aYdf#19	q]~Ϡ31? qS^-g%q\ijL61G2#kMx$1U=+V9n	4.܅U'56cUR\ZΣ*jȊCg R|->gO ۽Ԋ8MƣC q^DOř$`A5FW9NJ e]˷MքNO6A"o~}ܩm|[Pmq0?\c]K7y/#H^	cN1[^-]3^i٣ͯ)頛2TBG+!tl:>ĺZ<Z\l'|W
qUyEgz4մHsY3h<OCXHragȪ1o	:G=B3Mt4U5Hzvw<IiW'?z@լ	Z}^CE4fn1HE<}hۚ~T0hPz)A*r%*0ȩ@5WJ),\+/|eVqX<Rgߊ;P{Sf֒@jmׁN~5	-xӀ@lP1E-1~QLB֤QOSKeARؤS`}	B;fSQ@\1֔}(ӂ"q0rGZrʢWT_\t@tbp)Tx:R2V;[v:Zx9㜞$N֊@pqRHiM49cdR)PES JQ$[Zg5Udߐmiq7cOUf ($g5tW׵DV<1pX\:]l]|9O^Hғ1h\/ ( !V}kS3IȵUxMoq$T/4ͨ% ]vPֵ(2udCvZR=&|q79 ?SXھ6nO?]XUH˞_J$M!ՓA֩[a-u-ZD4gSʮtV?gI/nTTnZoIӥ\{{I>M	>k7GMGQ5܏nzMk7&
J ,_J$Ec3ol{
v	A 1~x^5m/g̖XT+Yq*KU*
ܽծ,<4b$
Drg;ǥrsڳ<XStS9]KuƟ,	sln=Ѥ7ey<W"I	#N?JkZ]E3SRTG1О_CYV<qQRغqѲE5[
mÁBNzʯ
˸dnQ?&`R"ՎRH1Ҙċ֪ă"
@YsT{TV䉢<#%r䈕g9KMN07WQ-,)ʠ95$:&pg)P2IJ=	Jd
<O2*ΣC#..2@U×DnHa˷;'NjH? *V{}r)5E(Cg o?k?[Ĵ1 sנ}IlJ]içʒؕ^oMla׾T3yN C]:E}	޸Cn Sf*8L%aeǮ=Ω>VvILo|3@~Or[41v8,T<pz	E1B_+ps铎1J9bJ i+
٪^Mj$
hfvۚ&Rpq{n`_N{_pF/Zi5Gʰn$ra5M&D` ${-/v%+]	nO5՚ fP+G1g/k!$t'E-$wtq-AOQ曡JE%guRNʼGaJ'Utp UT^O5RWY$ pG̿j{WINضof^Hee#kV
jo+gi}r|{;mɌ(ݿ'8~ګDh$2<WY&~c`|p':=}\qbpNI&IR ;WJ9j/ZJp
FtթA'z\Q(@ :z( t@J QFx`- )h (^Q@z(0hE(R gQ@h4v NhIG@3Iޖj3Fh(&ihht P;E{yg5sx+fP;W[bE!UO͏ұ&+^\ڀ:|P6_SkB֞oI|]@3\#\ZFz"
_'i$-V2@wEpP>M,|Q0<rT^Wd	= #@w\A~р 5J)N7!QVi	1p Ed[SAc,O-ӧ]`I$E̾N#\SU@~wvܛt-; ~x]0G{{n P@C#$zT!N[B['=K&y_0?%6mob uC'<a]+Hsޖ_6>bL>Ʋ#ܯ_.|\獅`E_3c.?^:h^Hf0vc+p2.+wkSa5V]nZrꎀqo䚦|):ndbt'ƣ)DFk(wc
5Z{
ᦕJ̹ qI 	 ?TKeg+/T[0{ *O#6`tS]?2Vo9|KXͲEuy_HO~R;twlϘs"Tli"89m0=*D:rC[Ry$ީn#3۠WյԴh Tc0
ak;@{'f
` %y
v"&qb6d#&r_P+;T@F]I06#喃n1k#V\oq/LY@
ډ,SGd(T( 5c{
O7Q0&܏N=Bseum>1b^kBj
pw Z G,wierŞ6]Hӊ0-n`֪U{r![Ȣgsap?dӟN𞣰><$3ِq'cYċ3n;9uMTk{ybٛe-mݹGk
GnϷrR<V/!u7*OpJ̽ѵ=??lzZ:hf4E/3< sZϺǂ/bv37@$5$BsXSN񔬓T|߯Z(YtK3Fd5&9E`j4ig?&K I#kpiTrRk?\ա:!L|s}^0Mݿu6*^ 3ISZ@UxkHA(D;>s%MyEoj^'!$C?a0*aL4Q֊ J(;/CRi(2i\AnOZw}i Ir}UԄf'hW~۽zT) R4O'bi3%2U+sV
 Sqq<sRPȠ  өɧib9jaby@
 Mݺ
h*9L<zT3TDyq{0'3!9RQ-Wgɴ?hWBH>~QnȖsvZ`HPv_]im@]bN3dUw+n
pcyTL%]0e X֪K]}]F%o]3Lk388忕UFRQtOU/Y.f$
ohF=	 뚞hzU   N:>VXRsuyaO?iiŻ	eܨ 5]WS$`}
^AozbE!{NZdZ0,	,Y}1T\~u/ra#GN:nzqECy_X h2޿;VT0;b1NsIA?
Ghftl?jϸ/<e-j|N8jM J8q
hBŃ,v?~ԥ1+H@_Ku9=g"V{p.t|Zlx_-$ȦfجG 	l؜`2L <硐re#G/H+0| "{?#/@#+*ͨO\]
V^# n-⸝]KL4bJ'$:t6V2Aar	'b$I$QܛW'"9$?2nn
 '~aڊVLS;+MCBp7[ܼ*}*d;
7ea[l -A}kg-,a:)jtM+ ʅF01j'	~W00$K$QI+^gt$f,~bI'4+Nú]>e_H{;xV-}{~KMLR$.AcUzE7Ԋ*9IȽ#WK\;j]%v7ux?*kDw6A5'g_1$B)_|6e vcSwlJ>.n f[{Ā J5M>o ߳a,rRܬ{'ҩj)O~`XZxIE[{can{pă?J[jR#ZL+n]coHx9X2p1䌓V8LnWZ +
66H`!ZTc<!ӱbx5t)}bvW=}3@]CxEI,l$8?P6S*G885$ڥCz{:M7Eܫ̅{mܬGT@ԅ4d"wF5P;p	SrCPK\ldbu?zvz+*=:.}{:ʹʮelԜIu-lbǊ)8 k(;QE Rw PHF}E% QE wE 'ZuQ@.(
;QK@(ގ@b ( (E-E-G4RRRJ`?
;{i bizP hI@FyRh)hh ^%(
 QN_z&d@a7}Ez[e S<kF[Wz5ZV8閖V̨F/$sҹqFJxZYg~X>"eb*q}iL˅8g2FBy9UM7y^-k
A9n P71Iw3;#_~?IYdi *ժn4Ы"|o HHkks7r}Wf+u*vIBיiH.u(g\g&P[.	`J+w9++TI=2
lTy?-Om10OP'M	{vݎs2Z,%FX3`7 *J2oobwQuX:
j蚖*(wΡk۩c\JF
8"%B:Ds-LA~tC	 T?LSd]/n86 qשk7sާ4+A1{k޴-
y=n͞swgkhnq-Pz2C1r\<@L9	/';'$}Eh?:G,D.ѣ 'FVFKwv^鰱8_r0Q[Sw]ﴋɋ>Cc(\ҬZiX\C$tF`GLzڨҥrBO̫ RS.XeRW;WDm}Ny^[k(U	 ʀw*qg5<ms /fH#CJFk=sPU
fgQ>qը<Ijpn~`t{bt亖Ռwc̴D_
iۯ 6ǃȤ	{gTgo-	mz2)8(==ݦx. :O'AGwyϺ!KsZtrf)3G싳:&t̺odpʥOZɧߋ)$clz~uzRo\ޢ{_h^v\}3Yv%>m0py wkm;(:9K,.pss9uA4
(q>9ټ,f81̼_p{+ͩv:Z̔jodẇrۻ'ltKikؔNO_ԤGKdƛXʿgWHW&[Ca*ƽUxu\1Yda0k\Lx {7QZ#YCA08M]6&]-.]r"CCt It'ə %/׊(RPJJB1H	C?Ze9\N.0=~t`޷4+[MV	{/j[x"-7-%!)$,~H|%MaV=)Q@(aKIE -(lxzY
;V?zz9B*r)2WV=QԢk?G*	,e,ܟʺ+B@ī0. /BwW $Uqр"	ݤ7ja7 :}XMK4TpѝSH6񳉗MCa^G]G>JۍE$ nw_MF
Ĳ9q*+6c!553+,1<p-Fec&!>?CTeIt cv:d?qK*:Ƭ$6s/I?(T~c+8_8mXs?Zȶlkfn*¾֋%}gZ]Օ,(Q=s$+2G;<$(jo?j JO>z\&nP]Ey]dpi>:l >xh2ĞZ1ƲTaa9$RJ;)$]{ek{hn U?<uu%1GZi;`ms]МSVgR5OiN~ JGx- sչ!B+jV.nog?ސ:uw>"3{jǢr3K
Z'mO-;1\aL*å]TW9}E+}}kD[ژ`HhQ qG5p'ԆTɧjص~F[͵@~<;Vv RrjaatPQP+zSИdYc"zbl`MZ)tRU* x܌8e=j힥5Փchu!R0 ޘP~G@cv;:mŽ܁*_~\NR͜IX4ԍ%rEsz% <1J[R81= slRAfuVOўxi?:p8} 0p*T\z&Dr
>6z3GZJ \FyGQJh &P8 dҌрiq@	^Ssۯ Iڎ;R)}h`- QE QE 1EPIE f NQaHN)iϽ ҒsIK@	I- 44f( Fh(@UH[<cLu4m/JN(hh`Q2;+i9a?*<8$z?nc$oMhIipZoZQH@BϭVBx``~U4^o$NdSy6's~Bn6FN=X<! Ao$zIG5yyi'%BkəJq-J[\2"4q8?uSDQrT5{ם|y
nJ;H @5,EXQcF	RI= ?Q4ѳ񣙂HƇſ4:տ ~( W+T 7? C'OoSj s NWGpt=W#^}bꃭýq_i|?i
m7MƋ;!yetDRN8jKF(Pyd
 i3jH*d^A(~M1v;D(w\<Jߩkݢgm/nOW;[¬V<[S٤]0C 5klj,<g죰*ܺΝn#kXYLi&	$=y+A.\MZZ"webE0S׭7<&Ҷt^is "`n@=
ŧ!yTfTDyroF*Zݤ.fݳ#m_+?uܞޢuWjCӽ֕udpv4{9PDY[2'?q {ըU?#VČE;5yIc*~v;$Q64MCJ正2?x((8h'v%KFRB]՘8SY/,cr8V沣H$/qAxuA]ʼMnulw2ĻՆA)Y<O6H$Qaud~>AZH$E݀9	
7xr1SԾdRtTeŰ")>Cʟ]}qu7
b1'ӨX&Е-F;ujB-,q61sW[]PCÚT,JGW9x63=K~nb8Er9V_P3zUd)'azQoݿ5ut߸qG$-D*}q^-7#S@< Y^C9

;5c
TI8%X3՛BiSMn%Q@[t $2)$eFA>jW'Jzu,uSKE pZbQ(-TQI@EPE(KAR'9c8
%Mţ|W,{{z2itTҷ) `wrgm^o4r[YF[vI{Wd5Q>kZ~>'ĶS;kaBq6sH5zVGR<`䪟s>#G5&Ҁ})BN18 LܧܙXʽ7Z#'Y-# YlmcBPMdèq;;E=8HYGD( uV*om-ܩlgk+$MV,!\li&3ZEwޑd9@ E

Nqil3Nk.hn/v8OV
&wQNF[ZI @}z+xPFY6	.I>氕NѥQq-IHv]LYj(T5m$uݖ=^*
AKOU@Ȼl#POZ#sRQN7q-X5dI0ϽIe 0$µ2nIB(3jv`u4Ȣ$^yFȡH;>M#GM-+ N}Mʱ~2cS2` 皡r,CM8
 o,؃RB:52;(Sqy-m #Թڌ_` ZyYb&?1y<֬ZkOq@,3}MlA
M.3Sȭ)&ZYluӏcTr=@Qx1g=̇	sUʕ8SVYymJb4l
Њݵ׃|*80
)
Mlv,,П^Qڱ$K%սKQ3IJoQi9XGz)ՙIIҊb#3I&r9RRQ@QE 斒
ZO^ )h gۚ@9R)h( i)h fs@j)(@P0=hEPQԀ>Q@%-!4 4R(uBќ g7:$tSSGAE1qڊ{r1ޙi|=,ujf;UY giZ	9Ljp=H]%d`'ZnRbͷc_hUBmwM$Bv;\;FsEU*}ٛ~&.ƒ"Cmd<j<ڥXҴQKc7&Q$m$۸*MF>OzO%ȭQ>r=)7@3SeMyNvZRHzFj#oķE9yRzV:N0֟(\򟸥>Eh
!DE,xr)cKNOJ3};@ PhVTm¡bz
|fe(IT5hB	a"G`j`O(著p9''ޤN_`uJUu-7su0
zuRv4tor5p=jV2,ҕ$@<k)(Tѭ.9HǔZޝD1B::o5rT}G8FO,."]5nֱ.#3Ԗ5[LqO:Mq%Se$_#.zjm1@͏뒫MhhQ"5p[̎_?Jњ } Pc!/$ !h*ǷEJHbb|{`g@@wfX#eI@3H{uؖ;,dbHTn}ْS	lyhP6Q?21Τӭ.7f9!ԞÎ Z*%ib;*)ʐnEXo~F?ʢvyROވc bWln?GWZ;MkQQ并?ˡ)n--lnu{ܕQ~b707py_հm76Ao2:sqj}{B:%H.IWrgqcWo31̊pU"rkE((B4&:)PQPOv<ӸGETQKLd(
XW)88 c2(͸\qI}*g$A,pp(7b,RJ0뚆,[ak]Qck|b'
y9\Ue?iwi+z-7faZ73p̨z¶O
%珂s=뒴{iĨsՕR''2Y@On\Vem:3Po$QVåi[QX[rOՏn^Fa-<m.9vZrcѻogm8{ 1YN43q0 }<zI%35k	UochKsSQuQ];˜Vqjg&X٢ICm${iE$iZi ~ʨVLJHE؁9횯,{_ }j%Hfq9RZ*7L{Mϵ86*lviZ2Zݭ\;0trvvCV
SЕwZkvɟO>?ն}SݪREU;mI!wfF%K18][Zivw[2'GGe	_A$3,SI9/c{MzzeX<s6r8=VNRO*-y
&4`$sS
p
d(>@z<lOJ4`Dw)ɪ*δ9lw~Rhiq^}sWQJ
?Z\#ɵ	?3$0ǡIsȪL8&V$!׫Iee0`3#6F*̍NrޭPaJ0/9&-m6f9 gj[8vf5}aC3zZ"ʉ
;LQڀjrӼ]
Vɯ/YƲwX>dC
qcOПR		?xpDv.J7GלdP2!jE緽@ў`vD;y)iw'AQԒ}e!zJ_ʊ LьZ(  QڏK@-&)it QF)z (P 4Q@IQҁ~PQKIڀEPQGAPL ъ\PQGҗ ';i)G\PQGzbΑ#zZ0[@ aIE/ߵKY@\#5JڦX<Sq
?LԮ  4Aw7iN0qG׵b>!>ckO+p6LTx8 d׌gq?f3 Á פ-IaPTŸJy$edf`;S|?֢yrFr=MT J%uWmic,QoT[d1ⴭ=9K"=C6
+"y=# pxL6B{m5B$ ;1Pt{X|/<wYC:d[ȉ1OJtNʙ㚆K YvZ
`>GFDTW"ԏ$.$m[̈<GЁlcrxĽGS"`"hm2+z'$i$PZ6"Nw 3Mq &RZ;M.
5ȷ#H$e sxe?JĞ\renQsb*GJ¦
(NX[:m֞NZU:b!I;<r¡xI5g6mʞyh5M>:o/(~N<O=.	"$g+ ֪׵!dDY,dPw :-B8/96*?).$v_/p?JEܓZt۔%9$=0ΧKI-~rx<氳RCw=Dr`HT>̶#6.`19i z~X}08o3Vg~*(\#G% ȇ?OMG~`gcC5>5DKfXCb}	~R<pH}<z0FCvȐ̒Tc4lv1{)zS)QE QEEPEPQ)G'R T	\hc]f"::ՈdVuiWks|y\`߅*уW8RCKo+w8椸M/K	-ct4K\[dr&&!BVQ$Me9YO/5nM%qIԔu1

 Z"ym _Y=iN1*.WrduRj:N^;} Y(/PD }C(5R&Lig,I'Ri3@RjE'AdX$H֬$^a"Q%ȯ*RҴQ3r+\
8)cFUUڃbΦHqz U o| @QMvIu1hi	 u-7= ?=3@+aWRgG#dVx9^&4YZ03KEʐɐjeec+Rь!H( 1MMj3$UsodcS2oR7Q[/_j.
?tzr6IfSR0ZG'#ڐʩoXPޘZpQx D*SPj* U(@ȣ 6[+O!bO$)Ћ
HCGw+(pqj'JvϡUN1M	Tq\x[*aӊX #==)1Ep/.ҝ=ܪ_JI$91Et@ܭGڤosQQKGz ( ){ (R@Z:KށGZ({EvEPE ^ԔvQހA( (bQK֎JJZ;PQKI ( KE 'K֎y@@))W ?ގtN
%n8è9jdkcjo7ZDsF(BV|<kXv7!W╀ώQ'=50;@$v?WmQnUS8e#wMBgl/'}@Wma|mSBe1C!'SύZ.=
R;US8=iUx)۪,:\i8<g5FTJz\ w=VX  zbj=-/KVg|P<dP;ovTܓ@<ԧ$T2Zv;RE4&f
GPlN`%_.F yVI0:+
A9<Ҭyr8d ca~{&ő01"	:}1G^OJܶO)\,Hi
B's!Nsy4S$׵X,>d*jTӛt|?li:I?*XqoJij>Glv4$}Oc^vQO jcS1{QA)j=Чw/=T.i	hWxr1V4)ϖrNd:ҲkT
>dR݀a٘cR4I( (aEZ))hSn;}ugbMW"E" 
۩.>{   OUĲ@2/^yKEH,[7`4q6O=qPE$ʲ]NUPj&[n$Hbdrk96)Y5U,O\ԋ (:+Ȳ]OnzRZI\3J(hhǭ 
="$[$U2*2v#He~+D<RQTHnh1	;IɫWpTe7dRgOIp)3IG4 74,?.}zTy.AϭI}j0x$R}A,=zRڃ֣H4ϵ / cOlLT7j3Hdwq@#V]͔ 7OQW(SL%\gIT; y<WRGzK@$g
Sbn#ZM0}*ՠd'j#([>AX
\}2TzvNFW<RsL#DTЁÒ Lڼ_ZxMaGz(AjZJ3ڀ
 J
( -Q@-\ڌ@GjJ)QE /z3JZRRA(4 }( S֒PEP1J>P{Eʊ )){R Gz NQڃ@z(Eh( S6M -QLBQE vcK'Ҁ7w.G+aUk+1DOB{H޸:P0;h}*;!#5Fۢ<v۸=iv?VUj=ȩ2 HD3%P>4\,_QK!	OZ}BV
R1#ғKSC'yMR sH\fN!oS$	޴jRL܊K9ڪxa4RvAIj( 4v
PL6lC
8a TA-;W
* Ӣ`TՖXLEO#P=K*)`bPHQZg@JN)ѮxA8q<PdWe+ڴȨ=\3S<]q@ASȤ2喧wa&i=Gc[?|+Ͻ({	O1v	,Gr>U=FL3}_Lؚd[1EJisi
"{^MxⲳoQ<ʝs5D4!5sIcHǰdxQe'VU e9S(miw-lךMWށ˽sRD9GFFU
FJγpzEtfNc'qmQX8oMTc->Viz]!<縬RZũ+6KI`%\bS% hɫ[mJ4/1q3Qnc  'ɒQ2BR9!DtGq =j3th d[tQp81P=΁P1PI+شQ>BџAGZP39izBڧUcޚBlDUF*1O5hKڊ`?;5w"óFi4as3YW%T?/sRQen@EVNW6Q&WR=iRVQڛE2i(@))i Sj-)C)i1iL 'F{R,H'5C`gҪ䃊`]A sUCi#'@5y@ѨԦ]āen1ޗ@!Rv@
T}j.icҤD?Ҫ$̋>ɟS]v
'QqϽG$ӹ :RPf:!h4PIE -GOZ ){PEPKHh@ڎQޘ}袊 
-'Җ
=)JZQGz 3KIQ@(@ Qh3I@?ZJ) j3A
J
 4Q h =)(sE% g3E GJGCE0
 >dQ@j(A
PS:bmT VNhWq@N2w.cAezҲ=@l"NqƑI4prKn ={w1?EJ㰻%(@ tM+FWҤviWQMӗր5f$(UZyM3ڪ;$LO&{P ii3Fh =;Q(t Ň~UsIm`} /}1WJˆAZ<gOК5YHZzF`qRdQ"2)jMF3ڃt
L0j9ZTfݗ։Zc 4;1FAR%Va!l+
fXa#9ZX]E)wG'ҔG4O1ٽNMGJ{Ҁ
dԐ$
'+^i-ݵ=DK.o,Z9Y*H%F}S|V\/e`INр*5k VյҟG@>w.l,2>QԏJVQV[
ɷ-ȍ%YHb#OQU&A PqHE@	A$$J Z(> }h(0E($ H?L bIFަ# "NiE1L֓yn~K'IۄxlKr#ŷcP]^1ŎX}3RP]G39''ޛIKPXQIK@Q@Q@Q@Q@Qހ6栥(Xpi3ޔ6Ms)1Af)\Hzc1c	@()h>v MLBZPIw zњOƀ(J^ SOSN4HE(Q@E% ~RP :(1
(4 QGJ3L4{RQށI -IH Rf ( ?!袀
(E ;R((4~b׊J(  'Z^ KLAQڀRQ@1ƑP{SM/jNԊ
))i RQE /jJ(!MdD6ݎ(9bi2?1z
ĬAA*0T0<ifdBzz`qN`N#ui(s ?% ўi斁ގF}E7#@n(39@ɺ=Ŀ<r*DX)3	*)f:zS#TGcg46"D`sQޫ	DLR0ǥO"=06W({sUq:J犌dr+AE#5IK0z`TFXF!G)<fH`:x>'1)qE ZOj^Θ>)dU7(ЎE!M<o61S]Z1ASvZ8E,4RRS &)qJ Ӱ0)nXiQN¸ƌG *iCph&W+2WJAHd0<74âj!lt+.x7xArIIEÔs1c94(i)hP)ۏJ mQ@Q@h
(
(JZ r6ߥ+sR1	)i QE QE Q@/lR vjPr3PP
SqN5Bu-'j(z(i֗4րQHbIK@QQ@E&h3@E% fcE% RR@z( RqA&x@I;P1i;Qފ ()(i(J ZJ?
( ( ?J ZJ	@:Ju :(!zRQ
 QI@cVaڣ!q4P1i(ZJZJ ( * XRր%&'$g4(@-Q@(cI(ۅ.iSfHE1
*"6OJ|T$LSEb:}*ImS=*qH͸sڀe`֥KnƙƎaȧV|s<gUWXu9ZG#ITz^`ԡN;
袁&{c5vEQ81cbijCi3GOS ( ֏s֊B
 (4RE =$d'kJe(-Ҟ;Ь֟NlZZm/JbEP!i){Q}!ؕ.Ai3JHRsI(0( ( ( JZ )(
Z3E Q@-PFx ( )E%{Q( ( ( EPEPIKE %¥Z
ZNSi;QABњJ3@iN6Q@GJNԴ *ZJ=hE )4 QIR:J(~vJZ (G~@EPIA4PqE(Ԁ( RQ 3E4 製 QG?J (K@(43@IEEPރ<P
F-(  (E
(
(E QE QE Q(4QE RRJ%!ăчQќR: (振p~ 9L4f=*:qm^V\
frC<ӸXuhzt*T]r
F>24M:S`F]6v *7?8 .
JPt8d4N=hFiM% -}h/ҒN QE -	ߊzchD֊XҔjwTm!=8v
Bh&4fQ@Q@Q@Q@Q@-% H J J(@j(
(
(
(
(
(
J\Q@( ( PEPGj(E2)1{QIE0RPN)Z@/S(?
Z(BHhPE'ր3Iފ ^f (ގ })M% {~4 vƒ( PFhE 3E ƏΒ:KIt QJ=(z(4R~ R擽 (
CKI@ޙN4)i(LQKM?z
=hC
(
)(4 Qڊ;E%- RPEPEw)( 
(֒p 94ަҊbDۏB)$T{Tt%- QE RQ@RxnWҡ	Ow
$99iŦhؒ,*,ʑ*
DF=
70SqO"R1}A94d W g*OL968)3)(Q@	KIE ;4SisL4\M&) QE QE QE((()h ( %- )hJZ ( (4QހQE QE qE QE Q(((((@N^Mu袀
	&L'&ry(QFhRRPE%- Q@j(
ZL@E'nfJ>RPE% /j(G4Q@.i((i((  }(E% -QހԜRJ ?(QE Q@RvaEP@8u!ifڀ(0()h
( QցE )(@I@Q@Q@Q@袀
(Pג)81	)̇ۊeJC
(
(
(
(
ZJ(sN
SL HRӄL@Wwz
 Xjҙ7}i$3IހtRRHa((Q@Q@Q@Q@Q@Q@Q@Q@Q@w4RQ@IE QE RQ@/zJZ ( ( (hE 
(
(
(
(
;QE %((٣4)昅$J(aKIQ@Ej(Pڊ3E -%P!h)3@GEh QIqK@Q@j( )(J Z))h h{Q( PEAE 9
)(&RvIE(hE QE IE 7 LҜ)BQE- 
(
( f
 QE -
CE RREPEPE RQ@IE  RJ( 
 袊 ( ( ( ;QE QE RIE .ii Q@sF)Q@
) QE QE QE- %Q@ ( ( Q֊( :EPEf
(
(
(
ZJZ (
( Qh
(Z ( ( (E QE QE QE w

S 
(J Z;E .yf;E - QFxAEPFh
((E QE
?PE~4 w3@&x
;QG QE QG@IE(LQ@RZJ (@QE QI@E%- h )( -% .h
(
(ԴP hE Qފ( ( 
 QE QE QE QE QE QE Pi(  (Fy94QE QLf@QI@-%- QE -PEPEPEPEPEPEPEPEPEPEPKIE -%PEPEPEPR@Q@RPE QE QGj(  Qހ
(
(PEPKIG@-(QE QsE0
( QE 
?
9zZJ)RQ@ϵ%-%Z ( ( QIK (
(
(
(Q@Q@{RP0EPEPEJ)hbQE QE R@Q@hPފ(( ( ( ( ( ( ( ( ( ( Q@Q@Q@Q@Q@Q@Q@-%  ( )i(( Z ( ( ( QE QE QE QE QE QE QE QE QE QE QE- %Q@Q@Q@E%- QE QE QE QE QE - QE PEPڊ(AEP0( )R~PGj))Z?:(ڊ8s(4 QIK@(A@ ( ((Z($Qހ
((AGGz( ֊NZ(1MQH((AEP0( 4QE %Q@Q@PI' ( (J(i(
(
(
(
(
(
(
(
(E QE QE QE QE QE QE Qފ( E QE QE QE QE PE QE QE QE QE QE QE QE QE QE QE QE QE QE QE QE QE QE RQ@h ( (N QE QE QKE QE QI@G%- QGj ( ( (`袗 Q@E% ~4PEPKIK@E QE( 
 QGZ(Qր֒E%
PhQGz) QE QE QE QEh ( J Z(
))h( ( ))i( 
(
(
(
(
(
(
(
(
(
(
(
JZ( EPEPGz(Q@Q@Q@Q@Q@ހ
(((}E QE QE QE Q@w
(E 'zZ)(h ( ( ( ( ( ( ( ( ( )h
(
(
(( ( 
\E RR@Q@Q@Q@( E QE0
(Ɗ((ES 
(hKE
(%/ RR	E-%
)h( 4QE QގԀ(hQژQH(AE /zJZ(( QE QE Q@	E-% QE QE QE %-%- % RI@EPE
))h;I@- QKE % RE QE QE QE QE PQE RQ@


================================================================================
FILE: app/public/images/tower8-server.jpg
================================================================================

 JFIF       C 		

 $.' ",#(7),01444'9=82<.342 C			

2!!22222222222222222222222222222222222222222222222222  @"            	
    } !1AQa"q2#BR$3br	
%&'()*456789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz        	
   w !1AQaq"2B	#3Rbr
$4%&'()*56789:CDEFGHIJSTUVWXYZcdefghijstuvwxyz   ? *ZJZb)b}h@	(QK@.h1HH Ӛa$҂Ӏց uQE -- (v8
8ɸaSL#1(SzsIz2-8i?_ʤJ( @;SQE
(
ZJ3@-% RRF3HHeA@M'hٞ4 @
j6(P(Q@E&PI;Q ZZna>Zg}| RۚO` ЙĚpP8(6}	֎}3hȥ"!)2;@IO}i3)Ii|ǮqH4$28t37LS1ُ1{USb#&FmD'j_2<cDp{Hc/N*>3)x0~Lz~cK)jwޢ4{d'➳!jNM=E0u=qL(lP1dJێ]XGnhGUp@ 4PK@isQ@Xoh@Lb pɥ:JiC@y]z>
.ǩ4z6>b8!eYz QA
)@'41.6v,)>^Pӷ/ea #1)p(_'4P+ع :RH]iA#aQ?y
f3%?`?uHQP;QE Q  )*A4V:ȣr:)b\`(Mr:r
$jw֏>Oc1@c.qK a(9*f'&Ƨ$8>*SQ)wZar;HI&C
J3FE
(&
3HH"LJ9֌{ ZLZ0(ڀ"RC)0fh"M$4/ҕr<3qR)0␊Z >J;i=h&ijQ)hQQK@	KE- %}h ,OJJ~I0T)<EeljMуAqwM;>\V&JpMD#&X-nAF34)LKGPE
Z(( ( > C9G~M `E  \RFh>dQEF(` -&=@Xg4(@~?.oʗ<@(q(
1hZ2ԴPdԻz)7ހ#֗ޙz/i6@t^(=I.;=(ORiF9 (RfLiQ@@>撝L}h3M1O?\)
!$j)X.V9Sy0(5`AڞғM74u#{IzRqIvɠcM3,z/Fzi?}I4 j MބP_S@%ʌԟƟG{b)1@=h֗ ){Q@E'җ *iir4n NBOƍ펿'4<~4|7QR+<)~_`>!YCj2<GN# 6~Ò8gր)Y?u-Mq](wbhĢ?
 oRoc&iH3S

Ć@G+ޚ<~JĻI|v)ףa2i3RyKwdhȨٛ[+
3gۊ芒0SIGޕ
tGIR&?AHZ1	tEini3KE !ϥ7I@ t)ƌeii1IJ u%&H AI=h֏Ɛ#֌
( )3KI@4sEE-&hqҍ)sE hqFH,Q@! 
2M .RuJ A)h { Z))hhjLѸ lҊ)rR##>%- QF((<u7vz
0OZ R֌(s@
sNf QPPf4Q@"㟥'{b)6ьt,zQԓKP  -&} -4\
L
Z( ǹ֚dUMdnZc
9<i\,Ne^ԻwA ud(٧ JL҆\Qpj0J&oLӸO*!7	\,M)F j:Lޓ Rڒ`/NGt(HR`)(`R`J3H3I@ţ&O -ߩ4  {ѸSyciP|)p޴Ƃޔ47p%GR)Hfj.,OW|ӄEĻ&HOB)Lj9M- R pb=֗rAS
i~#=Q4Ф4h 1tNAKz߅r:)9K=}~z8?4㱠.&:(=&1E .Wo=%'zcހ:IE#w E\})44Av<{?~T (<w'M,	Oʀ Ar]?CqIY@qB)οLx4	F{2O\dJ'L{
B̄S3`D?<5Y_~w2p04
x0Jv*B>hت&cie?fJ..V&lPiu3ϡpa֫J*jW.IΠ9Kk<GGzdԿn ?
.RE#4S0BqH!-'LѓKE> 4`RR 3I 
`ڌ	43րE7@&9)s@}(ÓE&hL@Ficzu4
Bi ܓӆ}iBKLAQIE :4fE6
 }!aPSI3@KMCQKLњ \њLq=(,3
 2ڔ(E f4PE6 -d
 Z)(#ҀM݀&^i
 BXQwɥ;R撊 )i(@E6@?:0{E. K n=N>A.E&E ')@SP^M#Fݪj)X.B#=6j}Qz
,;Ǩ"6`4X.WS9*`Kϭ1xG^iy'ҋ-&hSQFF( zѷf"vVÓQHp*0WK>C6Cކ0\{4ƑR)1)lݽs@\.(# ziF
q(M2H$S2LM(= .~7h&U42I vvL wY.@SɤM1/p)X9KؚoǠGEJ c)w4X.AJՁ
٧v.d@I&VԘ RzF(]t
AКxv?Zb#,ORi*]z(
8?ZXų	JOvӏZ̈h?&WКq)A=FEoo 83@fIi(NhFϵ3bGf$v:R G4Oʔ*Qe&)Y1x@zP;%?4 4P~ÓޒX+d}
&ē.)R `'7lΝOY\q#ߚR  )w?OЩqJ#W+daY)ݔe{s@]IlcQ	h+j3֐4N)Oi2iԔi'Ҍ:q@<G2h$Rnf4vi3IQj@.i3F
jLRތPy; mQ@
1NȠIK@-% ( Lѓ@4/J( .i3E .h~ f4 Mҁ O=`1Pgsgց֚XAdNSuo2`9No VoN>""ؠ6zRWIs8@
ڌe{W2=hM 
Z.XQךJ\(iy!v,IzLQ'&W7gҢ.hX~3cG2h{.ij--@X}ߚSrdh.h j\f.h7#֌1})0{ ~}3֙@j9(;Rf4 RaOaKpF= 0F ~} s@I>9g ncz(S mA,}h~҆8@
7h)<Si3Hv.hbғpxBIah
) yQ~RivJqbQ biyҍ cR }x8=E ;n4wZMv}(ێ>o4m &4{R oHX6.":V2V?2Y(kӏZP\sTx\ʑVLh&;pX6}NirvGaȪdځdo-\yG;!c<WjҀEq{bۚozoyQAHBQj\Qm4a}KU\owʟ?h|}h}ij_,GZX
I{zPsʞ?
v=q@mC"sRbȼ1jmJ2(@Sq)0‹RN dU<Pϭ!֐!L71v+БQ
0ܞJ-y*6e=jCSw{⋏ Qc=Nhmiޓu.(ڌJR(ҁZu&E &(.i3@=qIq1hq@iz ~i2)c
7{S3IjRn4h&i?(i( ( ( E .( \IE .h (,n qAOO֘
.M&J9ހ)3Ss]xph.hIE :m- QMɣހ8wR KSNi٥})9V);}y)6J,"ɥiX4
Jz#/ӑ@&ޗhg=E048BM[(f,}ix>FsڡԢCy=Q0zP^iAJP!&cFOҘKz\PdQE!4cR GBE&ih٣yh;--i>t@B_
 *sSIc4v!( ǽfsIQzP=(֚wS %-I>ҍi\v'2ޓ\O!Eȴ$8` j(hXR=*Y8jUYG
blPi72E>=Z2{ix@	N/ Oz\}ix	ǥ.M8SCLC9IqK{ \Ih.0{Gъq=|N.0;6J8x.R()1՗C&
jN4ߵ!4km(U?dci>\U$X)xZT^*{brMc=	6J]ȗ~MSQHӄ7Doʀg
iyO񚲶s?<i~4D=Xl1Hz
,)v鑎pӰ1qFj,+i(?,/hcSKMi<Z!hSqڛLI	贊M{i@;L{Te֑I2R $T9cޓցؔʹmbRn})h &O4ϭbm)h
(
(
(E j*J1@GKO )m Zv6zSRm> dQѴIKF (b:)| H&qޗoATtfTpXE֊.$l0#5KKL
-Rh4Z3IE -4QIL4Lњ Z3Iɣ\4b`/4}i(R3K(h$ 2@YHY5gR
Z)LRzRfsFME(lc<z_-E;474gڀ)\{!hȤ &3@ϭ(=h斛z@֗w@NÎƗoZV?jcM'ރp=PP+
2L.} /i()
JP҂`8LFRM_JB}h=
'PMwA=i6
LJPƀm.74ns@4=iApaKn@aHgڗM()xiG (]ҀC篭!_Bh2=M'$좀e֔t~tRn 9KuaTvƁR1Bnɪ1N	(THnM7M(O4B/IdYJ{Ξ,[H'ORMh!ݩ1ԓEΌǥjhGQ`ڔDǢ3ĔּtoQ`}bC
8ZJΡ	)QC@!N
x=~tw9iןƨo&e=d4sLCn?]Y[bh5
KSNMg@z
NecL:_@-ٺF2i2}iO
=EuIOHSNr~v?Rcm#n/?4b))n]T^|$j_.[e.xARz4lGo .) i}y)|^$dI@KU w(MW#O]1hڣ+]a-#UԴm	s+2RLn(:v)( JJZ(( J)h4%Q@	E-( (%Q@(JZJ)-Q@Q@-%- %5OL~RґzJZ'G)vJMѨ0RXj
ir/ޓ4jip)Yammj0 O7sQp֗i4y0im/@X9
70dRZ]H4Z>ZRzяz`%o fisG>Z)3I`:L2=i џjLё@f.}h?
7{R@ZM3֌
 PњO4\9E&M'4 )s@gRdT|ѓL	sG5J‰1Mɣ> EGdPzѷӟpp@S&F@
GV4'fMZ1X4dT[&H,JZG}.L{7P%Ͻ&GGޓ4ĹnhL^̨'I0)=0)p)n4(ȠAzɣpz ޗhQ@E}3 v}P 
<[>8]˞ٖE=XTwcUԾ|>>-H-#sNa)!O@Gm=H3}.UԼo2
aWIy'ܴj>զ~+ 3L7|I .jí]>@^'nnY>]cҦ_6u":Þ36_R dx:#ށ{eANW!n>KUlzօՃC
]o#O jz!,?%
Lzt(Yr7d[Xԃb.?R}&^*~֤}Mo5V5*$ڬ}<iQ?'GҬÆuAU	 >*]Imt&?.}ZfF~Mi=\,<%o>=NiV PkKҰY;].1 E1ce+޵,g-xH|,q:E׮X@xKQVN+CI1i ̣^jSGiЎFj6=N>Wp폭7i'6s% v,3]
þ3]SE&M%9't
&!5~
Tgdrz[9T5pN7N{Y[#ƝfJOZyŭ?ʸSIcvcTHi%%- PRRP0(IKI@RP0( (RQE v  )i)h w( vM~%DELhCaA<RSn])wZN#ڀz)1KL8b&6Z(X(y`1
4X.ȌT]JzQJvE<Rъ,"ԛZr0.*\{;Rj`Q`})|j~IzPC|j<N=)6
Zo_JMN)<FehOzO/ޏ/ހ\Z\{<FƠޓf֣
@X4|̵.[ҁw4~NF-ցFicځ`zQ@
&iEhњ]} m4I43MѓIE >=9S_ 3@Qh挊7
 1.)QԙDQQbMnhFmou67:Q@M4Rsh֖ LR▖ ֞(,Zmmgһؼ^{#cy,Fv)&dE42NqCFA`[5U<]4픃{;ocEd/˦izm4Ȱ$c&ˮEmn[q+&ZF"ZZ[=Dǐ:
v,7GX:?)G)'dtlu7=U$HAU[&lr{(TA
K^jSIH*OZ.c@HI{kV+c
ۏ,󬉮wb	)-I-D-C U針
: Qq#;VΙiqud̺*Ͷcc6m] +i2dcNbmF>sýX$(7S-S&~Q OBvQ&j`P04RGz@%Ir=)۟hg$b`ϭP>]1Z
N>+6BCt9
ҥ<:`7HGi6sVt@ Өu=?V3 1MnㅲWzm [!Wiz_Lj}1zA(aHhh&@&ivqML[&O+٤EGEb\Zhb]֍֢77WAze\,Z
(
ZJ( JqnST#MI
sG5BQE Q@c3@RP Q@@ )(()4 QE uZ?(G~(F(R@
(/j`(Pu


)qF)$}M/jH4>( 
 %PRKE %%-!1)
)4 4[:wu]V\$f"p6
RML1讝> W[%_>VOsjWޥ缶^x|=ԭƎIv+}f p2X]8ZD|>	}k^()^@ro
6[]K$r-cd8((((Z(QފZ (^ R(OO&jhvSx?oP>`1r ηkuzOVbxM>?!MDwGpB 7YXH0	$U:{i%1a0STf=AT@5^H[iŰl.=*mKQD_jkRQ j/<:TefmqYi~bPU#jEVy|UOi3,r`JŽkI(0?Zy
͔b6*t)2p})'YP[4fZIn#jnAkLHл87d2+؊蝆̡o$[dݐ"9N7'㱠6b]-u䚲K">*ONE	3wH@XϨ<P5G g{bkYɨH`I8aZszKaޓ-% QE1JG@h@ی UwޫF ʭmY1-'?JnL
{AtN:Sr}98>l~4
@lt~" 1W^~cL"0s*:pO] `kel=#?θMiƘfHFdBǯ}j[-"RooZ)\v$EisQxN=)=
Djcҡ=jYHJ( (ZJ Z)((tQEYRREPKIK@5S @:jqҒ
)h$9Q@(@	E:@	Rړ 8cg4}M ъ:G4S;
- 'Z){@q( Fi P))q 84SIZCL(G9-!J 1'@4PIJh⁁G>|ƇKE% QE ZJ J(=)
 q%QHbzVC#+w>]TW$l
3Gé=֛u2:q+'1ug,p*R	3Jv RŶ=6)
;GV5mI^Ʈ-4m{zUmB{;Hݖ6Yc$&iQÓspb{ r)nt[PmXbFW<y9>[+S(	
T-6"`h5Vm$Z2:] ?2P^åޤf @V*sSCibKWAor\rd>k2R]}ןikGpw0㪭4:J7SSSTk_I7VED:iuQRXRQL#֓pQM)7
 }XyEéi('4u/P'&Eb}jbZ3M14HjAQ/ZS$mޮUҍXWu_Օ@2<G-OR"'mj[{<;Wԯ^/`;U1n;Ί2̅$Xʒ}үOO%9⧴c cq4U_IvbQ]q ;ad7ڭݤ`AH Z~QQJ^=Fۈ!:PA#A&8?ζL{LձRYݱ1pNӟM>f71!$<g*2Aܺ{[dxܣp-KHdާ;z{̕ܒNN=*[cBoj]q!Bz[@,7%WwmlT}k	e {WXYYb= TG&bMM2R6bˌjh1&[7 42ܥWK-KJ;6Km<4I=m^OTcvo!ݪ/DW9!rV Rx;ճ]	LJ4[Iq@]hgKy6J[D@4((r\{ g3*zLÒ>U)zBz0z`.:ʘos<ئb_+ɪ /quL^iS\yY	 _U:R ~jqoonqҚNsq kg]AHb\TXA)i*
EHSҟVbCN=)ĨOZ=i2QE%H`-%PQE QE QE [*Ţ
ZJ(h ;R CàO52(B(h `fZ AE
Z(FsE'C@E QEIޖR  N@~
:PNA &y4Q :ъ	 ~cX ъLQ 'z0{E1%-Jj}NMOI((E ~Ph 1)
-!RRHcqu~
rN޽+E~%ʸ$UGs }:6#PHid;MQ%E$nVeGW`T /_jșǌJ$b1zHH_Ё=kW^X;Vmw*(] ^1+~^F:D~$5mm1Y##r+6iqtGU]#ćz([OõM.ݷ cQRc%*FWm gt?Z5;od+t6<F|9x[e <`{]iKЬNu{r+[KAEA
5@!QE"(Q@=OU	(<iíPҖP$EA4~b8jhObq֞
0riffφIߵ z
BHkP<\ ` zrR5[G5EygAp
OڨVRh.
G ЗXvR`ɪVmÍrsRFJힼ
,JVӹp'9ZԱL?CpkJmz`P)܋fKoݿ2IM=}QOn>aP25y\}aJ[PQ#;WqfPlmqSFv:eQΈAKcQr3#+GweԾmY[r헉VM3nP/I%`CLY1Ǹ^E	JvՔ{d4yKגxu(`w}jXOȱj g e\:<{	Cךdzl"PcU&Χ|G|?5Dfn\H2n#ޱ'ҥ$	c<cU%`VgI,>YHc{_1	c9ox6r=ͣ9_;ߊn4bI>W*rk*' Usj`ܿPʱ.0>u{U~1AJ(i}f5f`OAɠj"3{|Z1@-'54#
	`o΍GoΓ4ei?4C@XBixyOݿ=gVu=
[|v=#˚<ps9-sfSPU?=X5VcԳX0M-'JAiviTCM8h!ZoRBRRRQE QE QE QE Q@袊1h )i)h ( AOީS:PF(!1Eb0h  `Kނ9
1@ހ
Q8t<RJCӭ4P!h4 ZJL @h8sG^z-.(c=ii(4 =(z^=('8 Pi?
Z	(:(4 @	MOj Ɖ( NQE &E7Z7{ҹV&⃊w.N:p/TY4dp%!n4dҸXu% $ӻSu	C;_[t W8,R&dd8TёR<ѱ
Q$O^j2vH'y\L'Fv1U?[_j6Z}J?I}ܖT5>l ٿIsV .hOq{a~<Cn?q?*O xtƜ?;xhCk{BѯMb	.0Hkq'vhR]IY|k<>"X$Yʜ
4)i2ww6yb%Pi!n ER((@PJ
%(@(INjc8PFE1bI4/JHZ~)֤j6(Cl1޺8\k
*3F[X
"?⡶mIrUh~}eRFv`sU6LA3Pb4ఃU6ڕϘRʐ"nU421@<3U5[ vێ2j:IZǅ Ԯ.!9Zi`)m|r*o9
l,<񒤓Q] 	7VsD-rVV<WhP2*Uer1ʶzBMy`$=xiOop%S/$:|$?XmW2SLI$IccwSץNiHAiSBجtb͂3(8Ud[Y&\_+*$BҳFt=um̤! ~D~v&HUrGȵd8V\?RSUGPOQOQ]64R.BGiqYFqέelcڬkPpd's=
e_HbQ?w>6hKkafy,UvymJ+C=n\7Jt㍬ৡ^*{mQLV4x `{Xi!"v;L$c<;V,JJĘLjW$CݲKy-,.Px9V7am0W4Rw	i;[ⵒwe]w@>[S#~t4/a<ӘM=hRJqn?e5[W
"eCN=s`s{l*5,L9&`	摢*nEY1MG+-4CEN!PtApRjqvS5F %1i
:hj#ԦojYhJJZ)J)hZ J(( (j()i)h (E}>DzN-KIKL(QE(R9izQh- 

 A$PzQ@Z='0O/3K4RQ)x4 w ۚ1.9Pi88 qҀԇ;`'HzӿJ%!4RRS}0QE Rv4^Oi>6*:t@	KE :tvBaEP =)iC@
J-Q@Q@% RPHih "E" ( ZQ֒ }8SE8u$}-%-2Cb  %-:Zb TVZuFɑ2xsִ5r5H娯2[)3KLK
p$s*zRۜzXN77`D2}+[(#W4U:褞XL6d"~"2pNZzӃ$ޝo#r$rOҖ6)[cmhG+B9Ɨ΋U1Y?U9>-]ǻ5Wh7Es!jH-+!Iaudq2	&kgx_L7bM>3H8
8k:km!v9zԚkp?z:֒pqRPR̦ĺ8= C6/n %tuo2NQi<rvox%m 0-cilĦdSߞ*q {pM/}A+doƥꉳeko/!-}=T'kG*. UȲ~=V2"˩2X͋/ Z:Ӣm~<Ķ&P	S>=裏 }S!"̝ Uۢ(f3-'zSւ7-!@i1KHh+xΰ3\t~i=+ϊ/}ұOZ;g VAgD>釩PRP1{IE  RZJ@!4[BI5,2v)6E\J)v6QKѴhm4M 'z)v6 J
.F@3
ZJ(ii(- QE D zJc[%h4S$((`%}i3Fi R
3E (.( @7 ɥ#4t 'lN:84Kh+@
 PKtrE )IZ_ƀ	Pw)4&p( j\SBR
i4E-% Su7ZPDQE
;QI@I>2H:T}E IJi(h-8tJxTaEP!(=)M!@((JZJZ JZ((Q@%/nP""9MLREG>6)1Er,\m.(\b
@4֗+KGE1Gz(BR<u׭? t~]ծ롪~	 
]CVYeJZLTvisM-'SS790DmI*U	)FbswI[qPn9sݘ
(ZIUh%[O?.eP9Tv3x#߱Ge0G&Ih5F@#&+j#E
ʼzu$G%L`:cCs8BvC0lnld(8REl V!i})$F2H(5/zX,ڱ0Z-$득Scd%x+V|R&w[kqNʥPCa-cȆe< xED_OhHF+CgY&q?#pE	ݎ/U`pGz[(BNjm\xх*\+@2:aq\@wEG %Oֶ26Y sPOm!h2ԭ4C:7h2V.-Hx	xoq@
ckR-Y r*hH⎵٭
{+0Ni{OxLbLJi
!+JSGkP]=BOaHBwxP?]hgv~:5,)3H)(QE% QE 
J3FhQFh"8&:7IHSI@	LSE1N$IE2E({IK@-% #~Z]GЖ(5Dj)(`Q) QE
J^Phϵ/zZ N: AG((1i2M <`zRdZ,sh+Zv #ތcAwJ3H9@0^Խ(P:PM 4-0sHi@4 ֗ސ'Z);RS??IGz
 RR OL/rT_HS <t/JxTaEHzRvRRHbQKE QE (4b 3KIK@.(PbZ( ))h }h8cEP?1zgp*ƪku ]
CAE5S [j/Ry@Iږ)K0*Q}S*I2<@VTNdAQUJ3<P%KɫYXR
ʣjjK *;[4ޗC7k@n,(FӁY-ĒK)E ֦LnCaPOQDO@SMy	.ƭZ3uN0V`!yWՋ,1Ŀ9cU.n'qqr:h-gft${s.b|rOTM<EfqNveJ{Sz
OHWQ&|iyC`<{bXriT
zv4@sn矨4tAs#}-X\A
iI{nVYJdQc#֪L5+#@\ck&H+v4ˌ%'wn[B9d2yp[/Ǒ֧ѭGBpAf]Io2YC$ϙ㚨o& {anT4d6ګG`22۩aքƟZ_0FpBɲtp:	"yz
C*yJ 
8ٽHӛ]b iϤ_hpi8ZF6 >4غn/88,iw-@(#ĚƊ 0:WHy :z2ҙ,Q7fuJlWGVu	Ψ섦wyZ) -%/zJ )JZCҁE&hOA@	Gz(@%-'z% %( ((@}-%-1JZJ(w Z)( KPE.M8ү4(fHfTKi+hHF}EQtsV/櫕bp?Z+?S1XgAӏhb8
3^
ֆS]~mhuhb<uUh2R/."V4N SKh|,һ3ʟ#oq	Gn\~kPN?	hb3(^tGY*:s~ӭs2#icH22)hW Α ?sgN gG Ͻ;2}NH1v+}E߉
h^i4q]΂7ƘGIcE{HB?$j+GNhn
JMcth.݁Vh62"	t)n\~tΎk4c?2]8], G?_yzTXi)4?Q@!<ў4QR04:~6(@% OQԒuhJ~3=~ KE1	^@
\ucE{i$(\
tWըHG}E&_ - B+G[e 
|^'yFQ^ 
sH~^ 8|ѱ^ 
9O=hzOS7syy (c<crѸz״ <~3/R  y )r0<Wpz״^u 
C##֍ֽ?[N Op0gϽ 
=⛇ֽO YQk	G#{ֽo E' =f G#k.l a1 -%?G+
cK 4r0<Ozѽ}kW[e|>|bxF^>PW3hzz%3K#FEKVص𿆯|?e5/3ĥ$3Rʔw<ZC2׼<Opdo rl$ r}O3-/#=翘Ɠ }e =/_}  ^u,8 z|^'yK秽{"^?R/|[=38 =O
9tֽqm ix ,?ƎF'xG]ҵŹvX3E ,n%yGrT?B| k4?` 5C/sɆo Gbl_x  ˽ 4rs@q/Rl	WU 7 ҏx'x A ,<ؾv'Ҟ5_^ W獧 ?J<i  Yyh=Eb+H$^|8   ;E ?N^YMy&LX Mg;JOק[C mǂӞ !/fy lnf&1"'-0bF2ki$+L s WxIcHFQ2zI%F5-1t8%Eiu^$1dlzxNX#okq wmO,"S?!ߒ§ K.l
:zW7| ͏: ?ok4ޟfy׬ |ƽd?O7?	?N(F|y#O%g?צ `}.?;t\~-_i##.UiIP8h{Wm 
¿~~nOHRSΆd?NMsO7&C0<  OX+&0qV%	呣߸Wp~xl{ mP
=ۿ?jkT7Jf} $$o
uy f?¿ { 
%Л $_5 ? k ~f¡?R _?s '4<:!k+ ?/*_~ 	;1&4qjZx>P~n*AԮ!M?4q"	0g$~uz{ T	Ad lݎrE8#ͼ )<H Ee A?-۫똥!Xo'Һ 
Hj&VB!Z#
InZjJyunӴ5-7UWOU7=E4GZ J'"Zo/\ws/Ɨ#=Pb|+)?E빟)WOuN)8
ǹ?!ELUT˫~bt-PˤrR bj/HtmLˤȨ+Qmg M!ӯ[yENi)M 2	% r&
JO"7!q-Plѿ*LIh))qGހ5-%Z)(Q@)(QE1
nRJjEIKb|trۜsN?1ˁWs6=&muEKDHa?*"ukq#NsuZ
RtW<qȩtK2p;Fjv9}Qg_7"`Hx53xGʪy:pyⅦF8>]ǎAp:W;xy؇9&ol͒"fVj@slt)KSU|K)$_KZҳ֫n$u :5cڀҗ36t>Sq"\ϏtުkBAN3ҫ<<S}!HѾQ=*lS(c5xg,{rc9p1Vd[&)9Y$<18FVl[_-Vck/@f*<uo@{Tz$l#-fISv7VO@ڑ(@ 4he85Q{YPv`0KU೼iY\}{:Yc}ς9ɡ4.0+ȨgErJG*cQ́X2].xdvb;c9oe2	)i~>p2A#KW+1:~Л`q\Lqm҉u>"0Mj5AFXZz| p1Tћ&8`AϔN(RNOBi',~ZWrJRbᾦGKv4sFx@87#!N)((xS6R$P (z)uT=[j~GN݁րIQ'&hXOQd4K),z煮#ЋTVAlS#>lP( sxzGM"$7BFۑbOҟhwxvH% 1|S[ǟ+s3aIngh?|`
Ϻ㘪oDpvGzĚFS;gk{h$fF63sU) `]kc Ffax׆kY,^[!#\mߌ{+-DvU`|&̵Is3}ْKw̅C2Wv"\\I#
.pŲG~k.cs5%:MM&z)ՙl
ӭSilG2Xkdem1bktO20Ez &h詬ɝl-;s늊T{ZG cQ׊26%=F?*}>KOX$;Ǹ}0O|S'tvq	XYZ׎E%F ZBu(-$o{dg9\6KD0*Jv&	JVFo/i\OΨ$EpyNlc^Ql[)z&cW˘ t\ Zǈ ҟ=_SE?֏*\cxR  |+ ?Jrakq̓`۸^(SLR(ϗ>~~trd4cbjzmD9-l<V}>Š pۙ{wԊɮmn<\SJ<]r&
@g>gh[ݻ<u]v8+)Eҏ李^}fK=6y
"NO⼵+m#9y%  g(MQW;-irD1<v>{}?z'9R,l܃juVtmu 
߉t"nC*pJR'2w:UPVQ
5cH-<@mb-}[ L'nN3?jtF m[Bݑ6Q_$$yfJui7%Iׁ^I:G1^G\\} ͌\=VBoA0x H[Ժ}H5J4(1CyFyI$8\syu"H碠ɭ#]yNJ9ؗKFƳ
I) \-%޿g$(eDW<h!gT0l2@rJ/_Խ{_[<yLz4ZʩkVslZ)'ߝS-!!)=ϟ?>֒KD7(E oҳoOKaqߐzLWRUgk
?h#I	?種9EC~?)D?a#6ҟh}l}
}Vyu8yJXn%uU 8#9O+\qqvf'ޟ(tɂ6U9u8.Cef΀LHgCAE}nKIk:zG)Ymy̚{
5
/>FYZ,esg9Ap|0~rR(DN5vzַBY
\0O ^VhΧrPݎk{&]2@L[9$:Xkt$hl#.1G j0h3ZÝJ5kmfDG
= ¹ۋf*TEOoQASfX	&N>Ru$΅JG;\+|eכ!F1t\9`Izί0Xg$JQ#3$+-5
/u=
kq2?3sΌZ]RPAd P *k>(Q$rOHtwsk0<KDrC	8SҪZj"f9?s?$p[0^H
1m9.x)>]BFM?ZȹoaBd?皇T:
S,D-ԎՔ<@R3G	;|ӌШEtkDta m
/:Oq }Pխ8ǿTmt1<W!O.6Gv$:\O } mk s s 	4:|˹cG?!;M $xWtU5+ŷ\FH't
>)!8I+lI{4M|X[셙YLf#JmMi׎': ɿ:ه[CbU7L7hϨyOݨc@3֤m۴67wp=j\kx[dk0RT?JcjV$ X"cYOsMMI6o-ܡRǍ:W;+IZ+`	"f4~֤}ABq0K~t+(e-cY]#p4.+F[͖&oUpaK"98Pbc_==M;U$y
4907V> O@r±%Cё>  ZM@na;=W~z,:Ւ?H5o`41G*'šQzʹƓ֋  jXGO?ĿrO!SErIӏx iMnП_t1?Ȧt PBC4)ޙl` SJZ (KIE P7Jb/ZCD٤Sx aҔtaʟzMMBaOYA궧R2yC(P9}>#
}H/# =hHеC!jh$p0&p߅J-6$ FکIc0ܘ#{ML݈٢ŐoZVnE)r$zH릭 bPvXD޵WDxZ<'Ƴ.CZ[+<s⌦رi\71܋/lcq욕Σ<iBe qU4!V٣Ў'Fp	#PZv9&$J&򦑳Oo$ u
V8ȡgltL9=i\38ԱƌdOǷGONkMNvz	իFQ
pN2qQ9(qV,mܹ6*C!<cEFqa4`(j5)m#!N
T	/R)xGJhL*8DTqf+!ЎH7fV.naf`usNk|SiǮj"kUjJ[sDp'Zw<R)ՙ=(,|Jd.Y$dPRtߍE7IPh 4)&y%P0J SQcC$KIڃ@4QI N>N,!4g)(4f ( 4tMb&2%L@{R.t^)7xn+=xlI ª&nlMXm Moc8+f
JM'MAa>LgB>셔z]>4[~@q0 h_;sZD¤bGJE[:S968h*]E²#
NԂS![Yui(~)̲{G\6R b&čS'_`{UZ;ItCs5*prO=1xY+0PfFi$.Y9'5lNbHEj匼`@~~
# Wܚ
$-(ߐl'?N(4w:oKsܴNHڹzST4YP>{i74
V=?UYʷnYFb[ȨJw9a*rԉVF p䞛?eimve W4g( C:yQdAVi4SMo(?uOV2iqZWlqDNHp	ѷXzPi)+
-K 2nj=OƱ]+{GQLaƪ;W%8Wn<T`=u"JFxz~d5vbRlu c6S D]VQgK7E%݋U5Vx.HD	%aO&Cc63(;5{q
0]nizvB)JXaQD^vKp 78Y]Bued1;Jq{#-SxnXmTXh$8_Zik,ٸJ^-Ʀyr4y|K K#a\js!]NF]>LQ\(p)0FqOW'uIU=iG"KydP0-c7+%9mEekQ#i$G O&PKLB&_BDvqEkn?C|uĞӼsJ_ygHFONÌ#<?l[XRFIS=:ԚSo|	K?'*}1ҦgO%Q`=15&_ê:M#HAwpO++=H#Ko
d1rvtUnZGz\w7ABJ	=j?6r듕R\iu^Ipۘ8ӵJz$i2r  վ
3YAnePH#5Z{:ʾ#=+Ѵc8=fKv?s^մb@?hߕ
p+lom/dfMfg8֬)yu
 X`!@8'>̭ fw?-omv (;
&J[s޵&9\^GJ!kb0zWwu{z<JCXµ'XRRde2Ң0kW-2m*aCʨ`?]O:̗6*n6VR{t"IsОP'hkYSb k*@?o^6J%ēc#{+<Dɟ?ZjܺF"&]9nHd?)B=qYZݱ\yے;sSxO{9!b$eu3Ny7IQފQKIK@E
 JUAhB6ӬYy|aO)Iy_2đM
Xm!Fp:~Uf5&ͼj`vjM
p>-h3ۊҮXChx`s *UCyi$}ȲŽv֯Gkxq\[>U$,q>EݕI9u!ki%EeUfxǭ`OEYK	ߖ0*ϕ-A1#6 ,/2=r*ұ
1KFhqM]D,Ĉ=J{;U]F8ߌǽi$p둶
@s$ށlaHѹF08 
3a=Hgh}+87'㸡nLwOtآ<Aa5
[l~kRX4&]bxs[sی:I'rM9mcofm^[jche9l1^
[C.)n}Rgh9ǵX,f2Z (@w(߯Ke6Nsf"ZWO2N:Y75R1Ya,=}kF)䉟5KO}l19ȧihg%v#?ewDo+jA,x*Բ3^.ab/J(bҌ4jF݈9%`<_*թZ	(KRueS<ԋe#iuL5C)$
M &ݣ^h,3BTw1ޡ3H_CҝfS䍯_)\gjCUGQO=ؗoAG}*:JcjTɩ2o\Pn$V#N6	{#ќiH
9HqMY#Mʢ*M(% RRIKI@zSZy!qґ#ڡZ5VP5}rJKJ'U<[pILk,6EGsLaGb9)X.k\K:[y/%ެBƣ{=+=>55fE(.nf'yS
.3mrЈpv:T)Tvi\h 8#GBsTHRAFkV̖UZE*;k0|˵9l5kqA2=	h)kr-ES-@a3q^I)Dd88nҡH4,zUtK.Z9:I!o>`H539SS˛R+xB*`G(9GQW#2!덢cMEBRBxZpKk?g*H+&stc\# r{QЉ&/w!w=X9T*T>2 ~Вqx 6ペhUB
⫹iPjh15<HP1;W9nu1o>aYҡ,G!RGˁ2>	#x<XvUŖg#A	.g5#\
rQXF8R3or=hZcT6DŇ&Qlj<EĻEZ_,p
M#vBy,Q5
v
6
ZwI
6AGJ(!i(i>NƥRw0Z LRK@g&ݟ;b85CsV".4LAeGX撤}),MyDs`q޵Ms<y+_Fn{g"GcpUE6 VJ[1u)jnn&RTI{jid5[DÂ #Y#M+;gcOsW5MAf?c$,z:L)'	fdΑiL! ݀x_{ւZpIfdhfX޹*'q=s]~};I6"?-8fӨǭ;(:<Lܑe
'
CUXcGɐc1
{kY$RkbJ.2 '&е[K=Z	Z3c u>XjMD%q$)"FTq8}k-lNw%$ePCtt%K%(icp2G5^}jw1۔R4yTSv#yXoE>eGQ{Kx|G,#Ƿ
CX6mzte=
U`͕<Uj:3qbs?u<Wo&+%ܸtۜ+oxfXt֑+Kd*TנԭDI-s,1< Ͻr}ŵ&*${L^%ILB_w  W9+ws߉$Bq7c+hPf,u~,:N_HcwX$~/®kFec2|Ƌt`E-!x> yeX1sLW"A⴮x!%rGZRXN =G޵Iua$.4b1p#o?r{HI4rdmv;=)o
^äi&UFX?rzN9 kU/7S@bv$izu)m&18`z%2Cb
4j<mHGҳu@N#ܪ\$g5gU$,>		ǓL搳s53m ^0ts]-YkRgr'\c3`ITSkz=Om㴸[EFH?02>kăOl0UHp>i%bMba;[jKW7oRru~Ӭ"T$X6AwODF5h33ŗѽmH7,G XwHf<4+Y,ʩ95M{>Ry)13qRIGPA#3OUto)	Beq/^mFM/Q[˒&m[`H#Gj[n-mb6_V}Mr/bw}j-ȌWym^~u|~q;*<}1X]\Go
F
OAZp>]ZK71pY	!Yx9mczIrq[]IٟKXao
]H\xur +</H^8]ڔ)@C ڴSYgA;Ze6o>sT/]eco^z֤ޥ(700H C$ѻ)+XuisesF^/tSáx'$ :97N&|õG-rnhvM&F-T$gr3m"ù`F9K]gjKVpP(E-  <PHXAZ(CR}xe
w<6:U6ttm-ą'<cygt&ƑOLkE:Ko6d)*F1U]m-Ħ8"'fI5T+I/6pl#C'<Ƌ)TQ$yx=T55Ea8oe; sw4)!@9{XȒhy?IP;
>, E:`|45t֬R0:խ6-/w/ecSk1
7sH>PkSF@ZF1Bf' =jqu>ג0[ <Faצ	I*`S^<NB$zW7?.6i#In[kFc-Cy@! 
aLT8He$&T.pZ8QW  Smcu{q"
5/.*~Vv1j-m@=}?8CS-͡cbp~l|ӓz }>@=@%CT3oV:q -IseUiW$wWr:6hN)]Piz;[iH++*.)7b"ĂGcWrܰͻ!gL_q:։dd;[# g^zRsF	*Ww"lM(	*R<'$q(;=)K'
=w&c
&Q { R- z#Tr:H፤26rI}i-ķB)2\	4V@89bd's/UT܆R2e<Z,NNjhYV]Ր+*>KIEIQE QE QE QE 4ғz+Rn5(c*5^9N'e`:W2O&duA&{sQuazM^4Й*H˂e܏6n&jD#9<t66[4ocQު3bǒzք2Y A{E(\ousF


m"kK2s[ ^^ڀ:ڃa3)5bT$u<۹O]3HgwlTwMہ㨭A_XۇSYhw*Ahcb9
S,qƥպTO$	sJ3O
OҨ.51tjH޲>Ij<|¶<`YSWH>WҞo$vwgv9XJ\D*	GigQP'Ҡi9|관Hlx'\L2(2QLi٢-4 fM :;}aS7ѿ.e94RC;JzP1h
v3ړ<11*phc9#[b$bHq\Uئb -f,YH*FBǪ##e-{Y(ǚY'Hkg;T##̩7l.okHO<Mn29*}>X4]A.C(qܟQ(s.ef>ӻ*[$:F6=^0zɤ摉Iw[hw[,rK)SnWj |FgF^	.T]kdV3<ӏ5Z==ڐnFpN8zl$Ҭe}[J,H!2sz[zWEXM8;hLۺ`"9
{M
Ze{D{OOkY֘^~jhgT;z-iwvne!C#Փ<ۥ+Y҅`{{lB>)H+pfZ=-ti{)¬k&s8{`A5@RcgLl`z~Tsk1F"Iddc⫔C唩*OQ sNș]upɣ\02}
Zt0[cI@V}kWZ
<ÌWEPZ[nZ7D BZKJig-l&e۶+6˸+o|JOk\GZdekDt>pHG#lסICg=֞lyB/'@*J?#ju߿'9п3+},-$̗K
{'\61]8+wBENR{Q0|R˒3WSrC]R(9UQ*9'J2dKO] َ?8kd|IֺٯhT7Vex<wv>?/OJ^JԙG87Rr27_ʚ;C^}l渱7 ԃjzVz立֤b2/"  !Y/#y1iI{TEjʣVOLv?dhRwLՈ.onവ3ڠ7wDIpx^}>|π:t ~4 
떋
fD\	|RG6,rp35VYԬn!JQ@+sF]ZnY+1]qjǂtB	.kG9"m5~xS:Uɾ2˪4,hW,8O.vkOZM]JPĐҷC㧹ji`G^U{J*P+e Q  *27+W<ͣ*\qޕI{f9Vx,U\36WeNˆY{l#"kͪ[A+BkEn-blٚ6V=rOoM`Rvv`}Uj
46uc*d39h¢eMi1eVmLB g<Φ0Xr9o]%887s?Fi GSֳUH'֮[[YU4v''y<ҿ\/54Ɓ`53~CsTm/,>cdՍ8HQ7FjȻg9nL/y<K<wZрv6
aXQ[}S,`H=~-ish{*)h,)i)E 8SjxSLB!b?O 
mnv8lV")o{㹩bXȞHс)J~[Gch0Z$bcJfC~<z!}~/I2 6U:Jm"<߻-ʐG'{_kwַ;PѶ㸨ԥ+Z	ﴋlٚ0BO<9dsOD}z61̲֞Dܿ)>~1*:
?Q`i4!~F;tw&"0ƈK ҭڴ=0c2M:%Yy
g[2dRF9VOh/iMm(xVmBh#'%ƒ$n
~MEmQ\''Nk[H>k"OHOjvtRɀ4\p#xue08ϡ(碑Q$hI6vS匀nŴ60>q3޻vYT*{ָi-ao;zrѕدq0)ai-6A}wya-vE͎ޑzRTك
i
6|f?[cNϋT"BmT0R!;q^jyi˱cVF pzSdJ\NGlYI# &Ij"̈ v 0i'rT}dW8>Աݕ$K3>0>-)#\dSEv pyaIOZ<Q'#r~yBHzx(@R5,Qi8Ry ?jMM:ñG қJJx4x{dFO]P @9ȋ}G<G{(~ozyTm8M2$MTjVO~*(z۝N 7^2ݔTVO N7I/
zdP'F1w4sPH2(5
ZJ(h ( )CKHzPF
%/j)A8&Gҟ4&
QL<S"*8=OQڞFFvV"(nym]H&hqK֞蝙
;j=srjJ]۫>ќbv(g&R;qI kqQ
ðiD:ajU;zWä.ZT#Þأ96
"ۮV/,!1,H.5[ǿJ|̞D]I{~L8Q*x_	cHvƊ11Y C,Mcg'}\ya7LЃX&<ry󐑎* h)/&)	7ސ44(7K@
84ƣɣZfi}h2r{ iwǥ `Ի!j \{P'ޔڋ~cړyM #)Jf*8,`ObRiEw emr'	']&;ն*9S`Դ妞yh,9^:;Bx1S/9[ncYŇN85"ڱ66R[GJ_p; s:E5]Ef(n&BÜ˗LDt飻.dKh1-)~?w<U8$(K {BXԓ|z`1:F.
#`UO3Ķyw0:+Q 4
nuX&E`=+l< enMЙ<anw99fGT7Y;U_Y4HՋ ArzE9F׾zMf3Bcc=<
q~J$n=xuvgRgq~Q+X쭺?̌=3S
e;@DncگW^Vsq"D۹###n+;@Oj7OO~Vbvy'֤-|azvWAINͶŬduFWXn @ kIƝK֖Ć1T$
y <T-T+.mVFova{8caɋ})FWES ¾/,C
P{Ҹ@8'?Q)i$
$Y
!G6in?XI\'2$csMp;+GG/}Ʀv mG^lFCkGE-m]AOʰo2wrIIN(ӣG"6{a3;L\ װ7W;'%_>@b'ŸY#լ(a ,oOuw1E'&Tw"`H67
 
Wٯ>돭t77Zzz[\:,zry*WNYXc2Y\sT|MhבZ.nf2#[ c=q/߸Zdp;B7	=~Q\j7/)$qpdqX\Zn53m%r2ߥ7V}%݂@

'|- 欌(а`Y7udf\UGYz>4KiZG4B'xZV=?N+|VG_ƳDe.fHe+'֯F	m~Y]B/`9cFJOK"lхc9&v	$9=皴iM;MGƂFm2[kv¥yr	C}5ke*# A=8%PY_8㧽#FbsӐGCN.gn5)KrAyq	X bc6O,UrfV,6^1>WzvRjvZ/"G!`1GM1hkV')k9&tIjk׷h0A$]aP\<8gXM3$~}*ͲIuFY:G2hORf`H$(^qޡr䎊h`ǽ*}?*KIծ#i"rm'Z{12zU9//m
e&qsFsZu^V+"Z{×C{**=pȮmxy	ui8~u&Z+);GpA|Q;U|-֓iȟcz,Fy{hP3>p7G7ӑj!i3r)JBwͪ9a[x~kn*X+wr~V~WWM/$v|UbI'UAYR/mMA1Z7}IoOP
z
Ԩ{Tk?w >QÞ&BxȫQ[5mXOJ-jRBTO5^v`F{Vdg03P5,Q\W2gǮ+<5?"CE!bNxUW-	[/39`+qpJ:r{{	$e,daxYi?LbI+Dʹm1V֫i-.n	Y[*:()܇-iA r2vKOdSifS, 566hM={Tsj"mYH\7 ;T48Ԓ++HhF&s`'TEw#8l\5蹷+mfHF'J/̚|4.ˁwcvx	;;l\[/ڕ^9_d8ڪ_噊p1۶V}iݶ"meZp]rhT8SM[VvsV9cNI|9(@deeޘV0T7'[Y!_)wlbw5uZism:c+dguqb@zhвq̖?SH9#.n"p-֥DzyqJG+;
"$'rT8><ұNzlrz|9f Z^!cEڣpoV`Eg-艆:فDq-B[DxG`\W^zҮrP>G":cEX,֗pxȨndpܞ{`H(R~_ZVV4Q8PI#xҀKP'*A<E	+q9<7S<Sv2WH=,fm㹽J8mܨt_1R
q-A!BzPg$QVcʌ+3ǵW=T RzE-)T:g0xGIOAeb@т0=iBQw=X
{!'45[|rcJp
 f۾dEcrwg[4%4>^Ei994>3ҥ#G>))j
( )i(BIE F5%9zeIH)i(b҃MO^Jzh=x<H>eVG6;^5!M cT1
RdI
?QL֚?Jr$RC3hM R&5%SbsҜZ_4:B('҃֓vb㜚^)O (zSv҃hH#1ߩ%)TH I֢iAQ$IbYd
{S;Sbwt v
Fii6JQѩ6pS(*Z(1YHPXH({u^M*00F	LԡqP ׊P.R*c 5*v;SDT8S,}j5(<^pT!꒜u<SI̠
<8+yh~,9xmѲڱia5%m
T55 Jt7u4mNgY%TP|a}sg Ӝu#XVZ\$cz#s%N.7KSF&]7ۈ8Xkɪivs+Zof>`G\}*]_֒:]JK[˻9)
JȇT1BXb+Hy% R]	鋾7aTv4뤂eĬ՘y]wkFkK- +6䓎Mco>"ff?SLnX]hn`=WC]"H- /̐^=[Oxgz7]@z51vV3vor.FқyG$
|q4S}if*r` 7p ^،wO%\2LZy? Oơo<1"_
DIs>R<QIEEPN /wC=+^ lG5ݴoiT6߮iRgR2ǵ.?Sq!=*U!{3 3Si*ɨ!`GtO5oO?hhYAR:ZݯBA=y*8a6+:&`l4
l>늖){ȡ%~TTH6{Tr$JѸ+"6wT+MKqL `d RmHI#>߅BѰ+(9xxoT 
e0hv#1=[?ҡ5kʎ,+_~MYoݔ]\) AKkvNi[Tʠ'8W5KmGK]<}3
/8Gӵ);:ǜTOUjJyV3#m@IgW*jc}:EO.Z5y`X.dZVIAϚ=iݷ5+D#(#>L=JK2U@1HF3αOSHl`7Y=zZJ
GQOvjT	OG.WF=*9LScP>Yl4+wݦ-kr%\՘=)
R_ѷ|VDSdդ=ժ!jGͽ69WSE϶ͻ a֔.V`:ULKT&^TtoC
+IHxe'QZYMs#7(Iz{Vs"7F0=>Qj6~
Bxssαuhj:=4Ǻ'dt\1V
(9_֒(.CR%I}h&Q{+[I6.3q4k>YC{Ԛ^6=xачMm@8ۄ{cwM`U
]Gs[֍'ܫlw$ecIOu =+\ILH ~i7R)W8Ea~γ.m'Xg㕀!XrAnX
:G2I3$r{TLE,~lM&xQ
-Aښ:4:'Imp!owvcl۔U@xQެĹݜ$􏀋5*$[9\pi},$yl8
Jxx޴qf$zSĎ	
EjŹY9ϥ ˗ZƄ"ީ$fl
9d@a*ޑM]s
RpCȥYPp?Mؒ{h-\aiX Ii[$7Gj{|m<|/ه9)ɀG䥎?58 TnxO[6yjɎ?~%I֕E4\Ѵ̈́@$znFz6Z Mo❰QQ[#6*j~4R1)h"ƢSMW+ӚwJhr
.}EY "aSQQ&z14lҸJ93 ةhC
r9U6*LJHZvB!6dtnjBtUTMϐ*dQ>#ޡ;=INsSؔ[	/kJX)f&@
zbC@֛݁'H'-M#@HHj,}M	f	zѰRњ&KzQE QE -"v;PfM>}i*AE\j TLzT⒔*$p{bjUDzC
.r9 w@lq@XEHniuI<ՕM;))i156)Bm1?ʫ$c6*)q$#"VuW%qVn:ִOo-C5RHl y )ڡ\ZJ>GOV	n>0RR7XR淒SrRQZռGm\G?E6$d#S%NOC5
@}\=ƚIu0E=`FF,@X=?3CD4S[?Յ䀑(s lUħ#9ֹ.	%u$-KtJzaMsO ^b˱@D֧Ӭd%aƾink"&`0>p?U;]bְ%:7V/"cip"dz
.1E"QEQ@;Y?SsJ??@%F+ү-M.;Xg3Ϯ,ݭv)X7bSe$<Ȫm=Rh%Ftx*&4@aտzfCAK.c Y#*2
p?:>X^y@jOS7R9nH rEhu"2b+ׯ8ڰ ΔA$ ;qRjm".S\*g N?d[ɱՖEPiAQ[_ūnp8>7'. M3)~SW&ѥt2EL',U?*hJňc0GNgƕpΠ`D\vbPsu[V/J4|Wp2:2̪_@~R5vE^ Z}v+"f* $H#}qhgު撜c˨^-_y<=}*ZeV2	%q{CޛwZ[Sz{t	9;nrNIZN d3!0	ƀۻ}ڤFOd'%;.	8M,cpá<Db7QґeW5B#F0Ju	 xQ8fO_jeqEb9:XNVFިya63è7WS	=9#
&	^.YYOϻbܸ
A[O`8jƉ4	/
CV-I0P[[lR `<IAgRHR20!5?<E ~E"Ty-*2;)=	oavl&p {9%C`1Xby&4Ċb\}+R夳Ƈ\dIS2waְ$vVYIڵKXP}+>ZEhJ(ś` tS Oi
A?zҐuC5,r?CR~TPT`ކ*8Gң3) |_jț4Rⓡ\zsAR 恁>nqNR[jQFNO4rr/AHNM1N):8psDb⠫.>H~\AJ$aэ6 9sJv%c:JZ( )E%- QE QE0m֥14Z(0J ZGZ
L)۳ޡ/M.Ʈ1Ip#6F3MEMb@ǽ<KӸXfqJXHAC⋊Šҙ5G^iz]f()|M/=h=E=Ig~_F.4@KAjHRNw*/;R(7iq
9Kf#GDx5#K#ucQZE SE*?M	RQTHRREPKJ(i/j  IN~iejUjR;Bc:T~jҙЎRG&Ӄҡ-!I⋅7<T|UtȳDy#4z:tRJaD HL2q{SQ
)VY!G歶$A"4+
&T8=EG(j~7mq6 RY"*@*ÑQ7d'#c
٠)#8UWh哟a si#Hȶ7BcpXt+0 c}jt+^ƶ̌jrO<%@ʯ;CrnșBhc^~o?Zo:'EsQOUZw+iKX֭z]$af'A~S ON*I;Rʜ *7hkR# 4yoOkQ=(=[ pOdk(=[ tᴹEH碢h72//t-I/ZEaׂ
涅qD,.O3Qewi5Ŵ@Ԍ\uؔ\g9xQ%Em)Ծ,K]֣
.@ǽs9ܠzV6mdJ,sѧ&orٲbEO"-K?NzmWm<UaG6c9$'z]
2]D7
)R	
/z CC	

zԤi$*-&q2 pLrp}OAK/˓򦘜oʤQ~{5XX2VEkjdz` hqʊB'ef? 5ʦIc sx=6#FͿ j<D*Ih뚍ʲ}LQa\UI5?ڣQpdjȯFjbG!(9SqK s\qҐry'&zxi
("E";NZT!%]֣J"C8vTCFpjޫoE@!-rԖy|WXTI9R)G3FufVK\׉FGZ>CgڢGi zm=Q6/;t
`wH})1a4f葲VS&
c~G t;UmCMK	*.=@i3['v +DZD1<*КM+vc6oK]P'-,`sYOq!w=aaUZJV݅%}h4
((J(E 	?Se \Z1Ǹ:wH+[F}VZ9>F،[K.O|QC&DV9!.~E,m1>)C F
T0k
E@8lsќi>֦g/Y#
JLuS A4T#⁁$y=)v>
NOOo_梊3+zҤx3Aw>yЁbX4E%2ZJ 
%P36QE QE - QE S^Mz!)M%"(u%Q;OFX3EERRR@
NZe%aK81q@F3FvF` RE?1z5zӈ<!ۊh) +}(*HE:ԑ42^ZEE%-J(i(h(WmHTP1h% RQ@Fi(zJ:P+O.J^b479
jW"T㨬)69J]pk
Oߥ:FSJerMu|¯fZt_ʛmH=Jmh~ƿj("_4wFP.+;{nGc8qCWCNqSAS# MfX
;ʔ"HĂ0*E1Z t~T1
)B8(`/OAh͵FOy+3@&2%c*  gwLиAI#HRJ}Ԧv1LcڶҾ@xf괕ѤloN?償ɦd;]O\QfAr_YPĺhŤ84	4/A]3Ud`**MLw#:U|­fG!i 
ST`i,6Y;O)ۣͧqp~TQ@})Si*HPZ4 F=ih3L.Rt~TRgZa4XWE!?^z
jK)<?Znr*2ޙt;2r:<C)\|G޵\,K淭WGFi\,L.$ORg3OeMY4]*4]]M5A֨g4Usyl=SFCTiF^9kr6jW *Z񔏛JH6y|-bLIT Wu|n<Aգ7
_,{U;Xl5#)
Z7iF<U"QMh_4pЇ_R䍸V`Q>٭ݡr(c[ߕ:O"#яU	0*F,;9('UR {0OEa&18̘ztc4\O*EesQԚg(k-R{nP^&8rt-}L݌/j:dUOJ+OO9| .n	VB:w-O	3QQ3yzT d=lֆNďB3H*>5z0\Uk9;dm"絆	[9ǰL}ғHjѹ#jLLzilaڐh(@H9juueOF bBhJ\V]$GOQSpEme?J7 UJmf<aN{f#j.4􅝰:wn<I2M;N>U.#S=? U((Pi( 4PhE&hdl-> Sr(ȣ4њ.̚9acM惚WQE QE R@	EPKIK@Q@Q@Q@Q@ %(8	iޔP1QRTchBjJ8- &)N}/zJ*-Q@ZJ(l.*JOIqQEIaEPEPEPEPEPE-% (4 VPx+j+P?U=krp7Wmt
 Vv` J#=uRr@h㠓I#4aj@A\Ӕ#pA$sMm[CgRUjŧr"`L<pI#^)#zC)PF
%V\(zjO1QtgҢf p4wp>|>cLyd#XPy'	%	/BjuR!֦EDrrS!1	n;RuT|4 y8_ңv%~;6rx@$ۑJaj~Nj8\@K lSS$.i0*>}LCM*N=w
2iPz@Ӛ Ǹ@棞Q
z4i~\(T袳4
(
(( ( PKIK@h SiA	RVMnzd8ְ:Ӕ`T*+(o-mݏzvqyLN~Vi{Me854 $t5i&Y{Jg/y-$M1 סD4SLF8Էwb5 6H."UV#]
F;xnYŠlc=k̭:ѨBi	9k}$K)}kY-XmmN{#+A
Pn,9:C!1&>uBp2*Y[P(%)2(A)
)ݩ3 iz1R!@E Ԓ#ԂO{Ao	RP~2QOaM1/;rP] ?xhc}
&^AhbF=IeΟ&S
>d'N啤*OAҢ Ȫy?Z_z>%	~#t?":*M8RSM 4LLњBE3rM7Z8P+1KE &(1-%Z)(EPR@Q@Q@Q@Q@995& &4F:ԟ0%!GU%0=((?vPҧSIJM1E%-1-%Z;E QE
'5b&RJJ((( ( ( QE- QI@EPFqE&idu#r_6,2lt4r>[Ȼ>Vfֶ'd'֤و0¡ئI"85oR1LEn*o<J犔 c dZ?&fSӵB\V{
sM'&1SqIy<TOUx֕ʱu

"((rzzU.ϟ8?1&3c-I3hpq3@MDCÞ\,J.JVN9W<uH1'ڞ]z)Tzb&iK\K!+)}/H<hcHzicԄ㸤ϸ40E'SwBcJZbJjJbjۑH֚jlfv1rqUi	.j y&EDJ)i*J
(
ZJ( ( ( ( (h)(<TlhMCEt?jQp>a\Rcq޴L7N7q	$cY4jěHQڴFLlz̳(8b`0\vG=vm	W_)-H8v
4sYS@''402DmObsު27;cCN]R `P Q4q	1> c@X/(
2C0*x4x
{_<GۏdZoy$7:SȯvȪPPqS1m
=*qW`I$8Ӏܚ!8Ԟ$v(,M=oHd~Ih"
HI= 8h+)<R?5* zTFJw\5KS##TF#֐GC;yQ[lc?Y^SzP:QX:n y|/|ڹȯ ɤ\zu(O3
Ǔ&fE%-QE 
(Q@jZJZ (Eb4(0H6**]ƀW駊94
\J0
+ mi RPE
(
(uiI #]ғu!jRv4%0L@Xq?- 4
`Gzxj> _ƊNPKޒ`-A/ߩQK֓kr:(
Z)(i(( JZ ;6PyW^azRejІ,2e
?5IaUl߃V"2Z'Vi";bLS'i>m'W#gCɹwI1cYwJ-_,2{RAʑO";2W?J*WzUqCV4NEܤgQ֭I>X;{!ErhҜGJg֋ qM<;QJLJ(\FI/SHW Ӌiؗ"z|vIsE5'MA@&g\zq5ґyiP.8fJOz!ؓڐIb3TB6TB^PQE QE QE QE QAEu((%Vȥj5<%kO sC;F9UehuL/ҵXЉ!l,y5z"bq`A<_09Oܲ 	yA[څm.Y9ڰ;
ͫ3D)YKU#;P
E]Hat8eހ~zri	E/֔4 cFP1JXQq؛4?14A( 4@4  8W&*qIoi$ap ǵGgqV*#W'{{o	$Z 8$qh	܀GM8##v槷+\>Zr-fPC
MQ$M^aǔqީ`pRݙd	m#"uӥZ1kT6:X5Waj%1?Lp}+H7*zLJ]52/Ԭ)E%QސQޘQ@Q@PhN41E!4f3II@E% (<N .)( %- QK@.
J3@ I(L@Eb
( N:өҝLLLҏIJ>ES(((Q2
IH @W*K
(QE ((h
(J(h j<xES$SOQ4Zc>AđU{kOG!@ w/ZtRmp
UGUqX'#4P
VY7D=jBDCHpsy8Ep [pm؎[T؍"5MAhZYz**M%R*\v'gGU|QEő}Z3EbySKi
4* 4k z+%hFZ<t;1mI)kz
<(zU9^4.?S hNڦazU<v.tM,urij_CGT4&#[Z3
U<RˈQE!袀
(
(E QE QE QE QE QGz Z(u<t
W?9jT24ajbYֱZVKV
ҫ1f{AkPn9y_tyTTbҒ4;z
\gՉUi0@83Sl)^qT֐TюjK`#:TC%w{P!OQLP*^Tu F;t>ƗpI@>LC.	M.@qڌ @0F
 -R01S[˰5(f1ҫ\2{ZelPsNp^jN3Q)RfRE QE f( ( KI@
=ih"P0( 4fKHNh)ݩ3E RRE RR )QE PE NJu2XQTRw ( Z))h 
;A@0mI(5IH(EPE QK@	KIE QE RPEP&-*YnyT Gd<S	zu5E Za|qNcFpOX3+du|}*pqN*)Y~k<hZI\r8Tr6'X2>=
yDu(SH2ր4y$.sR?@=M9.U<Sj6[Ԟ[vf,+67i5rQ`)cڊ*01EUJdIv*&?ySy(ϵsԟeC`)њD4Oʋ:(抴,c/#X
g8JM1QE
(
(
(
(
(
(
(
(
()4"EKK*,xjm? ߊjKȀOsZʰ9l.+KXM5GXU#M
̧Q-tNK.}i,d^%KgZFqM8Px`+5BbI8Ejʳ\qA@5eiQ4bs!1g=c-RIf֜ ▂%ڿuFO'98i1Q@z.QݩcH)iS3=)i{2s ;ƌMh{3d7Aϥ.)Ϩ ^)Oh M P1
SL)ǽOΣV(bNhXm#
(QސQ@Q@R@&i(ъJ PisMъ ZZJP8b )i( )i)h  b;Q@RҟLNHL((}(QE  ZCE @ēIS&(RI@EPRRIE QE QGj( Z -%(	On*IkUHjfzT!D<
)6a	LEiZ $jU@ޘ+׊fMK/jjJlcN%Q'
Ě<v@<Tw.iw/{S.top)Ҁ+/Z:UeVGJHlZ(tS$)i)h g9nEVa WU?pRCĔ$JVmM.OSɦHP J^9jd ELlѿj~;V@:_gq95,	GER4
(
(
(
(
(
(
(
(
(
Q֒uӔJgZ]8q3M[sbchAb2w,Ci mfؐ!TI,DvVrV7@m,GN+f5$S횦-c>.R;
]SWEc9`tZV>dfpRv#
hv(B4neE44r!҂Ϋ3R=V?*:Sdgi s1Sz<dLު~PsN5"ۨiWDYf*@8XW*{=3	>Ү
c@'A%J)  SwP2L

ژEER((@QGz`QE QE ө(aF)h ( (1( Z( J)h PE-%
LR@bSy4%!RfڊL@IE> Fh#ހҠn	 bLhmQHbE QE% QE QE QA
JZJ )E%IޖW8ifʒ H`)b^.+Aa:(a>Q,0#TKCaN%>c7)!ʂh2JHHw'ښ֏qG!jȪíZ) aES$)i;@POMPkr*Uj?$9lrU}MIQ)oNITK)	$At͞j{F%A=LrXiK`8`TUw
X`0Ȩi2(aEPEPEPEPEPEPEPEPEPEPg#4 n9ia[$t4qԀN
 .7,08V{n#+u "Ur;ҍNEE֪HϕCUPyz
Tj%>F9$"XEgr[[FELQV~qF!8U]HၥYATq"ljp4yeZwDrMLf`G4a^hN4wqF)Կ 3b Qڟj)Ji^7>)Xw+B:ղ=6ҰTԙϥ4ŞaW<BLal)Xwb1QE!-%- 
J^( ( )
- QZ)LQKE &(
(\PQZ(PbZ(  LR1 'z1N&);bb
{Qөhivu/&]֊ZbF- c/E RRZJZ *GRSu0DtQE"% Q@Q@Q@PA( (ԆԆPE QE  E <J(r=h~
@j$SD:;/J*
5R4é^0߅9S>f9zHhu>XrjС
(QE '¦gr.:" u5Xx֒)"@)Faޜ6("TQ.*QA,,<SE\_?Zq(ԞttQEIQE QE QGz( (  ( ( ( ( ( pa8qQ
t|092E$xi^@TNiJ@NhA4cҘ4rj:(@A^E5SR'S$ЃQaUJ,4tfCSa܋41McՈ<Tu"9^;X23Yةisک2E1FsKV@(:Sd}ZVv5-بb7Zr!i*ܑ֦IUW-4<F)T3Ev(DnZc\
.)QTȮ)hǪ(RQYES ( ( ( )i b( E-% QE b JZ(((;EJ)hBQKEQEQE QK@Q@ES ) QEZ)(*Jdv(AEPEPKIK@Q@Q@Q@	KE QE -()(((@Q@O	{Tb!!1czqf;ƟTH9]`e');7֐ȗZUZڄZ(!E Tjǯhh1fI[RJuQӇZozQ@SޤbK5Sf%D?D[j  {VIT5R(6
(
(
(
(
(
(
(
ZJ( ( (E)H){P!2zQE(3O c$x.4!ҚzSH:PPpR%5Ӫ99u^i1QpE SJS4ZE
SjI~2 ڲB5JJ&jҐRVd~)ip<aQ49XY**faڡ[{"fZe.E7~E3bR Lǵ.(h ( ( ( v( ( EPv@QE Qڊ ( (EJZJZ ( )hE QE
(((
ZNԴ QE QE( 8( )E+QJF	
(( EPEPEPKIE - Q@PEPE%- RRA QE U ˊh7ZE>a)ژBoOJr
 j9UP9Cll@ɨyGqQj=z.>0ry4  r/G? S3I܊~f/(C%:KT@\i2TvhpU$wv9Z?+VnOҔ=ʴQEIQE QE% -Q@Q@Q@Q@Q@Q@Q@vRm)@	ڗ%- 
Z;Ҟ -H)✽)2ʏQQzRf/c,i}袀+~zm:_ڒi
Z4$L1R\jКnu %qHF(h\괾dmީO\YQdN޴ӌl0O4
GcO;ӾƞԐZN Piv=gASHzUbiދm-%/z((((((
;QE 
(
(
(
(
?)iQE QE QE %( Z))x(%- QK@RPIKL(@v
(E GZSY}h(eqIH( ( ( PEPEPEPKIK@j(
(
)F3I@z(
($|٩%:%F)q=E:|S Oӏ4E6Cހ"^gYI>SNaZq֘Q҃E -A75C71:XUՊH$H)iT@M@ُqV
UUǲ֬&;5} Zy &/D7+QEEPIKE QE QE QI@EPEPEPEPEPJi(=()Ԕq@-% )B@gzzBe8)&d'Az}a`z0)%J (@Wm+IRYe~袁ED#)?,@
aNl.; hfp(TR*\SGHy~-XW#hjJ(\aM>6RPnpWԔ>(EPE QK@	E- QE QE 
(
(
(Z ( (`-(( K@	KE QE RE QE (
(
(Q@Q@RP0e*R*j:+SjC`PQKI@Q@IE QE RQH	Rzar:cCiN	[
3PSh
(
P2@>j (ϽQMnH_ΔH&ڸ=cH+<RV+*\X`{4 `~POP?"+<RcDuf/*N[HPz&6d9Q2ǠZW#<(*!,r[֋Թ3~"2Zeyw邯U`y)^5
ȡꉋRUo#dj-ctQE( ( ( ( ( ( ( ( ( )OJJSҀ)h(^
 \OOH"&\ JCLÏS5d%-'z (@%Qځ[Z4/%`:揜v?H$1h5bNޜb
cA
2AP$;hv (JRPE}IC}EIC袊b
(K@Q@Q@QPQKHi v( ( (i)h()QE QE RPKE(E QE QEh(4(4PIK (ޒ (( i>6QE%@	KE% Q@ɢh ϭ(AޝHhl҅?4Qqޚ)ϭaQ@ Zr m(b(O,zkLhh2R  w]Č2)1BP!8UCm(#z}2B[nސX}C/E!PƆȪTCRBp8 cҗ4E1a #CRE9Ʉj{
Sjx5DjDmH9Fq=4i2E?CҩW%y9d+.0 aIt 4Q)QE QE QE QE QE QE QE QE QE PKIK@	EP 
'j\C T?)2cʝJǨ4J-j@<h(Pz) */Ieb;TdҪc$h=M>ABR0ʑKE 23S+ObQE RR@	IKA%)IRQ%QLAKIE -Q@Q@((bu( ) QE RE QE QE0
(ԿPKE Q@(ڀԴq@E%-
(E% QE RQ@E% J(h
(
( RQ d28#iҐ)vLJQI@)(PS dџz
&h 4f PhZ ( ( ( Z)2(Ƞ"(GZVRqRp(b@
	y*,҆"֌ri0(904t 	}hooZ_0e)D;΢Ȝ\iE^.Õ`T[<~UFFEE((JZ (PE QE u( QE )E PzԱQ,|SBe3E5c@AHKR*4-%0_:'@V2ԔI`i􌻇^{U*Q-1'kpE8(Rq@~5?#E"6WEPQKI@4R7C@(( QE QE;QE(4Q@Q@%/z) QE QE( (
(
)hAE- u((4PQA QI@E% QE QE QE 袊QFhQGj( (  (E(fii( MZMԀlh
JQ@As@@ĤQ@
4 QE QE Phh<PEPEPO=)ƀ)ؤ&)qKE0=i tҊ3`%-0iqE 'R{RbP!pM7PKO+M.M0_)E'n4n4
D(>ƀfր1( ( ( JZ1E QK@	E- (
O@M% Q@Q@pT05➤Tݎ✱bU_SNBdؓF&CAsL,QAKfMG1)0Dj:jQL(Q#]r284ncۆE-
JZ()vOcO8BQE S[u52
(DQE
(EPEPEP (QE QE QE(`Q@袀JZP@(IKHi Rq@Q QE RREPR( IE -PIE Qފ (4 QE(4QFi RZ	
(ZNnԔ;RP&)ih ( )M8)(PO ce86()r)rgNԿ-: 'RHE(IK 3ڜ) -QLBR)ƘO4 P)ؤ1Fu-%.(Em5=;16PTzRsѶlW+IV*CրNa}QKԔ( Z8 ))h@(4t=(\JoCRh*=i4dGJaN6KE Qޒ%.21LA#}i(Ppx4%&YuT"NW4+)覬=EĐSC54=
lf!E'zZ gcO#c褣< ( 8%iX7NbQE >>(Q%QLAEPIK@Q@v
ZJ( ( ( ( TQK@E
((
\RtR@((HbQE QE QE QE QE wJ ((tR@	GzkS)2(Ȩ,IFQ@?ppQҀ4Z RsIE QE 4dњJ \94 QIE /j(
(
(4RQ@Sږ֝@4Hh1@ħ
 (@cMxJ)-ޒKIK@
QMHNS4 Bi)sL"uJ4֤4A^8cVMFO5)J4G"O Ttޒ-Pӓ6.1@+M+Rϥ1\bIq4GH<tҞQE P׹S|摻\b uB֚~0GQOGP͞1@u @))NOjN Tt5(,8Й`T;hzqXb"@cpwƝGZ dQޛv`L {.i@RB7)6h-^!>==ip ƆQEIEP )RREPEt ( ZJ)h)h
(
(
Z(-%.( Zbz( Rb mPIKE!Q@Q@( J)M QG@	E- %4P1(4PќR
cHc7=&?ҝږ#ҏ¤.0O )M QE (
(.m(8@J\@Q@m %Q@
)iih bE @%-S E 4LSE KE)i)hh--%u(斘fLQasKnh ;44␟~S@84"	$E ( ) ʒ'liARQެF0i!V)
 +HDqL zQbj8Uz֨Z(4 H=1@7PӨ:qQ7Ƞ4r9@zP -Fy?4Fi( GN&#rIbP!h4 QILiȥJ r)I/NJ(4:}G'Z mQHchQL(
( QE R@Q@Q@()h (h ^QE
Z(E@ZOKE %'zZ((
((RE 
JZJ ( RRހR@
"I@
"Ț2MHV4p4K@( 'u bZ\NPъ fi)})( J0i(LE<hbZ)R@	KE QKE(aIKE %Q@ QE QE RR RR K@  	L}4)"q(zWR 3FM;3Fiv<RPEP h )A*IA۔j\#If4i\)BizaҤ{SI(ԛj0pr)Bvh0RR SM#(o}I 4iLsE.L (I@3E% :SiAC<`KEGp`h)3FE -܊7
:@Թ P"2HH{RR` w(%RREPKIK@Q@Q@-% RR (QE RR (h-%Z(
((4QE QE QEQ@Q@Q@vQ@%.i
 JhcqIuJZ)	"})ha@ӂ4@Nn))أJZLQ@4^f)MR 2QJ˷h<P2nAKL( Q@%- R@	IKE %PQKE %
JZ()MP0^( Z))hR3m@!S;ө)?=XvE-;r94a܊qB:SqHaE Q@E
(	*5 {U(;⋛ϽS-E]lGw433.
:

%"44P?(y ݩPi`4RF1٢K!h<jLb@Қ 
i)s@
&(fh4Fi3F(Ih sKEw1l釭 QEKIE(EPEPIK@Q@Q@-PEPKIK@Ɗ( ( t)i((i((QE QE( ( )h(E RRPHii) Pi
 Rf<[)M ((ZH?
%P1("P!(RsOX+M94H͓E2OZ9
Rh"˚u6?OE(@S
	E-	)qGH4wQKIH@	GzZ1@	K()h(KI@4O7&r
 dڐpiIRisLsIJB@=)^Hh))qKt@

	I( ^RR R>m> 4m>`P3G>> Q@qE b E-1O4b
1E% QFi RQ@ie֝A֝ր R@B3E.( Q )ihf(g4b\!1M

))hԴzZJ(h`QE w
(
(((AKIK@Q@Q@-'- i(EZJ(JRPEPEP  JZ)(h𢁉Қ(
(Z(SMII@Fiԥj6JV9N@Id)#
=j7Tc
%-% %-R ( )QKI@	Ab4Li1Er
N8KEZ)iJZ(ZJ (PRSGj J(4PQK1@	LS(;ъ\Q@	E.(@	E.(BQKF(RP 7SO4Hhm(EI4#4٤4z3H ubE `PK|6)#0QTnO+ciA4fȣ58O<%٣49VHǊJ
%0!4 zњ3@iK@@PތQ)M'm ('֓4PEE QE I@	J:QF(sKis@Fi(( (
