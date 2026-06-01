# vue-yarn-repro

A reproduction of issues relating to `peerDependencies` when using Yarn workspaces.

## PRs & Issues

- https://github.com/vuejs/create-vue/pull/1011
- https://github.com/vuejs/devtools/pull/1097

Also related:

- https://github.com/vuejs/devtools/issues/388

## Steps to reproduce

1. Clone the repo locally.
2. Enable `corepack` if it isn't already enabled. This is needed to use the latest yarn.
3. In the project root directory, run `yarn` to install dependencies.
4. In the `packages/vue-app` directory, run `yarn dev` to see the error with `vite-plugin-vue-devtools`/`@vue/devtools-core` (for https://github.com/vuejs/devtools/pull/1097).
5. In the `packages/vue-app` directory, run `yarn lint:eslint` to see the error with `eslint-plugin-vue`/`vue-eslint-parser` (for https://github.com/vuejs/create-vue/pull/1011).

## How was this repro created?

1. This project was initially created using `yarn init -2`.
2. The `package.json` was then edited to configure Yarn workspaces.
3. A `packages` folder was then added and `yarn create vue@latest` was used to create a Vue project. The linting option was selected to allow the linting error to be reproduced.
