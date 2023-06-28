# Developing Flowmapper

## Overview

Flowmapper takes in .dot (Graphviz) files as input and generates a static site that provides interactive architecture diagrams. The code is released as an npm package. The end user typically would point the package to a list of flow files that would then generate a static site that can be run locally or hosted on Github Pages for example.

## Prerequisites and Dependencies

- Node.js >= 20
- npm

## Project Setup

1. Clone the repository 
2. Run `npm install` to install dependencies  

## Development and Build Process

1. Run `npm run dev` to build and start a dev server  
2. The app will be running at http://localhost:3000
3. Run `npm run build` to build a static site with sample data provided in `statics/data`
4. Once the build is complete, `cd build` and `npx serve` to run a local static site to interact with the diagrams

## Code Organization and Conventions  

- The source code is located in `src/`.  
- We use [purify-ts](#) to handle nullable values and option types in TypeScript and Svelte.
  - Maybe is used for nullable values 
  - Either is used for either/or types that can be Left or Right
- All code is formatted with [Prettier](https://prettier.io/) and linting is done with [ESLint](https://eslint.org/).  
- Svelte components are located in `src/routes/` and `src/components/`.   
- All API call logic is located in `src/lib/`.   
- Application state is managed using [Svelte/Stores](https://svelte.dev/tutorial/writable-stores).   
- We follow the [Feature-branch Git workflow](https://www.atlassian.com/git/tutorials/comparing-workflows/feature-branch-workflow) for version control.  
- Integration tests use Playwright and are located in `./tests`.
- Unit tests use [vitest](#) and are generally colocated in the `./src` directory.
- Utility logic and constants are located in `src/utils/`.  
- Translations are located in `src/i18n/`. We use `i18n-svelte` and  `i18n-util` for localization.

## Internal Architecture

Read this page for a deep-dive into how Flowmapper works.

## Error Handling Approach

Error handling is done mostly using [purify-ts](#) with Maybe and Either monads

## Contribution Guidelines

- We use semantic versioning (automatically versioned by Github actions) 
- Hence we need to follow the [angular](#) commit conventions when creating PRs (using feat, fix, chore etc for PR titles)
