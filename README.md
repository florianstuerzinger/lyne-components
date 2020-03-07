[![Build Status](https://travis-ci.org/lyne-design-system/lyne-components.svg?branch=master)](https://travis-ci.org/lyne-design-system/lyne-components) [![Greenkeeper badge](https://badges.greenkeeper.io/lyne-design-system/lyne-components.svg)](https://greenkeeper.io/) [![semantic-release](https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg)](https://github.com/semantic-release/semantic-release)

<h1 align="center">
  Lyne Components
</h1>

> Lyne Components are the building blocks of the Lyne Design System
> and are based on standard compliant [Web Components](https://www.webcomponents.org/specs)
> compiled by StencilJS and browsable through Storybook

## Todo
- refactor build_release_urls.js with promises
- in travis, build logs are cluttered. Lower log level for semantic-release/npm publish and npm install -g netlify-cli
- Rename package name to "lyne-components"
- Decide for Branching-Model
- Add Merge Checks
- Add Linter
- Repo -> Insights -> Community -> Fullfill checklist
- Semantic-release updates version in package.json, but in the package-lock.json it does not. should we?
- Prevent push to master
- npm script ```start``` runs stencil and storybook in parallel. We need sequential. Problem is that ```start:stencil``` has no exit code since it is serving and watching, so the second sequential command ```start:storybook``` is not run. Quick fix is to run them parallel.
- In Storybook, css changes are not updated in watch mode
- Different secrets and env-variables on git, travis and netlify.
  - Document exactly which key is needed for what and where to generate it
  - Before production: regenerate all keys
- for DEPLOYMENTS.md: in which timezone should we format the date?
- DEPLOYMENTS.md might get large over time. Should we limit it to x releases?
- build_release_urls.js -> check if there is a limit in the deployments request. Do we get the latest 50? 100? Do we get all? Probably, we need to limit it so  the response does not take too long
- ommit output when netlify_deploy.sh and build_release_urls.sh are called on travis
- Make sure that all production files that are published are minified and compressed (dist/, loader/, storybook-static/)
- In Deployments.md, write cleary that dev's should not change the file
- in Deployments.md: if a dev is changing the content and pushing to the repo, might we run into merge-conflicts? if yes, how could build_release_urls.js handle these?
- we should remove the npm script ```semantic-release```. Might be a problem that a dev is able to start it from his local machine

## Issues
- If you commit a fix and the merge the latest master before pushing, semantic-release won't do a new release: 'The local branch master is behind the remote one, therefore a new version won't be published.' -> https://travis-ci.org/lyne-design-system/lyne-components/jobs/658782240

## Verify
- If a travis release job is running, semantic-release did not run yet, and a new change with a breaking change is pushed to master, what happens? Travis should not make a new release, but make another build afterwards with a new release containing both changes
- For how long are deployments saved on netlify? Forever? 30 days? 1 year?

## SemVer
We use semantic versioning

## Git Guardian
Git Guardian is activated for this repo: https://dashboard.gitguardian.com/

## npm
The production build of the components can be found here on npm: https://www.npmjs.com/package/lyne-test

## Storybook
The storybook is deployed on netlify an can be found here: https://lyne-components-storybook.netlify.com

For a full list of deployments of all releases, please look here: https://github.com/lyne-design-system/lyne-components/blob/master/DEPLOYMENTS.md

## 🙌 Contributing
See [Contributing Guide](/.github/CONTRIBUTING.md) and thanks already in advance! 👀

## Developing
See [DEVELOP.md](./DEVELOP.md) for development docs.

## Releasing
You can find docs about our release process in [RELEASING.md](./RELEASING.md).

## Documentation


## 📝 License

Licensed under the [MIT](/LICENSE).
