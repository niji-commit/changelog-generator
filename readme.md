# Niji Commit Generator

[![version][npm-version]][npm-url]
[![License][npm-license]][license-url]
[![Downloads][npm-downloads]][npm-url]
[![Dependencies][david-image]][david-url]

Turn your commit messages into a digestible change-log / release-log in markdown using the Github Comparison API, and
some extremely gnarly logic.

Commit messages **must** adhere to the [Niji Commit Format][niji-format].

## Install

```
$ npm install niji -g
```

## Usage

```sh
  Usage: niji [options]

  Options:

    -h, --help             output usage information
    -V, --version          output the version number
    -o, --out [directory]  Location of the directory to output changelog
    -r, --repo [name]      Repository name
    -u, --user [name]      Repository username
    -h, --head [name]      Commit head
    -b, --base [name]      Commit base
    -t, --token [token]    Github Token
```

You can grab your [Github Token here.](https://github.com/settings/tokens)

## Example

After installing, run the command with your desired arguments, here is an example:

```sh
$ niji \
    -r <GITHUB_PROJECT_NAME> \
    -u <GITHUB_USERNAME> \
    -t <GITHUB_TOKEN> \
    -h <GITHUB_HEAD_TAG_OR_BRANCH_OR_SHA> \
    -b <GITHUB_BASE_TAG_OR_BRANCH_OR_SHA>
```

The script will output markdown like so, which you then are free to copy / paste anywhere:

```markdown
## [v2.4.12] | 2015-09-21
*branch:[`release/v2.4.12`](https://github.com/Nijikokun/project/tree/release/v2.4.12)*

Type | Scope | Link | References | Description
--- | --- | --- | --- | ---
Changed | app | [eabfe21f](https://github.com/Nijikokun/project/commit/eabfe21f9af124abawee0193d44e630946d3d572) | [#271](https://github.com/Nijikokun/project/commit/271) |  Change app key to service token, closes [#271](https://github.com/Nijikokun/project/issues/271)

[v2.4.12]: https://github.com/Nijikokun/project/compare/release/v2.4.11...release/v2.4.12
```

Here is the above markdown as a preview:

---

## [v2.4.12] | 2015-09-21
*branch:[`release/v2.4.12`](https://github.com/Nijikokun/project/tree/release/v2.4.12)*

Type | Scope | Link | References | Description
--- | --- | --- | --- | ---
Changed | app | [eabfe21f](https://github.com/Nijikokun/project/commit/eabfe21f9af124abawee0193d44e630946d3d572) | [#271](https://github.com/Nijikokun/project/commit/271) |  Change app key to service token, closes [#271](https://github.com/Nijikokun/project/issues/271)

[v2.4.12]: https://github.com/Nijikokun/project/compare/release/v2.4.11...release/v2.4.12

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
