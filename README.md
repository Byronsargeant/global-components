# @nuxtjs/global-components

[![npm version][npm-version-src]][npm-version-href]
[![npm downloads][npm-downloads-src]][npm-downloads-href]
[![Github Actions CI][github-actions-ci-src]][github-actions-ci-href]
[![Codecov][codecov-src]][codecov-href]
[![License][license-src]][license-href]

> Module to register global components for Nuxt.js

[📖 **Release Notes**](./CHANGELOG.md)


## :warning: Important

NuxtJS Team released [@nuxt/components](https://github.com/nuxt/components) to auto import components when used in templates, allowing better performances and features.

If you want to migrate from this module, you will simply have to remove the `.global` suffix.

## Usage

Suffix your components with `.global.{ext}` to declare your global components.

```bash
components/
  my-component.vue # local component, import it to use it
  my-button.global.vue # global component, no need to register it!
```

See [live demo](https://codesandbox.io/s/nuxtjs-global-components-ujtoq).

## Setup

1. Add `@nuxtjs/global-components` dependency to your project

```bash
yarn add --dev @nuxtjs/global-components # or npm install --save-dev @nuxtjs/global-components
```

2. Add `@nuxtjs/global-components` to the `buildModules` section of `nuxt.config.js`

```js
export default {
  buildModules: [
    // Simple usage
    '@nuxtjs/global-components',

    // With options
    ['@nuxtjs/global-components', { /* module options */ }]
  ]
}
```

:warning: If you are using Nuxt **< v2.9** you have to install the module as a `dependency` (No `--dev` or `--save-dev` flags) and use `modules` section in `nuxt.config.js` instead of `buildModules`.

### Using top level options

```js
export default {
  buildModules: [
    '@nuxtjs/global-components'
  ],
  globalComponents: {
    /* module options */
  }
}
```

## Options

### `dir`

- Type: `String|Array`
- Default: `components`

A list of directories to find components inside your nuxt project.

### `suffixes`

- Type: `Array`
- Default: `['global']`

The suffixes that files can contain.

### `extensions`

- Type: `Array`
- Default: `['vue', 'js', 'ts']`

The extensions that files can contain.

### `ignore`

- Type: `Array`
- Default: `[]`

An array of glob patterns to exclude matches.

### `ignoreNameDetection`

- Type: `Boolean`
- Default: `false`

Ignore name detection using prototype names.

## License

[MIT License](./LICENSE)

Insipired by [nuxtjs.org](https://github.com/nuxt/nuxtjs.org/tree/master/modules/components)

Copyright (c) Nuxt Community

<!-- Badges -->
[npm-version-src]: https://img.shields.io/npm/v/@nuxtjs/global-components/latest.svg
[npm-version-href]: https://npmjs.com/package/@nuxtjs/global-components

[npm-downloads-src]: https://img.shields.io/npm/dt/@nuxtjs/global-components.svg
[npm-downloads-href]: https://npmjs.com/package/@nuxtjs/global-components

[github-actions-ci-src]: https://github.com/nuxt-community/global-components/workflows/ci/badge.svg
[github-actions-ci-href]: https://github.com/nuxt-community/global-components/actions?query=workflow%3Aci

[codecov-src]: https://img.shields.io/codecov/c/github/nuxt-community/global-components.svg
[codecov-href]: https://codecov.io/gh/nuxt-community/global-components

[license-src]: https://img.shields.io/npm/l/@nuxtjs/global-components.svg
[license-href]: https://npmjs.com/package/@nuxtjs/global-components
