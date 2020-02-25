We typically look out 6 to 12 months, establish a set of themes we want to work towards, and then schedule work each milestone supporting those themes. When planning, we typically look at potential work from three perspectives:

* **Maintainability:** As the resources we can devote to this project is not limitless, to ensure the project’s longevity, we need to make sure the code base is as maintainable as possible. This means sometimes we will have to make hard choices on features.
* **Extensibility:** We cannot implement all the features in the core plugins. There may be widely-needed features that we can’t easily add in the core. But we can make the core extensible enough for the community to implement such features in the user land.
* **Performance:** We need to take account both the developing experience and the end user experience, and performance is a huge part of it. That includes package installation speed, building speed and the bundled web app size.

Legend of annotations:

| Mark | Description |
| ------------- | ------------- |
| bullet | work not started |
| check mark | work completed |
| :runner: | on-going work |
| :muscle: | stretch goal |

## Workflow

* [ ] Migrate the tests to GitHub Actions
	* [ ] Should test against multiple Node.js versions
*  [ ] Add E2E tests that include a package publishing process (to a local npm registry)
*  [ ] :muscle: Gradually migrate the codebase to TypeScript

## CLI

## CLI Service

*  [ ] DevServer: allow lazy compile for multi-page apps, to speed up compilation. [\#5178](https://github.com/vuejs/vue-cli/issues/5178)
*  [ ] Support `vue.config.ts` and `vue.config.mjs` [\#2138](https://github.com/vuejs/vue-cli/issues/2138) [\#4477](https://github.com/vuejs/vue-cli/issues/4477)

## Babel Plugin

* [ ] Use [`@babel/preset-modules`](https://github.com/babel/preset-modules) for modern build [\#4848](https://github.com/vuejs/vue-cli/issues/4848)
* [ ] Investigate the feasibility of transpiling all dependencies in `node_modules` for projects
* [ ] Investigate the feasibility of bundling polyfills to a separate chunk (like the [“differential loading”](https://angular.io/guide/deployment#differential-builds) feature of Angular CLI, may replace the current `polyfillsPlugin` implementation)

## TypeScript Plugin

* [ ] :runner: Support Vue 3
* [ ] Support scaffolding with `@vue/composition-api`
* [ ] :runner: Support Yarn 2

—

[TO BE CONTINUED…]

—

## Major Releases

We also have plan for a new major release sometime in the middle of the year, pending the status of some primary dependencies of the core packages.

At the moment of writing, we plan to ship Vue CLI 5 after the stable release of Webpack 5.

Current planned features of Vue CLI 5 include:

* Webpack 5
* Cypress 4
* Workbox 5
* Drop support of Node.js 8
* Drop support of TSLint