# Setting.json



```text
{
    "workbench.activityBar.visible": false,
    "editor.tabSize": 2,
    "editor.tokenColorCustomizations": {
        "keywords": "#21bb03de",
        "strings": "#009991",
        "variables": "#a31fa3dd",
        "types": "#c97800",
        "functions": "#990000dd",
        "comments": "#333a",
        "textMateRules": [
            {
                "scope": [
                    // "entity.name.class",
                    // "entity.name.function",
                    // "entity.name.method",
                    // "entity.name.section",
                    // "entity.name.selector",
                    // "entity.name.tag",
                    // "entity.name.type",
                    "support.class",
                    // "support.constant",
                    // "support.function",
                    // "support.other",
                    // "support.type",
                    // "support.type.property-name",
                    // "support.variable",
                    // "variable",
                    // "variable.language",
                    // "variable.name",
                    // "variable.other",
                    // "variable.other.readwrite",
                    // "variable.parameter"
                ],
                "settings": {
                    "fontStyle": "underline italic",
                    "foreground": "#9b5d00"
                }
            },  
            {
                "scope": [
                    "keyword.control",
                    "storage.type",
                    "storage.modifier.async.js",
                    "storage.modifier.await.js"
                ],
                "settings": {
                    "fontStyle": "italic",
                }
            },  
            {
                "scope": [
                    "meta.tag entity.other.attribute-name",
                ],
                "settings": {
                    // "fontStyle": "italic",
                    "foreground": "#777777ff",
                }
            },  
            {
                "scope": [
                    "meta.object-literal.key.js",
                    "meta.objectliteral.js punctuation.definition.block.js",
                ],
                "settings": {
                    "fontStyle": "italic",
                    "foreground": "#1100ffbe",
                }
            },  
            {
                "scope": [
                    "meta.objectliteral.js punctuation.definition.block.js",
                ],
                "settings": {
                    "fontStyle": "italic",
                    "foreground": "#1100ffbe",
                }
            },  
            {
                "scope": [
                    "punctuation"
                ],
                "settings": {
                    "fontStyle": "",
                }
            },  
            {
                "scope": [
                    "meta.brace.round.js",
                    "punctuation.section.embedded.begin.js",
                    "punctuation.section.embedded.end.js",
                ],
                "settings": {
                    "foreground": "#777777ff",
                }
            },  
            {
                "scope": [
                    "punctuation.definition.block.js",
                ],
                "settings": {
                    "foreground": "#777777ff",
                }
            },  
            {
                "scope": [
                    "variable.language.this.js"
                ],
                "settings": {
                    "fontStyle": "italic",
                    "foreground": "#996300b5"
                }
            },  
            {
                "scope": [
                    "constant.language.undefined.js",
                ],
                "settings": {
                    "fontStyle": "italic",
                    "foreground": "#009991ff"
                }
            },  
            {
                "scope": [
                    "comment"
                ],
                "settings": {
                    "fontStyle": "italic",
                    "foreground": "#33333388"
                }
            },  
            {
                "scope": [
                    "keyword.operator.expression.instanceof.js"
                ],
                "settings": {
                    "fontStyle": "italic",
                }
            },  
            {
                "scope": [
                    "entity.name.type",
                    "entity.other.inherited-class"
                ],
                "settings": {
                    "foreground": "#9b5d00",
                }
            },  
            {
                "scope": [
                    "meta.import.js string.quoted.single.js",
                    "entity.name.import.go"
                ],
                "settings": {
                    "fontStyle": "italic",
                }
            },  
            {
                "scope": [
                    "meta.definition.variable.js",
                    "variable.parameter.js",
                    "variable.other.constant.js meta.definition.variable.js"
                ],
                "settings": {
                    "fontStyle": "underline",
                    // "foreground": "#ff01aa",
                }
            },  
            {
                "scope": [
                    "support.class.builtin.js",
                ],
                "settings": {
                    "fontStyle": "",
                }
            },  
            {
                "scope": [
                    "storage.type.function.arrow.js",
                    "punctuation.definition.block.js",
                    "meta.objectliteral.js meta.arrow.js punctuation.definition.block.js",
                    "meta.arrow.js punctuation.definition.parameters.begin.js",
                    "meta.arrow.js punctuation.definition.parameters.end.js",
                ],
                "settings": {
                    "fontStyle": "italic",
                    "foreground": "#21bb03de",
                }
            },  
        ],
    },
    "workbench.colorCustomizations": {
        "editor.background": "#fff",
        "editor.selectionBackground": "#00f5",
        "editorUnnecessaryCode.border": "#0f0",
        "editor.selectionHighlightBackground": "#00f3",
        "editor.selectionHighlightBorder": "#00f7", // same context with selected 
        "editor.wordHighlightBorder": "#00f7",
        "editor.wordHighlightBackground": "#00f3",
        "editorWarning.foreground": "#00a0ff",
        "editorError.border": "#0080ff",
        "editorError.foreground": "#ff0000",
        "editor.lineHighlightBackground": "#ff000032", // current line
        // "editor.inactiveSelectionBackground": "#30303077", // search all
        "editor.findMatchBackground": "#00cc44a8", //Current SEARCH MATCH
        "editor.findMatchBorder": "#00cc44a8", //Current SEARCH MATCH
        "editor.findMatchHighlightBackground": "#00cc44a8", //Other SEARCH MATCHES
        "editor.rangeHighlightBackground": "#f003", // search symbol
        // "editor.rangeHighlightBorder": "#f003", // search symbol
        "editorSuggestWidget.selectedBackground": "#f005" // suggestion selected 
    },
    "vim.foldfix": true,
    "editor.fontWeight": "700",
    "editor.fontFamily": "Source Code Pro,Input Mono, 'Courier New', monospacez",
    "jake.autoDetect": "off",
    "editor.suggestSelection": "first",
    "[javascript]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode",
        "editor.foldingStrategy": "indentation"
    },
    "[json]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "indentRainbow.colors": [
        "rgba(255,255,64,0.2)",
        "rgba(127,255,127,0.2)",
        "rgba(255,127,255,0.2)",
        "rgba(79,236,236,0.2)"
    ],
    "[html]": {
        "editor.defaultFormatter": "vscode.html-language-features"
    },
    "extensions.ignoreRecommendations": true,
    "workbench.statusBar.visible": true,
    "editor.renderControlCharacters": false,
    "editor.renderWhitespace": "none",
    "window.zoomLevel": 0,
    "workbench.sideBar.location": "left",
    "peacock.favoriteColors": [
        {
            "name": "Angular Red",
            "value": "#b52e31"
        },
        {
            "name": "Auth0 Orange",
            "value": "#eb5424"
        },
        {
            "name": "Azure Blue",
            "value": "#007fff"
        },
        {
            "name": "C# Purple",
            "value": "#68217A"
        },
        {
            "name": "Gatsby Purple",
            "value": "#639"
        },
        {
            "name": "Go Cyan",
            "value": "#5dc9e2"
        },
        {
            "name": "Java Blue-Gray",
            "value": "#557c9b"
        },
        {
            "name": "JavaScript Yellow",
            "value": "#f9e64f"
        },
        {
            "name": "Mandalorian Blue",
            "value": "#1857a4"
        },
        {
            "name": "Node Green",
            "value": "#215732"
        },
        {
            "name": "React Blue",
            "value": "#00b3e6"
        },
        {
            "name": "Something Different",
            "value": "#832561"
        },
        {
            "name": "Vue Green",
            "value": "#42b883"
        }
    ],
    "peacock.surpriseMeFromFavoritesOnly": true,
    "peacock.surpriseMeOnStartup": true,
    "peacock.affectTabActiveBorder": true,
    "peacock.affectAccentBorders": true,
    "editor.minimap.enabled": false,
    "breadcrumbs.enabled": true,
    "editor.suggest.maxVisibleSuggestions": 15,
    
    "emmet.includeLanguages": {
        "javascript": "javascriptreact"
    },
    "emmet.syntaxProfiles": {
        "javascript": "jsx"
    },
    "[jsonc]": {
        "editor.defaultFormatter": "esbenp.prettier-vscode"
    },
    "typescript.format.enable": false,
    "typescript.check.npmIsInstalled": false,
    "typescript.autoClosingTags": false,
    "typescript.format.insertSpaceAfterCommaDelimiter": false,
    "typescript.format.insertSpaceAfterFunctionKeywordForAnonymousFunctions": false,
    "typescript.format.insertSpaceAfterOpeningAndBeforeClosingNonemptyBraces": false,
    "typescript.format.insertSpaceAfterKeywordsInControlFlowStatements": false,
    "typescript.format.insertSpaceAfterSemicolonInForStatements": false,
    "typescript.format.insertSpaceBeforeAndAfterBinaryOperators": false,
    "typescript.preferences.renameShorthandProperties": false,
    "typescript.suggest.completeJSDocs": false,
    "typescript.reportStyleChecksAsWarnings": false,
    "typescript.suggest.autoImports": false,
    "typescript.suggest.paths": false,
    "typescript.suggestionActions.enabled": false,
    "typescript.suggest.enabled": false,
    "typescript.surveys.enabled": false,
    "typescript.validate.enable": false,
    "go.useLanguageServer": true,
    "markdown.preview.lineHeight": 16,
    "spotify.showSignInButton": false,
    "spotify.showSignOutButton": false,
    "spotify.showLyricsButton": false,
    "spotify.showMuteUnmuteVolumeButton": false,
    "spotify.showNextButton": false,
    "spotify.showPreviousButton": false,
    "eslint.run": "onSave",
    "spotify.statusCheckInterval": 2000,
    "workbench.colorTheme": "Quiet Light",
    "debug.console.lineHeight": 10,
    "editor.suggestLineHeight": 16,
    "editor.quickSuggestionsDelay": 200,
    "html.suggest.html5": false,
    "php.suggest.basic": false,
    "javascript.suggest.completeFunctionCalls": true,
    "debug.console.fontSize": 11,

    "commentBox.styles": {
        "defaultStyle": {
            "commentStartToken": "  // ",
            "commentEndToken": "  ",
            "leftEdgeToken": "  // #region ",
            "rightEdgeToken": "",
            "topEdgeToken": " -",
            "bottomEdgeToken": "",
            "topRightToken": "",
            "bottomLeftToken": "",
            "capitalize": false,
            "textAlignment": "left",
            "fillingToken": "",
            "boxWidth": 80,
        }
    },
    "workbench.fontAliasing": "auto",
    "editor.fontLigatures": true,
    "editor.foldingStrategy": "indentation",
    "editor.acceptSuggestionOnCommitCharacter": false,
    "javascript.updateImportsOnFileMove.enabled": "always",
    "markdown.preview.fontFamily": "SomeType Mono, -apple-system, BlinkMacSystemFont, 'Segoe WPC', 'Segoe UI', 'Ubuntu', 'Droid Sans', sans-serif",
    "indentRainbow.updateDelay": 2000,
    "editor.highlightActiveIndentGuide": false,
    "turboConsoleLog.addSemicolonInTheEnd": true,
    "workbench.editor.centeredLayoutAutoResize": false,
    "javascript.suggest.autoImports": false,
    "search.location": "panel",
    "window.newWindowDimensions": "inherit",
    "scm.alwaysShowProviders": true,
    "editor.lineHeight": 20,
    "editor.matchBrackets": false,
    "subtleBrackets.style": {
        "borderColor": "#f0fb",
        "borderWidth": "3px"
    },
    "importCost.timeout": 1000000,
    "editor.fontSize": 11.75,
    "typescript.disableAutomaticTypeAcquisition": true,
    "vim.autoindent": false,
    "editor.renderIndentGuides": false,
    "[go]": {
        "editor.insertSpaces": false,
        "editor.formatOnSave": false,
        "editor.codeActionsOnSave": {
          "source.organizeImports": false
        }
      }
}
```

