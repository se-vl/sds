## Erforderliche Software

1. https://code.visualstudio.com/download
2. https://nodejs.org/en/download
3. https://git-scm.com/download

## git-Repository klonen

Git Bash oder Windows PowerShell **als Administrator** ausführen

```
C:\Users\Max> mkdir git
C:\Users\Max> cd git
C:\Users\Max\git> git clone https://bitbucket.org/geowerkstatt-hamburg/masterportal.git

C:\Users\Max\git> cd masterportal
C:\Users\Max\git\masterportal>
```

## Node-Installation testen

```
C:\Users\Max\git\masterportal> node -v
v10.y.z

C:\Users\Max\git\masterportal> npm -v
6.y.z
```

## Masterportal installieren

```
C:\Users\Max\git\masterportal> npm install

npm WARN deprecated tsml@1.0.1: no longer maintained
npm WARN deprecated core-js@1.2.7: core-js@<2.6.8 is no longer maintained. Please, upgrade to core-js@3 or at least to actual version of core-js@2.
...
npm notice created a lockfile as package-lock.json. You should commit this file.
npm WARN mocha-webpack@2.0.0-beta.0 requires a peer of mocha@>=4 <=5 but none is installed. You must install peer dependencies yourself.
npm WARN optional SKIPPING OPTIONAL DEPENDENCY: fsevents@1.2.9 (node_modules\fsevents):
npm WARN notsup SKIPPING OPTIONAL DEPENDENCY: Unsupported platform for fsevents@1.2.9: wanted {"os":"darwin","arch":"any"} (current: {"os":"win32","arch":"x64"})

added 1263 packages from 1662 contributors and audited 15011 packages in 55.851s
found 0 vulnerabilities
```

## Masterportal starten

```
C:\Users\Max\git\masterportal> npm start
```

(Die gängigen Browser werden darauf hinweisen, dass die Verbindung unsicher ist.)

Im Browser zu https://localhost:9001/portal/master durchklicken

Anschließend die Url zu https://localhost:9001/portal/basic ändern

## Das erste eigene Modul

https://bitbucket.org/geowerkstatt-hamburg/masterportal/wiki/how_to_write_a_module
