# Stylelint

In VSCode, to fix all fixable errors, open the Command Palette and choose *"Stylelint: Fix all auto-fixable problems"*

- Install [VSCode Stylelint plugin](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)
- Clone repo to your computer (eg `/Users/jeanine.schoessler/code/stylelint`)
- cd to `stylelint` and `npm install`
 

## ExampleVS Code config:

```json
{
  ...
  "stylelint.snippet": [
      "css",
      "less",
      "postcss",
      "scss"
    ],
    "stylelint.validate": [
      "css",
      "less",
      "postcss",
      "scss"
    ],
    "stylelint.configFile": "/Users/jeanine.schoessler/code/stylelint/.stylelintrc.json"
    ...
}
```
