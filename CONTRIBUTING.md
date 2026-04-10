# Contributor Manual

We welcome contributions of any size and contributors of any skill level.
As an open source project, we believe in giving back to our contributors.
We are happy to help with guidance on PRs, technical writing, and turning any feature idea into a reality.

> **Tip for new contributors:**
> Take a look at [GitHub's Docs](https://docs.github.com/en/get-started/quickstart/hello-world) for helpful information on working with GitHub.

## Types of contributions

Help writing docs, catching typos and errors, as well as translating docs into other languages is always welcome.

You can also get involved by leaving feedback on [issues][issues] or reviewing [pull requests][pulls] by other contributors.

We encourage you to:

- [**Open an issue**][new-issue] to let us know of ideas or improvements in All Contributors, documentation you found unclear, or other issues you run into.

- [**Look at existing issues**][issues] (especially those labelled [“good first issue”][gfi]) to find ways to contribute.

- **Make a pull request (PR)** to address an open issue or to fix obvious problems.
  Read more about [making a PR in GitHub’s docs][pr-docs]

- [**Review existing PRs**][pulls] to help us merge contributions sooner.

- [**Add or update translations**](#translations). We need help translating both All Contributors’ documentation.

## About this repo

This repo contains only the documentation of All Contributors. For other repositories of the All Contributor Specification, go to [our organisation][org].

### Setting up a development environment

You can [develop locally](#developing-locally) or use an online coding development environment like [GitHub Codespaces](#developing-using-github-codespaces) to get started quickly.

#### Developing locally

**Prerequisites:** Developing All Contributors docs requires [Node.js](https://nodejs.org/en) (v22 or higher) and [pnpm](https://pnpm.io/) (v10.10 or higher). Make sure you have these installed before following these steps.

1. **Fork All Contributors** to your personal GitHub account by clicking <kbd>Fork</kbd> on the [main All Contributors docs repo page][repo].

2. **Clone your fork** of All Contributors docs to your computer. Replace `YOUR-USERNAME` in the command below with your GitHub username to clone in a Terminal:

   ```sh
   git clone https://github.com/YOUR-USERNAME/allcontributors.org.git
   ```

3. **Change directory** to the cloned repo:

   ```sh
   cd allcontributors.org
   ```

4. **Install dependencies** with `pnpm`:

   ```sh
   pnpm i
   ```

5. **Generate TypeScript types** for all Astro modules:

   ```sh
   pnpm astro sync
   ```

#### Developing using GitHub Codespaces

1. **Create a new codespace** via https://codespaces.new/all-contributors/allcontributors.org

2. **Generate TypeScript types** for all Astro modules:

   ```sh
   pnpm astro sync
   ```

3. Pass the `--host` flag to avoid “502 Bad Gateway” errors:

   ```sh
   pnpm dev --host
   ```

The dev container used for GitHub Codespaces can also be used with [other supporting tools](https://containers.dev/supporting), including VS Code.

## Dev Server

Run the Astro dev server to see how changes you make look live.

To do this, run `pnpm dev`:

```sh
pnpm dev
```

You should then be able to open <http://localhost:4321> and see your changes.

### Check for broken links in the docs site

When adding or translating content in the All Contributors docs site, you can check all internal links are valid.
All GitHub PRs are checked this way automatically, but testing locally can help if you want to confirm changes are correct before committing them.

To do this, run `pnpm linkcheck`:

```sh
pnpm linkcheck
```

If there are any broken links, the build will fail and log which pages need to be fixed.

## Translations

Translations help make All Contributors accessible to more people.

### Translating All Contributors

The documentation of All Contributors is translated into multiple languages. You can find the source code for the site in [the `docs/` directory](./docs/) of this repository.

Help out by:

- Reviewing [open translation PRs][pulls]
- Updating out-of-date translated pages
- Adding an untranslated page

Visit **<https://allcontributors.org/i18n>** to track translation progress for the currently supported languages.

#### Adding a new language to All Contributors’ docs

To add a language, you will need its BCP-47 tag and a label. See [“Adding a new language”](https://contribute.docs.astro.build/guides/i18n/#adding-a-new-language) in the Astro docs contributor guide for some helpful tips around choosing these.

- Add your language to the `locales` config in `locales.config.ts`
- Add your language to the `locales` config in `lunaria.config.json`
- Create the first translated page for your language.
  This must be the All Contributors landing page: `src/content/docs/{language}/index.mdx`.
- Open a pull request on GitHub to add your changes to All Contributors docs!

[org]: https://github.com/all-contributors
[repo]: https://github.com/all-contributors/allcontributors.org
[issues]: https://github.com/all-contributors/allcontributors.org/issues
[pulls]: https://github.com/all-contributors/allcontributors.org/pulls
[new-issue]: https://github.com/all-contributors/allcontributors.org/issues/new/choose
[pr-docs]: https://docs.github.com/en/get-started/quickstart/contributing-to-projects#making-a-pull-request
[gfi]: https://github.com/all-contributors/allcontributors.org/issues?q=is%3Aissue+is%3Aopen+label%3A%22good+first+issue%22+
