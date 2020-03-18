# Dynamic I18n v2.0.0
[![npm](https://img.shields.io/npm/dt/@nuxtjs/dynamic-i18n.svg?style=flat-square)](https://www.npmjs.com/package/@nuxtjs/dynamic-i18n)
[![npm (scoped with tag)](https://img.shields.io/npm/v/@nuxtjs/dynamic-i18n/latest.svg?style=flat-square)](https://www.npmjs.com/package/@nuxtjs/dynamic-i18n)

**Dynamic i18n** is a tool to import your i18n and inject it in your vue-i18n instance

This module automatically import your translate file from a specific provider.

# RooadMap
- Integrate [https://github.com/nuxt-community/nuxt-i18n](nuxt-i18n) plugin

# Supported providers
* Google sheets, see example of file [here](https://docs.google.com/spreadsheets/d/1dBsD-EsKb1mHvq4P2Zm4DcOPK2szuxqkkvnTsmbkYhc/edit?usp=sharing)

## Setup
- Add `@nuxtjs/dynamic-i18n` dependency using yarn or npm to your project
- Add `@nuxtjs/dynamic-i18n` to `modules` section of `nuxt.config.js`
```js
  modules: [
    '@nuxtjs/dynamic-i18n'
  ],
  dynamicI18n: {
    languages: ['en', 'fr'],
    providerKey: '1dBsD-EsKb1mHvq4P2Zm4DcOPK2szuxqkkvnTsmbkYhc',
    credentials: {...},
    ...Options
  }
```

## Options

| key | Required | Default | Description |
|-----|----------|---------|-------------|
| languages | **Required** | `[]` | Contain all the locales we want to import. |
| provider-key | **Required** | `''` | The identifier for the source of the data stored. |
| credentials | **Required** | `{}` | Configuration for the provider. |
| id | Optional | None | id of the active document. Use gid for google sheet url to get active tab id |
| maxAge | Optional | `1000 * 60 * 60` | Max age of translate files (60 minutes), use 0 to disable it
| fallbackLocale | Optional | `'en'` | Default language if not founded from the store |
| localeNamespaceStore | Optional | `'i18n'` | Default namespace of i18n locale store. see example of store [here](https://github.com/nuxt/nuxt.js/blob/dev/examples/i18n/store/index.js)|
| outputFilePrefix | Optional | `'locale'` | Prefix of the output file like : {{outputFilePrefix}}-{{language}}.json. |
| staticFolder | Optional | `static` | Specify folder in static

## Migration from v1 to v2

Dynamic i18n has been updated to work with the new version of [https://theoephraim.github.io/node-google-spreadsheet/#/](google-spreadsheet) and the `title` option to locate the tab has been replaced by `id` which is the `gid` identifier that you can get from the google sheet url query params `gid`.

## 📑 License

[MIT License](./LICENSE) - Nuxt Community
