# GT 1191 Starterkit Mini

Dies ist die abgespeckte Version des großen [GT1191 Starterkit](https://github.com/HAWK-GT1191/gt1191-starterkit). Während dieses vorkonfigiert ist und mit der Bildkonvertierung und -optimierung ausgestattet ist, ermöglicht dir das Mini einen einfachen Umgang mit [Sass](https://sass-lang.com/).

Das Starterkit Mini verwendet neben Sass auch [browser-sync](https://browsersync.io/), [postcss](https://postcss.org/), [autoprefixer](https://github.com/postcss/autoprefixer) und [cssnano](https://cssnano.co/).

## Voraussetzungen

Um mit dem Starterkit arbeiten zu können, musst du vorab Git und die Paketmanager Node.js und Yarn auf deinem Computer installieren:

[Zur Installationsanleitung](https://github.com/macx/starterguide.dev/blob/main/de/prerequisits.md)

Installiere dir anschließend bitte auch Sass:

```shell
$ npm install -g sass
```

## Neue Website anlegen

Lade dir die Dateien des Starterkits herunter und lege sie in dem Verzeichnis deiner neuen Website ab.

```shell
# Speichert die Dateien im aktuellen Verzeichnis
$ git clone --depth 1 https://github.com/HAWK-GT1191/gt1191-starterkit-mini.git .

# Speichert die Dateien in einem neuen Verzeichnis
$ git clone --depth 1 https://github.com/HAWK-GT1191/gt1191-starterkit-mini.git neue-website
```

## Entwicklung

Ist das Starterkit eingerichtet, kannst du mit der Entwicklung deiner Website anfangen. Der folgende Befehl startet einen Webserver, kompiliert das CSS und öffnet die Website im Browser. Dateiänderungen werden ohne Reload nachgeladen (HMR).

```shell
$ yarn dev
```

### Datei- und Verzeichnisstruktur

Folgende Verzeichnisse sind dabei zu beachten.

- `public`\
  Das ist das Hauptverzeichnis deiner Website. Hier findest du die `index.html`, sowie das automatisch generierte CSS. Lege hier bei Bedarf auch deine Bilder oder Fonts ab.
- `src`\
  Enthält die Stylesheet-Datei `styles.scss`, die das Starterkit in CSS umwaldet und im `public`-Verzeichnis ablegt. Hier findest du auch `_presets.scss`, die deine Website für Demo-Zwecke vorformatiert. Diese Datei kannst du löschen, weiterverwenden oder dir Teile daraus kopieren. Eingebunden wird diese über `@use` im Stylesheet.

## Alternative Entwicklung mit Sass

Die einfachste Methode, Sass zu verwernden, ist über die Kommandozeile. Das kannst du tun, wenn du Probleme mit den Befehlen `yarn` hast.

Der folgende Befehl wird deine Styles (`src/sass/styles.scss`) zu CSS kompilieren und hier ablegen: `public/css/styles.css`.

```shell
$ sass --watch src/sass:public/css
```

_Der optionale Paramter `--watch` sorgt dafür, dass bei jeder Änderung der Datei eine neue Version erstellt wird._

### Website veröffentlichen/versenden

Wenn du deine Website auf deinem eigenen Webserver veröffentlichen möchtest, muss diese einmal „gebacken” (build) werden. Folgender Befehl startet den Build-Prozess und legt das Ergebnis einer statischen Website im Verzeichnis `public` ab. Dessen Inhalt kannst du dann mit FTP oder SSH auf deinen Webserver hochladen.

```shell
$ yarn build
```
