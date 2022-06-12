# Whist README

This repository is Whist's fork of `brave-ui`, with a few modifications. We forked `brave-ui` so that we could build Whist integrated within Chromium on top of Brave, to benefit from Brave's features and development pipeline.

Note that Dependabot security warnings will frequently appear on this project as it is a large Node project. Given that we frequently rebase from upstream Brave, we prefer to let them handle Dependabot/security patches, and will generally close those Dependabot security warnings. We keep them running in case there is a serious security flaw that we must tackle ourselves.

## Whist Changelog

None so far. Once we make modifications to this repository, we will list them here.

## Development

Before building or modifying the code, you should pull the latest changes from the public [`brave/brave-ui`](https://github.com/brave/brave-ui) repository that this repository is forked from. To setup your repository, follow these steps:

1. Clone and enter the repository

```
git clone https://github.com/whisthq/brave-ui && cd brave-ui
```

2. Add the upstream repository as a remote

```
git remote add upstream https://github.com/brave/brave-ui
```

3. Disable pushing to upstream Brave UI

```
git remote set-url --push upstream DISABLE
```

After this, you should be able to list your remotes with `git remote -v` if you ever need to debug.

Since Brave UI is a large and active project, we will very often want to work with the latest upstream code; meanwhile, we need to make sure that our own repository has a sane commit history -- we cannot simply periodically merge the latest Brave UI on top of our own modifications.

Instead, perform the following steps to incorporate changes from upstream:

1. Fetch the latest changes to the `upstream` remote

```
git fetch upstream
```

2. Rebase on top of your current work

```
git rebase upstream/master
# git rebase upstream/<desired branch> for other upstream branches
```

3. Resolve merge conflicts, if any arise, and push to the Whist Brave Core repository

```
git push origin <current branch>
```

## Building & Publishing

This project gets built via [`brave-browser`](https://github.com/whisthq/brave-browser). Please refer to that repository for instructions on building and publishing.

---

# Brave README

<p align="center"><img src="./ui-logo.svg" width="130px" height="170px"/></p>

<p align="center">
<a href="https://www.npmjs.com/package/brave-ui" alt="NPM"><img src="https://img.shields.io/npm/v/brave-ui.svg" /></a>
<a href="https://travis-ci.org/brave/brave-ui" alt="Travis"><img src="https://img.shields.io/travis/brave/brave-ui.svg" /></a>
<a href="https://snyk.io/test/github/brave/brave-ui" alt="Known Vulnerabilities"><img src="https://snyk.io/test/github/brave/brave-ui/badge.svg" /></a>
<a href="#" alt="NPM"><img src="https://img.shields.io/npm/dt/brave-ui.svg" /></a>
<a href="https://lernajs.io/" alt="Lerna"><img src="https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg" /></a>
<a href="https://standardjs.com" alt="JavaScript Style Guide"><img src="https://img.shields.io/badge/code_style-standard-brightgreen.svg" /></a>
</p>

Here you will find a list of reusable React components used in most of Brave products. Brave UI's [component library](https://brave.github.io/brave-ui) can be found on Storybook.

:exclamation:**Important:** We are still hacking a lot on this project, and therefore don't recommend that anyone use it yet. It's free to try and use at your own risk but bear in mind that components and APIs are very likely to change without notice.

## Installation

```
$ npm install
```

## Using Brave UI

```
npm run storybook-start
```

## Tests

We use Jest for testing. Playground is available under the `stories/` folder.

```
npm run test-unit
```

## License

This project is licensed under the MPL-2.0.
