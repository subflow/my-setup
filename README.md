# My Visual Studio Code setup

##### This is mostly for myself but if someone would be interested. Here it is.

The most important tool for me is the eslint config from Wes Bos.
He also have amazing courses check out his stuff at https://wesbos.com

And his ES Lint config here:
https://github.com/wesbos/eslint-config-wesbos

For the looks of vs code i use Victor Mono font, with ligatures and italic style. All configs included here.

1. First you need to make a global `.eslintrc` file:

ESLint will look for one in your home directory

- `~/.eslintrc` for mac
- `C:\Users\username\.eslintrc` for windows

In your `.eslintrc` file, it should look like this:

I have it looking like this:

```json
{
  "extends": ["wesbos"],
  "rules": {
    "no-console": "off",
    "prettier/prettier": [
      "error",
      {
        "trailingComma": "es5",
        "singleQuote": true,
        "printWidth": 120,
        "tabWidth": 2
      }
    ]
  }
}
```

2. Then run

```
npx install-peerdeps --global eslint-config-wesbos
```

3. Install the font [Victor Mono from here.](https://rubjo.github.io/victor-mono/)

4. Open up VS Codes Settings.json and replace everything with this.

My windows setup, i have a larger screen so i use larger font and different terminal:

```js
{
  "editor.fontSize": 17,
  "editor.tabSize": 2,
  "editor.wordWrap": "on",
  // These are all my auto-save configs
  "editor.formatOnSave": true,
  // turn it off for JS, we will do this via eslint
  "[javascript]": {
    "editor.formatOnSave": false
  },
  // tell the ESLint plugin to run on save
  "eslint.autoFixOnSave": true,
  "eslint.alwaysShowStatus": true,
  // Optional BUT IMPORTANT: If you have the prettier extension enabled for other languages like CSS and HTML, turn it off for JS since we are doing it through Eslint already
  "prettier.disableLanguages": ["js", "javascript", "javascriptreact"],
  "terminal.integrated.fontSize": 17,
  "terminal.integrated.shell.windows": "C:\\Program Files\\Git\\bin\\bash.exe",
  "terminal.integrated.fontFamily": "Consolas, 'Courier New', monospace"
  "editor.multiCursorModifier": "ctrlCmd",
  // "editor.formatOnSave": true,
  "prettier.singleQuote": true,
  "emmet.includeLanguages": {
    "javascript": "javascriptreact"
  },
  "emmet.triggerExpansionOnTab": true,
  "liveServer.settings.donotShowInfoMsg": true,
  "window.zoomLevel": 0,
  "mjml.autoPreview": true,
  // This is styling for the editor.
  // Font Victor mono, with ligatures on, and settings to select italic for certain types of text
  "editor.letterSpacing": 0.5,
  "editor.fontFamily": "Victor Mono",
  "editor.fontLigatures": true,
  "editor.fontWeight": "500",
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      {
        "name": "Comment",
        "scope": ["comment", "punctuation.definition.comment"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Keyword, Storage",
        "scope": ["Keyword", "Storage"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Keyword Control",
        "scope": ["keyword.control"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": "entity.other.attribute-name",
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "entity.name.method.js",
        "scope": ["entity.name.method.js"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Language methods",
        "scope": ["variable.language"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "HTML Attributes",
        "scope": [
          "text.html.basic entity.other.attribute-name.html",
          "text.html.basic entity.other.attribute-name"
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Decorators",
        "scope": [
          "tag.decorator.js entity.name.tag.js",
          "tag.decorator.js punctuation.definition.tag.js"
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "ES7 Bind Operator",
        "scope": [
          "source.js constant.other.object.key.js string.unquoted.label.js"
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Markup - Italic",
        "scope": ["markup.italic"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Markup - Bold-Italic",
        "scope": [
          "markup.bold markup.italic",
          "markup.italic markup.bold",
          "markup.quote markup.bold",
          "markup.bold markup.italic string",
          "markup.italic markup.bold string",
          "markup.quote markup.bold string"
        ],
        "settings": {
          "fontStyle": "bold"
        }
      },
      {
        "name": "Markup - Quote",
        "scope": ["markup.quote"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": "variable.other",
        "settings": {
        }
      },
      {
        "scope": "entity.name.function",
        "settings": {
        }
      },
      {
        "scope": "support.function",
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": "string",
        "settings": {
        }
      }
    ]
  },
}
```

And this is what i use on my macbook air.

```js
{
  "prettier.jsxSingleQuote": true,
  "prettier.singleQuote": true,
  // These are all my auto-save configs
  "editor.formatOnSave": true,
  // turn it off for JS, we will do this via eslint
  "[javascript]": {
    "editor.formatOnSave": false,
    "editor.defaultFormatter": "esbenp.prettier-vscode"
  },
  // tell the ESLint plugin to run on save
  "eslint.autoFixOnSave": true,
  // Optional BUT IMPORTANT: If you have the prettier extension enabled for other languages like CSS and HTML, turn it off for JS since we are doing it through Eslint already
  "prettier.disableLanguages": ["js"],
  "terminal.integrated.shell.osx": "/bin/bash",
  "terminal.integrated.fontFamily": "Consolas, 'Courier New', monospace",
  "editor.cursorBlinking": "solid",
  "editor.cursorStyle": "line",
  "editor.letterSpacing": 0.5,
  "editor.fontFamily": "Operator Mono",
  "editor.fontLigatures": true,
  "editor.fontWeight": "400",
  "editor.fontSize": 13,
  "window.zoomLevel": 0,
  // This is styling for the editor.
  // Font Victor mono, with ligatures on, and settings to select italic for certain types of text
  "mjml.autoPreview": true,
  "editor.tokenColorCustomizations": {
    "textMateRules": [
      {
        "name": "Comment",
        "scope": ["comment", "punctuation.definition.comment"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Keyword, Storage",
        "scope": ["Keyword", "Storage"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Keyword Control",
        "scope": ["keyword.control"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": "entity.other.attribute-name",
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "entity.name.method.js",
        "scope": ["entity.name.method.js"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Language methods",
        "scope": ["variable.language"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "HTML Attributes",
        "scope": [
          "text.html.basic entity.other.attribute-name.html",
          "text.html.basic entity.other.attribute-name"
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Decorators",
        "scope": [
          "tag.decorator.js entity.name.tag.js",
          "tag.decorator.js punctuation.definition.tag.js"
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "ES7 Bind Operator",
        "scope": [
          "source.js constant.other.object.key.js string.unquoted.label.js"
        ],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Markup - Italic",
        "scope": ["markup.italic"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "name": "Markup - Bold-Italic",
        "scope": [
          "markup.bold markup.italic",
          "markup.italic markup.bold",
          "markup.quote markup.bold",
          "markup.bold markup.italic string",
          "markup.italic markup.bold string",
          "markup.quote markup.bold string"
        ],
        "settings": {
          "fontStyle": "bold"
        }
      },
      {
        "name": "Markup - Quote",
        "scope": ["markup.quote"],
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": "variable.other",
        "settings": {}
      },
      {
        "scope": "entity.name.function",
        "settings": {}
      },
      {
        "scope": "support.function",
        "settings": {
          "fontStyle": "italic"
        }
      },
      {
        "scope": "string",
        "settings": {}
      }
    ]
  }
}
```

5. Finally the extensions i use:

- [Bracket Pair Colorizer](https://marketplace.visualstudio.com/items?itemName=CoenraadS.bracket-pair-colorizer)
- [ES7 React/Redux/GraphQL/React-Native snippets](https://marketplace.visualstudio.com/items?itemName=dsznajder.es7-react-js-snippets)
- [JavaScript (ES6) code snippets](https://marketplace.visualstudio.com/items?itemName=xabikos.JavaScriptSnippets)
- [language-stylus](https://marketplace.visualstudio.com/items?itemName=sysoev.language-stylus)
- [Live Server](https://marketplace.visualstudio.com/items?itemName=ritwickdey.LiveServer)
- [Prettier - Code formatter](https://marketplace.visualstudio.com/items?itemName=esbenp.prettier-vscode)
- [WakaTime](https://marketplace.visualstudio.com/items?itemName=WakaTime.vscode-wakatime)
- [vscode-styled-components](https://marketplace.visualstudio.com/items?itemName=jpoissonnier.vscode-styled-components)
- [Node.js Modules Intellisense](https://marketplace.visualstudio.com/items?itemName=leizongmin.node-module-intellisense)
- [vscode-icons](https://marketplace.visualstudio.com/items?itemName=vscode-icons-team.vscode-icons)

Cheers!
