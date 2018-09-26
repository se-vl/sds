## Erforderliche Software

Auf den Labor-Rechnern ist die erforderliche Software bereits installiert!

1. [Visual Studio Code](https://code.visualstudio.com/download)
2. [Node.js](https://nodejs.org/en/download)
3. [Git](https://git-scm.com/download)

## git-Repository klonen

Git Bash oder Windows PowerShell **als Administrator** ausführen

```
C:\Users\Max> mkdir git
C:\Users\Max> cd git
C:\Users\Max\git> git clone https://bitbucket.org/lgv-g12/lgv.git

C:\Users\Max\git> cd lgv
C:\Users\Max\git\lgv>
```

## Node-Installation testen

```
C:\Users\Max\git\lgv> node -v
v8.y.z

C:\Users\Max\git\lgv> npm -v
5.y.z
```

## Konfiguration anpassen

Visual Studio Code aus der Kommandozeile heraus starten:

```
C:\Users\Max\git\lgv> code .
```

In der Datei `package.json` muss der Eintrag für `lgv-config` um `-public` ergänzt werden:

```diff
- "lgv-config": "git+https://bitbucket.org/lgv-g12/lgv-config.git",
+ "lgv-config": "git+https://bitbucket.org/lgv-g12/lgv-config-public.git",
```

In der Datei `portal/master/config.js` folgende Änderungen vornehmen, sonst wird die Landkarte nicht angezeigt:

```diff
- layerConf: "../node_modules/lgv-config/services-fhhnet-ALL.json",
+ layerConf: '../node_modules/lgv-config/services-internet.json',

- restConf: "../node_modules/lgv-config/rest-services-fhhnet.json",
+ restConf: '../node_modules/lgv-config/rest-services-internet.json',

- styleConf: "../node_modules/lgv-config/style_v2.json",
+ styleConf: "../node_modules/lgv-config/style.json",
```

In der Datei `modules/core/modelList/list.js` folgende Zeilen auskommentieren, sonst werden die Werkzeuge nicht angezeigt:

```diff
-    PrintV2 = require("modules/tools/print_/model"),
+ // PrintV2 = require("modules/tools/print_/model"),

-    return new PrintV2(attrs, options);
+ // return new PrintV2(attrs, options);
```

**Speichern der Änderungen** nicht vergessen!

## Master Portal installieren

```
C:\Users\Max\git\lgv> npm run installMasterportal

...

WARNING in configuration
The 'mode' option has not been set, webpack will fallback to 'production' for this value.
Set 'mode' option to 'development' or 'production' to enable defaults for each environment.
You can also set it to 'none' to disable any default behavior. Learn more: https://webpack.js.org/concepts/mode/


C:\Users\Max\git\lgv> npm install -g grunt-cli


C:\Users\Max\git\lgv> grunt less:bootstrapDev
Done, without errors.

C:\Users\Max\git\lgv> grunt less:bootstrapBuild
Done, without errors.
```

## Master Portal starten

```
C:\Users\Max\git\lgv> grunt server
```

(Die gängigen Browser werden darauf hinweisen, dass die Verbindung unsicher ist.)

Im Browser zu https://localhost:9001/portal/master durchklicken

## Das erste eigene Modul

https://bitbucket.org/lgv-g12/lgv/src/28b785547e0b5e56a4752bc4d82c979b6a389f16/doc/02_tutorial_new_module_scale_switcher.md
