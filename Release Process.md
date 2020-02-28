
The Git workflow used in this project is largely inspired by [Gitflow workflow]()(https://www.atlassian.com/git/tutorials/comparing-workflows/gitflow-workflow).

* The development branch is `dev`
* When releasing a new **patch** version:
	* Cherry-pick the necessary commits to the `master` branch
	* Push to GitHub, make sure all CI tests are passed, and then run `yarn release` in the project root
	* Draft a new **release** in the GitHub [Releases](https://github.com/vuejs/vue-cli/releases) page
	* Merge `master` back into `dev`
* When releasing a new **minor/major** version
	* Cherry-pick the necessary commits to the `next` branch
	* Push to GitHub, make sure all CI tests are passed, and then run `yarn release --dist-tag next` in the project root
	* Draft a new **pre-release** in the GitHub [Releases](https://github.com/vuejs/vue-cli/releases) page
	* Merge `next` back into `dev`
	* If no urgent regressions have been reported in **3 days**:
		* run `npm dist-tag add {{package-name}} latest` for all the packages in this repository
		* Go to the Releases page and uncheck the `This is a pre-release` option for this release
	* Otherwise, fix the bugs, and start over to release a new version from the `next` branch. But this time, the new version string should be bumped as a patch.