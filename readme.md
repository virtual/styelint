# Stylelint

Untested:

- Install [VSCode stylelint plugin](https://marketplace.visualstudio.com/items?itemName=stylelint.vscode-stylelint)
- Add package.json & .stylelintrc.json to a root-level directory where you will have all your code (eg `~/code`)
- `npm install -g`


Manually update `node_modules/stylelint-config-rational-order/package.json` per [Allohamora's forked repo](https://github.com/Allohamora/stylelint-config-rational-order/blob/master/package.json) and `npm update` within `stylelint-config-rational-order`

Add the language identifiers for the documents you want to validate to the extension's workspace or user settings using the stylelint.validate option.


`@ext:stylelint.vscode-stylelint`

Example VS Code config:

```json
{
  "stylelint.validate": ["css", "scss"]
}
```

[Migration notes 13 to 14](https://github.com/stylelint/vscode-stylelint#migrating-from-vscode-stylelint-0xstylelint-13x)