# ts-lib-template

> An easy way to create a TypeScript library without hassle.

`ts-lib-template` is a template for creating a TypeScript library. It comes built in with many common utilities, such as git hooks

## Getting Started

First, install the template. There are two ways to do this.

1. Create a copy of the template on Github and clone the new repo to your machine
2. In the terminal run `npx degit snek152/ts-lib-template new-project`

Then, install the dependencies.

```bash
cd new-project
npm install
```

The project comes preinstalled with Husky (git hooks), Typedoc (documentation), and the Barreler CLI (make barrel exports automatically).

The commands below are available to you.

```bash
# Build the library
npm run build

# Development - watch for changes and rebuild library + remake barrels
npm run dev

# Build the docs for the library - default in docs folder
npm run make:docs
```

Make sure to edit your `package.json` file to include your library name, description, and other information.

The project also comes with a deploy action that will build the library and docs and publish them to npm and Github Pages, respectively. The action is triggered on a push or pull request to the `master` branch. The action also bumps the package.json version depending on your commit message, so make sure to use the following syntax for commits:

```bash
# Increment minor version
feat: your_commit_msg

# Increment patch version
fix: your_commit_msg

# Increment major version
MAJOR: your_commit_msg

# Increment release candidate version
alpha: your_commit_msg
```

**WARNING** - The deploy action will need to authenticate with npm in order to publish your package. Make sure to set the `npm_token` secret in the repository settings to your own token, generated from [npmjs.com](https://npmjs.com).

**WARNING** - The Github action triggers are commented out at the time of creation. Make sure to uncomment them. Additionally, the action by default triggers on a push to the `master` branch. Make sure to change this to your default branch if it is not `master`.

## Motivation

In August of 2022, I decided to start developing npm packages using Typescript, starting with basic [CLIs](https://github.com/snek152/js-barrels) and later moving to more complex [libraries](https://github.com/snek152/nextjs-utilities). The common problem I found with all of these was that there was hardly any information out there on how to start building these kinds of packages from the ground up, and thus `ts-lib-template` was born.
