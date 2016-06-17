# Changelog Generator

[![version][npm-version]][npm-url]
[![License][npm-license]][license-url]
[![Downloads][npm-downloads]][npm-url]
[![Dependencies][david-image]][david-url]

Generate changelog using your git commit messages into a digestible change-log / release-log in markdown using the Github Comparison API, and
some extremely gnarly logic.

## Rules

1. Commit messages **must** adhere to the [Niji Commit Format][niji-format], also supports [Angular Commit Message Convention][angular-convention].
2. Comparisons must be made using **tags** (`v2.10.4`) or **branches** (`release/v2.10.4`) to take advantage of 
version numbers.

## Install

```
$ npm install niji -g
```

## Usage

```sh
  Usage: niji [options]

  Options:

    -h, --help               output usage information
    -V, --version            output the version number
    -o, --out [directory]    Location of the directory to output changelog
    -r, --repo [name]        Repository name
    -u, --user [name]        Repository username
    -h, --head [name]        Commit head
    -b, --base [name]        Commit base
    -f, --format [option]    Changelog Format Type (table (default), node)
    -s, --sort [option]      Sorting option (time (default), type, scope, author)
    -t, --token [token]      Github Token
    -c, --configure [token]  Configure github token for future reference
```

## Configuring Github Token

```sh
$ niji -c <GITHUB_TOKEN>
```

You can grab your [Github Token here.](https://github.com/settings/tokens)

**Note**

You can specify `-t <GITHUB_TOKEN>` to override a configured github token or to avoid saving your github token.

## Formats

- Default: Table view
- Node: Commit list view

## Example

After installing, run the command with your desired arguments, here is an example:

```sh
$ niji \
    -r <GITHUB_PROJECT_NAME> \
    -u <GITHUB_USERNAME> \
    -h <GITHUB_HEAD_TAG_OR_BRANCH_OR_SHA> \
    -b <GITHUB_BASE_TAG_OR_BRANCH_OR_SHA>
```

The script will output markdown like so, which you then are free to copy / paste anywhere:

```markdown
## [2beff77] | 2016-06-17
*branch:[`2beff77`](https://github.com/niji-commit/generator/tree/2beff77)*

Type | Scope | Link | Description | References | Author
--- | --- | --- | --- | --- | ---
Documentation | readme | [`2beff77a01`](https://github.com/niji-commit/generator/commit/2beff77a01d3a9f5d1f38fd3ff41cf50815dc26c) |  Fix david dependency badge |  | Nijiko Yonskai

[2beff77]: https://github.com/niji-commit/generator/compare/3bcddd9...2beff77
```

Here is the above markdown as a preview:

---
## [2beff77] | 2016-06-17
*branch:[`2beff77`](https://github.com/niji-commit/generator/tree/2beff77)*

Type | Scope | Link | Description | References | Author
--- | --- | --- | --- | --- | ---
Documentation | readme | [`2beff77a01`](https://github.com/niji-commit/generator/commit/2beff77a01d3a9f5d1f38fd3ff41cf50815dc26c) |  Fix david dependency badge |  | Nijiko Yonskai

[2beff77]: https://github.com/niji-commit/generator/compare/3bcddd9...2beff77
---

## License

Licensed under [The MIT License](LICENSE).

[license-url]: https://github.com/niji-commit/generator/blob/master/LICENSE
[npm-url]: https://www.npmjs.com/package/niji
[npm-license]: https://img.shields.io/npm/l/niji.svg?style=flat
[npm-version]: https://img.shields.io/npm/v/niji.svg?style=flat
[npm-downloads]: https://img.shields.io/npm/dm/niji.svg?style=flat
[niji-format]: https://github.com/niji-commit/format
[david-url]: https://david-dm.org/niji-commit/generator
[david-image]: https://img.shields.io/david/niji-commit/generator.svg?style=flat
[angular-convention]: https://github.com/angular/angular.js/blob/master/CONTRIBUTING.md#-git-commit-guidelines
