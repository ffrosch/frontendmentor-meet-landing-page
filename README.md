# Frontend Mentor - Meet landing page solution

This is a solution to the [Meet landing page challenge on Frontend Mentor](https://www.frontendmentor.io/challenges/meet-landing-page-rbTDS6OUR). Frontend Mentor challenges help you improve your coding skills by building realistic projects. 

## Table of contents

- [Overview](#overview)
  - [The challenge](#the-challenge)
  - [Screenshot](#screenshot)
  - [Links](#links)
- [My process](#my-process)
  - [Built with](#built-with)
  - [What I learned](#what-i-learned)
- [Author](#author)
- [Acknowledgments](#acknowledgments)

**Note: Delete this note and update the table of contents based on what sections you keep.**

## Overview

### The challenge

Users should be able to:

- View the optimal layout depending on their device's screen size
- See hover states for interactive elements

### Screenshot


![Screenshot of the four card feature section on Desktop](./screenshot_desktop.png)

![Screenshot of the four card feature section on Mobile](./screenshot_mobile.png)

### Links

- [Github Repository](https://github.com/ffrosch/frontendmentor-testimonials-grid-section)
- [Live URL](https://ffrosch.github.io/frontendmentor-testimonials-grid-section/)

## My process

### Initial setup

Install dependencies (make sure you are already in your project folder!)

```shell
bun create vite . --template vue-ts
# Typescript must be a peer dependency to enable
# import and usage of types in Vue defineProps function
bun remove typescript && bun add --peer typescript
bun add tailwindcss
bun add -d @tailwindcss/vite @vue/tsconfig
bun install
```

Modify `"scripts"` in `package.json` to look like this

```json
{
  "scripts": {
    "dev": "bunx --bun vite",
    "build": "vue-tsc -b && bunx --bun vite build",
    "preview": "bunx --bun vite preview"
  }
}
```

Adjust `vite.config.js` to this

```ts
import { defineConfig } from "vite";
import vue from "@vitejs/plugin-vue";
import tailwindcss from "@tailwindcss/vite";

// https://vite.dev/config/
export default defineConfig({
  resolve: {
    alias: {
      "@": "/src",
    },
  },
  base: '/<project-name>/',
  plugins: [
    vue(),
    tailwindcss()
  ],
});
```

Add the `@` alias to `tsconfig.app.json`

```json
{
  "compilerOptions": {
    "paths": {
      "@/*": ["./src/*"]
    }
  }
}
```

Add fonts and tailwind as well as your basic theme to `src/style.css`

```css
@import url("https://fonts.googleapis.com/css2?family=Barlow+Semi+Condensed:wght@500;600&display=swap");
@import "tailwindcss";

@theme {
  --color-primary--50: hsl(260, 100%, 95%);
  --color-primary--300: hsl(264, 82%, 80%);
  --color-primary--500: hsl(263, 55%, 52%);

  --color-neutral-white: hsl(0, 0%, 100%);
  --color-neutral-grey-100: hsl(214, 17%, 92%);
  --color-neutral-grey-200: hsl(0, 0%, 81%);
  --color-neutral-grey-400: hsl(224, 10%, 45%);
  --color-neutral-grey-500: hsl(217, 19%, 35%);
  --color-neutral-darkblue: hsl(219, 29%, 14%);
  --color-neutral-black: hsl(0, 0%, 7%);

  --text-xs: 0.8125rem;
  --font-barlow: "Barlow Semi Condensed", sans-serif;
}

body {
  font-size: var(--text-xs);
  font-family: var(--font-barlow);
}

a {
  color: var(--color-blue-400);
  text-decoration: underline;
}

a:hover {
  color: var(--color-blue-500);
  font-weight: var(--font-weight-semibold);
}
```

Create the Github Workflow

```shell
mkdir -p .github/workflows && touch ./.github/workflows/main.yml
```

Paste this into `.github/workflows/main.yml`

```yml
# Simple workflow for deploying static content to GitHub Pages
name: Deploy static content to Pages

on:
  # Runs on pushes targeting the default branch
  push:
    branches: ['main']

  # Allows you to run this workflow manually from the Actions tab
  workflow_dispatch:

# Sets the GITHUB_TOKEN permissions to allow deployment to GitHub Pages
permissions:
  contents: read
  pages: write
  id-token: write

# Allow one concurrent deployment
concurrency:
  group: 'pages'
  cancel-in-progress: true

jobs:
  # Single deploy job since we're just deploying
  deploy:
    environment:
      name: github-pages
      url: ${{ steps.deployment.outputs.page_url }}
    runs-on: ubuntu-latest
    steps:
      - name: Checkout
        uses: actions/checkout@v4
      - name: Set up Bun
        uses: oven-sh/setup-bun@v2
        with:
          bun-version: latest
      - name: Install dependencies
        run: bun install
      - name: Build
        run: bun run build
      - name: Setup Pages
        uses: actions/configure-pages@v5
      - name: Upload artifact
        uses: actions/upload-pages-artifact@v3
        with:
          # Upload dist folder
          path: './dist'
      - name: Deploy to GitHub Pages
        id: deployment
        uses: actions/deploy-pages@v4
```


### Built with

Tech Stack: Bun, Vite, Vue, Typescript, Tailwind

- Mobile-first workflow
- Tailwind custom theme
- CSS Grid
- extended use of CSS custom properties
- [Vue](https://vuejs.org/) - JS library
- [Vite](https://vite.dev/) - Build tool
- [Typescript](https://www.typescriptlang.org/) - Type Safety
- [Tailwind](https://tailwindcss.com/) - CSS framework

### What I learned



## Author

- Website - [florianfrosch.de](https://florianfrosch.de/)
- Frontend Mentor - [@ffrosch](https://www.frontendmentor.io/profile/ffrosch)

## Acknowledgments
