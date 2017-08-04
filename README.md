# stylelint-config-narwin

DockYard standard configuration rules for CSS linting using [stylelint](https://stylelint.io).

To see the rules that this config uses, please read the [config itself](./index.js).

## Installation

```bash
npm install stylelint-config-standard --save-dev
npm install stylelint-config-narwin --save-dev
```

### Ember-specific Installation

Ember installation utilizes [ember-cli-stylelint](https://github.com/billybonks/ember-cli-stylelint) to provide integrated tests and reporting of stylelint errors. This must be version 0.15.0 or later to support Ember versions 2.13 and up.

```bash
npm install stylelint-config-narwin --save-dev
ember install ember-cli-stylelint
```

The ember-cli-stylelint addon will create a 'stylelint' config file at `/.stylelintrc`.

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

If you are setting up a new installation after `ember-cli-stylelint` you will update the `extends` property from 'stylelint-config-standard' to 'stylelint-config-narwin'. The `stylelint-config-narwin` configuration already extends the `stylelint-config-standard` configuration that is installed along with `ember-cli-stylelint`.  You may also add this config to your list of extensions per the [documentation](https://stylelint.io/user-guide/configuration/).

### Additional Ember configuration
#### Note
Configuration of stylelint is per [ember-cli-stylelint configuration](https://github.com/billybonks/ember-cli-stylelint/README.md).  For example, to update the linter for CSS instead of the default SCSS add the following to your `ember-cli-build.js`:

```javascript
....
module.exports = function(defaults) {
  var app = new EmberApp(defaults, {
    // Add options here
    stylelint: {
      linterConfig: {
        syntax: 'css'
      }
    }
  });
....
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

## Legal

[DockYard](http://dockyard.com/), Inc. &copy; 2017

[@dockyard](http://twitter.com/dockyard)

[Licensed under the MIT license](http://www.opensource.org/licenses/mit-license.php)
