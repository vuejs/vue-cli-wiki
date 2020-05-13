We typically look out 6 to 12 months, establish a set of themes we want to work towards, and then schedule work each milestone supporting those themes. When planning, we typically look at potential work from three perspectives:

* **Maintainability:** As the resources we can devote to this project is not limitless, to ensure the project’s longevity, we need to make sure the codebase is as maintainable as possible. This means sometimes we will have to make hard choices on features.
* **Extensibility:** We cannot implement all the features in the core plugins. There may be widely-needed features that we can’t easily add in the core. But we can make the core extensible enough for the community to implement such features in the user land.
* **Performance:** We need to take account both the developing experience and the end user experience, and performance is a huge part of it. That includes package installation speed, building speed and the bundled web app size.

Legend of annotations:

| Mark | Description |
| ------------- | ------------- |
| bullet | work not started |
| check mark | work completed |
| :runner: | on-going work |
| :muscle: | stretch goal |

## Engineering

* [ ] Migrate the CI to GitHub Actions
	* [ ] Should test against multiple Node.js versions
* [ ] Add E2E tests that include a package publishing process (to a local npm registry)
* [ ] Eliminate circular dependencies in the codebase
* [ ] :muscle: Gradually migrate the codebase to TypeScript

## Vue 3 Support

*  [ ] :runner: Should add a first-class Vue 3 option once things are ready
	* [x] The core logic has been implemented in [https://github.com/vuejs/vue-cli-plugin-vue-next](https://github.com/vuejs/vue-cli-plugin-vue-next)
	* [ ] The progress is tracked at [https://github.com/vuejs/vue-cli-plugin-vue-next/projects/1](https://github.com/vuejs/vue-cli-plugin-vue-next/projects/1)

## Production Usage

* [ ] **babel:** Investigate the feasibility of [transpiling all dependencies](https://gist.github.com/sodatea/0f12a4477512c02cf6e556df02603de8) in `node_modules` for projects
* [ ] **cli:** Support scaffolding projects with a “fallback” lock file so that it won’t fail unexpectedly due to some broken upstream releases

## Development Usage

* [ ] **cli-service:**  (in `serve` command) allow lazy compile for multi-page apps, to speed up compilation. [\#5178](https://github.com/vuejs/vue-cli/issues/5178)
* [ ] **typescript:** Recommend [`vti`](https://github.com/vuejs/vetur/issues/1635) as a standalone type checking utility
* [ ] :muscle: **eslint:** find a way to work around the cache issue [\#3065](https://github.com/vuejs/vue-cli/issues/3065)
* [ ] **cli-service:** consider adding [circular-dependency-plugin](https://github.com/aackerman/circular-dependency-plugin)

## Vue CLI UI

See [https://github.com/vuejs/vue-cli/projects/1](https://github.com/vuejs/vue-cli/projects/1)

## Documentation

TODO

## Keeping Up With the Ecosystem

* [ ] **cli-service:** Support `vue.config.ts` and `vue.config.mjs` [\#2138](https://github.com/vuejs/vue-cli/issues/2138) [\#4477](https://github.com/vuejs/vue-cli/issues/4477) [\#5046](https://github.com/vuejs/vue-cli/issues/5046)
* [ ] **typescript:** Support scaffolding with `@vue/composition-api`
* [ ] :runner: Fully support Yarn 2 [\#5135](https://github.com/vuejs/vue-cli/issues/5135)
* [ ] Get rid of (possible) deprecated packages from dependencies
	* [ ] `request` and `request-promise-native` [\#5220](https://github.com/vuejs/vue-cli/issues/5220)
	* [ ] Upgrade `@hapi/joi` to the latest version
	* [ ] Remove `core-js` v2 dependency [\#5125](https://github.com/vuejs/vue-cli/issues/5125)
	* [ ] Get rid of node-ipc v9 (Either replace it [\#2621](https://github.com/vuejs/vue-cli/issues/2621), or wait for the v10 release [\#4937](https://github.com/vuejs/vue-cli/issues/4937))

## Modern Mode

* [x] Use [`@babel/preset-modules`](https://github.com/babel/preset-modules) for modern build [\#4848](https://github.com/vuejs/vue-cli/issues/4848)
* [ ] Investigate the feasibility of bundling polyfills to a separate chunk (like the [“differential loading”](https://angular.io/guide/deployment#differential-builds) feature of Angular CLI, may replace the current `polyfillsPlugin` implementation)

## Misc

- A `vue doctor` command that diagnoses common misconfigurations in the user environment [https://github.com/vuejs/vue-cli/projects/10](https://github.com/vuejs/vue-cli/projects/10)
- A `vue stats` command like [`rake stats`](https://thoughtbot.com/blog/simple-test-metrics-in-your-rails-app-and-what-they)

## Major Releases

We also have plan for a new major release sometime in the middle of the year, pending the status of some primary dependencies of the core packages.

At the moment of writing, we plan to ship Vue CLI 5 after the stable release of Webpack 5.

Current planned features of Vue CLI 5 include:

* Webpack 5
* HTML Webpack Plugin 4
* Cypress 4
* Workbox 5
* Jest 26
* Mocha 7
* Enable modern mode by default
* Drop support of Node.js 8
* Drop support of TSLint
* Do not allow creating projects with uppercase names even in Vue CLI UI.
* Consider deprecating the instant prototyping feature