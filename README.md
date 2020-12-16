# learn.redwoodjs.com

Deployment URL: https://objective-lamarr-858e5f.netlify.app/

[![Crowdin](https://badges.crowdin.net/learn-redwoodjs/localized.svg)](https://crowdin.com/project/learn-redwoodjs)

This WIP site will be used to present multilingual tutorial docs for RedwoodJS.

### TODO

- Hook up to Crowdin l10n management
- add EN tutorial content
- UI string translation
- SEO 🤷

### Docusaurus 2 + Crowdin

We are using a yet-to-be-documented release of Docusuraus 2 that includes integration with l10n management service Crowdin. While there are no docs to work off of yet, we have [this PR](https://github.com/facebook/docusaurus/pull/3325) and [this explanatory comment](https://github.com/facebook/docusaurus/issues/3317#issuecomment-742589241) to reference

Also learning from reading source code for [jest website migration on `docusaurus-2` branch](https://github.com/jest-website-migration/jest/tree/docusaurus-2/website-v2), which is using this same undocumented setup for thier localized docs. See their test site here: https://jest-v2.netlify.app/

## Getting started

```
yarn install

yarn start
```

- Only one locale can be servered in development at a time, so start yarn with the locale you want to test

```
yarn start --locale fr
```

No worries, things work better once the site is built and served. Try this and the locale switcher suddenly works:

```
yarn build

yarn serve
```

## Localized content

Source content markdown docs are found in `/docs/..`.

Localized docs content is placed in same structure as source content from "mount point" `i18n/%two_letters_code%/docusaurus-plugin-content-docs/current/..`, where `%two_letters_code%` is generally a locale's [ISO 639-1 code](https://en.wikipedia.org/wiki/List_of_ISO_639-1_codes)

Localized content without a "counterpart" for the source content defaults to the source locale.

Every doc category (ex: 'Tutorial') needs to be mapped to a Crowdin translation flow.

We just have `tutorial` for now, but contact `@clairefro` to add new doc categories if needed.

### crowdin.yml

Configuration file for crowdin integration. Useful for seeing how source docs are mapped to i18n folder

## Translation

**IMPORTANT: Do not translate directly in this repo!**

All content is translated via Crowdin so we can keep our docs from going stale.  
https://crowdin.com/project/learn-redwoodjs/

Translations made from the above repo are auto-PR'ed to this Github repo once approved.

---

# Website

This website is built using [Docusaurus 2](https://v2.docusaurus.io/), a modern static website generator.

## Installation

```console
yarn install
```

## Local Development

```console
yarn start
```

This command starts a local development server and open up a browser window. Most changes are reflected live without having to restart the server.

## Build

```console
yarn build
```

This command generates static content into the `build` directory and can be served using any static contents hosting service.

## Deployment

```console
GIT_USER=<Your GitHub username> USE_SSH=true yarn deploy
```

If you are using GitHub pages for hosting, this command is a convenient way to build the website and push to the `gh-pages` branch.