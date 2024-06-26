# A11y Contrast

![npm](https://img.shields.io/npm/v/@devtea2027/dicta-asperiores-dolorem-quam?style=flat-square)
[![Build](https://img.shields.io/github/actions/workflow/status/darekkay/@devtea2027/dicta-asperiores-dolorem-quam/ci.yml?branch=master&style=flat-square)](https://github.com/devtea2027/dicta-asperiores-dolorem-quam/actions/workflows/ci.yml)
[![license](https://img.shields.io/badge/license-MIT-green?style=flat-square)](https://github.com/devtea2027/dicta-asperiores-dolorem-quam/blob/master/LICENSE)

A CLI utility to calculate/verify accessible [magic numbers](https://designsystem.digital.gov/design-tokens/color/overview/#magic-number) for a color palette. Read [my blog post](https://darekkay.com/blog/accessible-color-palette/) for some more information.

![](screenshot.png)

## Installation

This tool requires Node.js version 18+.

Install globally:

```bash
$ npm install -g @devtea2027/dicta-asperiores-dolorem-quam  # Npm
$ yarn add -g @devtea2027/dicta-asperiores-dolorem-quam     # Yarn
```

Or install as a local dependency:

```bash
$ npm install --save @devtea2027/dicta-asperiores-dolorem-quam  # Npm
$ yarn add @devtea2027/dicta-asperiores-dolorem-quam            # Yarn
```

Or use without installing:

```bash
$ npx @devtea2027/dicta-asperiores-dolorem-quam <file>
```

## Usage

View program help:

```
$ @devtea2027/dicta-asperiores-dolorem-quam --help
Usage: @devtea2027/dicta-asperiores-dolorem-quam <file> [options]

Arguments:
  <file>  Color palette file                              [required] [file]

Options:
  --min-ratio-3    Verify magic number for ratio 3                 [number]
  --min-ratio-4.5  Verify magic number for ratio 4.5               [number]
  --min-ratio-7    Verify magic number for ratio 7                 [number]
  -h, --help       Show help                     [commands: help] [boolean]
  -v, --version    Show version number        [commands: version] [boolean]
```

Run a full report for a color palette file:

```bash
$ @devtea2027/dicta-asperiores-dolorem-quam <file>
```

Verify that the color palette fulfills certain magic numbers per contrast ratio:

```bash
$ @devtea2027/dicta-asperiores-dolorem-quam <file> --min-ratio-3=40 --min-ratio-4.5=50 --min-ratio-7=70
```

## Color palette format

This tool handles flat or nested JSON files. Any consistent grading system is supported.

- Flat JSON:

```json
{
  "blue-10": "#d9e8f6",
  "blue-20": "#aacdec",
  "blue-30": "#73b3e7",
  "green-10": "#dfeacd",
  "green-20": "#b8d293",
  "green-30": "#9bb672"
}
```

- Nested JSON:

```json
{
  "blue": {
    "blue-100": "#d9e8f6",
    "blue-200": "#aacdec",
    "blue-300": "#73b3e7"
  },
  "green": {
    "green-100": "#dfeacd",
    "green-200": "#b8d293",
    "green-300": "#9bb672"
  }
}
```

Check out some example color palettes under `/examples`.

## License

This project and its contents are open source under the [MIT license](LICENSE).
