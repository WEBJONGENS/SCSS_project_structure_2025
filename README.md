## Installatie van de SCSS-compiler

1. Installeer de volgende VS Code-extensie:  
   [Live Sass Compiler](https://marketplace.visualstudio.com/items?itemName=glenn2223.live-sass)

2. Open je `settings.json` in VS Code en voeg de volgende code toe:

   ```json
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
   ```

3. Klik in de onderste commandobalk van VS Code op het oog-icoon “Watch SASS”

---

## Bestanden automatisch uploaden

1. Open de SFTP-configuratie van je project en voeg de volgende code toe:  
   (*Een watcher zodat wijzigingen in CSS-bestanden worden herkend en geüpload*)

   ```json
   "uploadOnSave": true,
   "useTempFile": false,
   "openSsh": false,
   "watcher": {
     "files": "**/*.{scss,sass,css,js,html,php}",
     "autoUpload": true,
     "autoDelete": false
   }
   ```
