# 1.2.0
- Null out "no-descending-specificity" rule
# 1.1.0
- Added stylelint order rules using `stylelint-order` plugin
- Rules based on [DockYard style guide](https://github.com/dockyard/styleguides/blob/master/ux-dev/css.md)
# 1.0.0
- Updated to stylelint 8 which requires removal of the following deprecated rules:
  - `custom-property-no-outside-root`
  - `media-feature-no-missing-punctuation`
  - `selector-no-empty`
  - `selector-root-no-composition`
  - `styleint-disable-reason`
- This also bumps support to PostCss 6
- Adds the use of [CssTree](https://github.com/csstree/csstree) for CSS syntax validation

# 0.0.2
- Added rule `comment-no-empty`

# 0.0.1

- Initial development and set of rules.

