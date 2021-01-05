# @wcom/create-app

[![package-badge]][package]
[![license-badge]][license]
[![semantic-release-badge]][semantic-release]

[package]: https://www.npmjs.com/package/@wcom/create-app
[package-badge]: https://img.shields.io/npm/v/@wcom/create-app
[license]: https://github.com/wcom-js/create/blob/main/LICENSE
[license-badge]: https://img.shields.io/github/license/wcom-js/create
[semantic-release]: https://github.com/semantic-release/semantic-release
[semantic-release-badge]: https://img.shields.io/badge/%20%20%F0%9F%93%A6%F0%9F%9A%80-semantic--release-e10079.svg

## Introduction

> See an example of a project created with `@wcom/app` [here](https://github.com/wcom-js/lit-test).

Simply create a modern web component library by running the following...

```bash
# NPM
$ npm init @wcom/app <my-library>

# Yarn
$ yarn create @wcom/app <my-library>
```

Then follow the prompts and you'll be up and running in no time! 

Once you are ready, simply create your first component and test inside `./src/components` and 
then run `npm run transform`. From here the worlds your oyster, keep reading for some 
more information on how this library works.

## IDE

If you're using [VSCode](https://code.visualstudio.com/) the consider installing the following 
extensions...

- [ESLint](https://marketplace.visualstudio.com/items?itemName=dbaeumer.vscode-eslint)
- [Prettier](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [lit-plugin](https://marketplace.visualstudio.com/items?itemName=runem.lit-plugin)

## Build

The build script simply leverages TypeScript to do the work and outputs basic CJS and ESM exports 
as Polymer suggests...

> We recommend publishing components as unoptimized JavaScript modules, and performing build-time 
> optimizations at the application level. This gives build tools the best chance to deduplicate 
> code, remove dead code, and so on.

## Lint

Linting is performed by [ESLint](https://eslint.org) and comes out of the box with simple 
defaults...

- [Airbnb Config](https://github.com/iamturns/eslint-config-airbnb-typescript)
- [Prettier Config](https://github.com/prettier/eslint-config-prettier)

In addition, [lit-analyzer](https://www.npmjs.com/package/lit-analyzer) is used to type-check 
and lint `lit-html` templates with the same engine and rules as `lit-plugin`. Finally code is 
formatted by [Prettier](https://prettier.io).

Linting and formatting have not been configured to run when committing files but it is ready 
for you to add if you wish. Simply add the following inside `package.json`...

```json
"lint-staged": {
  "*.ts": "npm run lint"
}
```

## Server

The development server uses [Web Dev Server](https://modern-web.dev/guides/dev-server/getting-started) 
to get you up and running. Out of the box nothing is setup so you won't see anything when you 
visit `localhost:8080`. It's up to you how you setup the dev server. One way is you could create 
a `index.html` next to each component and visit the URL to it in your browser, such as 
`http://localhost:8080/src/components/button`.

## Test

Testing is performed by the [Web Test Runner](https://modern-web.dev/guides/test-runner/getting-started). 
Simply create `src/**/*.test.ts` files and run any `test:*` script. See their documentation for more information.

## Release

Releases are automatically run by GitHub Actions and are processed by 
[`semantic-release`](https://github.com/semantic-release/semantic-release). Simply push to the 
`release` branch when you want to create a release. 

See [Conventional Commits](https://www.conventionalcommits.org/en/v1.0.0-beta.4) for commit 
guidelines.

## Documentation

Documentation is automatically generated by the `transform` command (more information below) and 
exists inside the `./docs` directory. No fancy static site generators or tools, we'll leave 
that to you. However, sometimes simple markdown files hosted on GitHub is all you need.

## Transform

The transform command uses [`@wcom/cli`](https://github.com/wcom-js/cli) to parse your 
TypeScript files and collect metadata such as what properties, methods, events and other 
information each component contains. This metadata can then be 'transformed' into other formats 
such as `json`, `markdown`, `.d.ts` etc. To find out more about the transform tool click the link 
to `@wcom/cli` above.

Overall it is a handy CLI tool to manage all the annoying pesky tasks for you such as building 
documentation, or generating types such as `HTMLElementTagNameMap` or `HTMLElementEventMap`.