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
- layerConf: "/lgv-config/services-fhhnet-ALL.json",
+ layerConf: '/lgv-config/services-internet.json',

- restConf: "/lgv-config/rest-services-fhhnet.json",
+ restConf: '/lgv-config/rest-services-internet.json',

- styleConf: "/lgv-config/style_v2.json",
+ styleConf: "/lgv-config/style.json",
```

In der Datei `modules/core/modelList/list.js` folgende Zeilen auskommentieren, sonst werden die Werkzeuge nicht angezeigt:

```diff
-    import PrintV2 from "../../tools/print_/model";
+ // import PrintV2 from "../../tools/print_/model";


-    return new PrintV2(attrs, options);
+ // return new PrintV2(attrs, options);
```

**Speichern der Änderungen** nicht vergessen!

## Master Portal installieren

```
C:\Users\Max\git\lgv> npm install
```

## Aktualisieren der Abhängigkeiten

```
C:\Users\Max\git\lgv> npm update
```

## Master Portal starten

```
C:\Users\Max\git\lgv> npm start
```

(Die gängigen Browser werden darauf hinweisen, dass die Verbindung unsicher ist.)

Im Browser zu https://localhost:9001/portal/master durchklicken

## Tests durchführen

```
C:\Users\Max\git\lgv> npm test
```

## Masterportal zur Veröffentlichung bauen

```
C:\Users\Max\git\lgv> npm run build
```
Das Masterportal wird gebaut und in den Ordner dist/ abgelegt.

## Das erste eigene Modul

https://bitbucket.org/lgv-g12/lgv/src/28b785547e0b5e56a4752bc4d82c979b6a389f16/doc/02_tutorial_new_module_scale_switcher.md
