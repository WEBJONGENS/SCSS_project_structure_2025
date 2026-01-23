# Handleiding Webjongens SCSS-compiler & SCSS-projectstructuur 2025
## Installatie van de SCSS-compiler
(alleen bij het opnieuw instellen van vs code)

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
   "liveSassCompile.settings.generateMap": false
   ```

3. Klik in de onderste commandobalk van VS Code op het oog-icoon “Watch SASS”

---

## Bestanden automatisch uploaden

1. Open de SFTP-configuratie van je project en voeg de volgende code toe:  
   (*Een watcher zodat wijzigingen in CSS-bestanden worden herkend en geüpload*)

   ```json
   {
      "name": "web** domain.nl",
      "host": "web**.texelhosting.nl",
      "protocol": "ftp",
      "port": 21,
      "username": "username",
      "password": "password",
      "remotePath": "/public_html/",
      "uploadOnSave": true,
      "useTempFile": false,
      "openSsh": false,
      "ignore": [
        "**/.vscode",
        "**/settings.json",
        "**/sftp.json",
        ".git",
        ".DS_Store"
          ],
      "watcher": {
            "files": "**/*.{css,js,html,php}",
            "autoUpload": true,
            "autoDelete": false
         }
   } 
   ```

   ---

# SCSS-projectstructuur 2025
   ```
templates/yootheme_custom/scss/
├── custom.scss
├── blokken/
│   ├── _cookiesCopyright.scss
│   ├── _hero_section.scss
│   ├── _index.scss
├── globals/
│   ├── _boilerplate.scss
│   ├── _buttons.scss
│   ├── _colors.scss
│   ├── _headings.scss
│   ├── _index.scss
│   ├── _typography.scss
├── util/
│   ├── _breakpoints.scss
│   ├── _fontsizes.scss
│   ├── _functions.scss
│   ├── _index.scss
   ```

## custom.scss 📄

Hier worden de mappen `globals` en `blocks` geforward. (Hoofdindex)

## blokken – Map 📁

Hier wordt voor elk YooTheme-blok een eigen `.scss`-bestand aangemaakt.  
Als je een nieuw `.scss`-bestand aanmaakt, moet je in `_index.scss` een `@forward` invoegen.

## globals – Map 📁

In deze map staan alle bestanden die globaal in het hele project beschikbaar zijn.

### _boilerplate.scss 📄  
**De “kookplaat”.** Hier kun je code invoegen die overal beschikbaar moet zijn,  
zoals styling voor links, `.tekstblok`, enzovoort.

### _buttons.scss 📄  
Hier worden de mixins voor knoppen gedefinieerd.

### _colors.scss 📄  
Hier worden de variabelen voor kleuren gedefinieerd.

### _headings.scss 📄  
Hier worden de mixins voor headings gedefinieerd.

### _index.scss 📄  
Dit is de index voor de map `globals`.  
Als je een nieuw SCSS-bestand aanmaakt, moet je hier een `@forward` invoegen.

### _typography.scss 📄  
Hier worden fonts geladen en de mixins voor fonts gedefinieerd.

## util – Map 📁

In deze map staan onze technische bestanden. Font-size berekeningen, breakpoints, formules, enzovoort.

### _fontsizes.scss 📄  
Hier definiëren we de mixins voor lettergroottes en regelhoogtes met `clamp()`.

**WJ - Clamp Calculator van Thomas: 🧮**
https://tom-mate-o.github.io/min-max-calculator-nested/  


### _functions.scss 📄  
Hier worden de functies `pxToRem` en `pxToEm` gedefinieerd, enzovoort.  
Je hoeft hier niets aan te passen.

### _index.scss 📄  
Dit is de index voor de map `utils`.  
Als je een nieuw SCSS-bestand aanmaakt, moet je hier een `@forward` invoegen.

