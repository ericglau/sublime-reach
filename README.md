# sublime-reach

1. Install the [LSP package](https://github.com/sublimelsp/LSP) for Sublime Text.

2. Install the [Reach IDE package](https://github.com/chrisnevers/reach-ide-sublime) for Sublime Text.

2. Download [Reach VS Code extension](https://marketplace.visualstudio.com/items?itemName=reachsh.reach-ide) as a .vsix file, and unzip it as a zip file.

3. In Sublime Text, go to the **Preferences** menu → **Package Settings** → **LSP** → **Settings**. This will open the LSP package settings.

4. In _LSP.sublime-settings — User_, add the configuration for the Reach language server:

```
// Settings in here override those in "LSP/LSP.sublime-settings"
{
  "clients": {
    "reach-language-server": {
      "enabled": true,
      "command": [
        "node",
        "/Users/eric/git/reach-ide/server/out/server.js",
        "--stdio"
      ],
      "languageId": "Reach",
      "syntaxes": ["Packages/Reach IDE/Reach.sublime-syntax"],
      "scopes": ["source.rsh"],
      "settings": {
        "reachide": {
          "maxNumberOfProblems": 100,
          "executableLocation": "/Users/eric/reach/tut/reach"
        }
      }
    }
  },
  "log_debug": true,
  "log_stderr": true,
    "auto_show_diagnostics_panel": "always",
    "show_code_actions_bulb": true
}
```
5. Change _/Users/eric/reach/tut/reach_ to the location of your Reach project. It **must** be an absolute path.  
6. Change _/Users/eric/git/reach-ide/server/out/server.js_ to the real location of the server.js file. It **must** be an absolute path.  
7. Restart Sublime.

