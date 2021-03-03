# sublime-reach

1. Install the [LSP package](https://github.com/sublimelsp/LSP) for Sublime Text.

2. Install the [Reach IDE package](https://github.com/chrisnevers/reach-ide-sublime) for Sublime Text.

2. Download Reach language server and extract it. TODO

3. In Sublime Text, go to the **Preferences** menu → **Package Settings** → **LSP** → **Settings**. This will open the LSP package settings.

4. In _LSP.sublime-settings — User_, add the configuration for the Reach language server:

```
{
  "clients": {
    "reach-language-server": {
      "enabled": true,
      "command": [
        "node",
        "/Users/eric/git/reach-ls/extension/server/out/server.js",
        "--stdio"
      ],
      "languageId": "Reach",
      "syntaxes": ["Packages/Reach IDE/Reach.sublime-syntax"],
      "scopes": ["source.rsh"]
    }
  },
  "log_debug": true,
  "log_stderr": true,
}
```

   Change _/Users/eric/git/reach-ls/extension/server/out/server.js_ to the real location of the server.js file. It **must** be an absolute path.

