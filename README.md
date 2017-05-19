# stylelint-config-narwin

DockYard standard config for stylelint.

To see the rules that this config uses, please read the [config itself](./index.js).

## Example

Coming soon.

## Installation

```bash
npm install stylelint-config-narwin --save-dev
```

## Usage

If you've installed `stylelint-config-narwin` locally within your project, just set your `stylelint` config to:

```json
{
  "extends": "stylelint-config-narwin"
}
```

If you've globally installed `stylelint-config-narwin` using the `-g` flag, then you'll need to use the absolute path to `stylelint-config-narwin` in your config e.g.

```json
{
  "extends": "/absolute/path/to/stylelint-config-narwin"
}
```

### Extending the config

Simply add a `"rules"` key to your config, then add your overrides and additions there.

For example, to change the `indentation` to tabs, turn off the `number-leading-zero` rule, change the `property-no-unknown` rule to use its `ignoreAtRules` option and add the `unit-whitelist` rule:

```json
{
  "extends": "stylelint-config-narwin",
  "rules": {
    "indentation": "tab",
    "number-leading-zero": null,
    "property-no-unknown": [ true, {
      "ignoreProperties": [
        "composes"
      ]
    }],
    "unit-whitelist": ["em", "rem", "s"]
  }
}
```

### Using the config with SugarSS syntax

The config is broadly compatible with [SugarSS](https://github.com/postcss/sugarss) syntax. You *will* need to turn off the rules that check braces and semicolons, as so:

```json
{
  "extends": "stylelint-config-standard",
  "rules": {
    "block-closing-brace-empty-line-before": null,
    "block-closing-brace-newline-after": null,
    "block-closing-brace-newline-before": null,
    "block-closing-brace-space-before": null,
    "block-opening-brace-newline-after": null,
    "block-opening-brace-space-after": null,
    "block-opening-brace-space-before": null,
    "declaration-block-semicolon-newline-after": null,
    "declaration-block-semicolon-space-after": null,
    "declaration-block-semicolon-space-before": null,
    "declaration-block-trailing-semicolon": null
  }
}
```

## [Changelog](CHANGELOG.md)

## [License](LICENSE)
