# SCSS_project_structure_2025

## Installation SCSS Complier

1. Installiere folgende VS Code Extension:
https://marketplace.visualstudio.com/items?itemName=glenn2223.live-sass
2. Oeffne deine settings.json in VS Code und fuege folgenden Code hinzu:

```
  "liveSassCompile.settings.autoprefix": [],
  "liveSassCompile.settings.forceBaseDirectory": "/templates/yootheme_custom/scss",
  "liveSassCompile.settings.formats": [
    {
      "format": "expanded",
      "extensionName": ".css",
      "savePath": "/templates/yootheme_custom/css",
      "savePathReplacementPairs": null
    }
  ],
  "liveSassCompile.settings.generateMap": false,
  "workbench.iconTheme": "material-icon-theme"
}
```

1. Klicke in der unteren Befehlszeile von VS Code auf das Augen Icon “Watch SASS”

## Files automatisch uploaden

1. Oefnne die SFTP Config deines Projekts und fuege folgenden Code hinzu:
(Ein Watcher, damit Anpassungen im CSS file erkannt und upgeloaded werden)

```
"uploadOnSave": true,
  "useTempFile": false,
  "openSsh": false,
  "watcher": {
    "files": "**/*.{scss,sass,css,js,html,php}",
    "autoUpload": true,
    "autoDelete": false
  }
```
