# GT 1191 Starterkit Mini

Dieses Repository soll dir den Umgang mit [Sass](https://sass-lang.com/) erleichtern und kommt in zwei Versionen. Als Leitfaden, wie die Sass manuell über die Kommandozeile bedienen kannst, als auch als Workflow, die mehr Automatismen nutzen möchten.

Für fortgeschrittene Nutzer oder höhere Ansprüche haben wir dir das [GT1191 Starterkit](https://github.com/HAWK-GT1191/gt1191-starterkit) zur Verfügung gestellt, mit dem du blitzschnell Single-Page-Websites oder Multipager erstellen kannst.

## Voraussetzungen

1. Lade dir den [Node.js-Installer](https://nodejs.org/en/download/) für dein System runter und führe die Installation durch.
2. Öffne das Terminal (Mac) bzw. die PowerShell (Windows).
3. Installiere sass systemweit und kontrolliere die erfolgreiche Einrichtung durch folgende Befehle (Ohne `$`):

```shell
$ sudo npm install -g sass
$ npm -v && sass --version
```

> Unter Windows musst du die Ausführungsrichtlinien ändern, damit Skripte wie yarn ausgeführt werden dürfen. Gehe dazu in die Einstellungen unter „Datenschutz und Sicherheit / Entwickler / PowerShell” und bestätige dies mit einem Klick auf den Button „Anwenden”.

Alternativ kannst du Sass unter Windows auch mit [Chcolatey](https://chocolatey.org/) oder unter MacOS mit [Homebrew](https://brew.sh/) installieren:

```shell
// Chcolatey
choco install sass

// Homebrew
brew install sass/sass/sass
```

## Entwicklung

Es gibt zwei Verzeichnisse, die für dich wichtig sind:

- `src`\
  ist dein Arbeitsverzeichnis und enhält die Sass-Dateien.
- `public`\
  ist das Hauptverzeichnis deiner Website mit einer `index.html`, sowie der anschließend von dir kompilierten CSS-Dateien im Unterverzeichnis `css`.

### Sass über die Kommandozeile

Die einfachste Methode, Sass zu verwernden, ist über die Kommandozeile. Gebe dazu ins Terminal und trage dort folgenden Befehl ein. Dieser kompiliert Sass zu CSS im Zielverzeichnis `public`.

Anders gesagt: Du arbeitst stets mit der Sass-Datei `src/sass/styles.scss`, die bei jeder Änderung als CSS-Datei in `public/css/styles.css` umgewandelt (kompiliert) wird.

```shell
$ sass --watch src/sass:public/css
```

_Der optionale Paramter `--watch` sorgt dafür, dass bei jeder Änderung der Datei eine neue Version erstellt wird._

### Mit diesem Repository arbeiten

Statt Sass manuell über die Kommandozeile zu verwenden, kannst du den Workflow dieses Repository nutzen. Dies verwendet neben Sass auch [browser-sync](https://browsersync.io/), [postcss](https://postcss.org/), [autoprefixer](https://github.com/postcss/autoprefixer) und [cssnano](https://cssnano.co/), die sich über Befehle starten lassen.

In Kurzform, wie du dieses Repostiroy bei dir installierst:

```shell
$ git clone https://github.com/HAWK-GT1191/gt1191-sass.git meine-website
$ cd meine-website
$ yarn install
```

Mit `yarn dev` startest du den Server, der deine Website im Browser öffnet und Dateiänderungen überwacht. Mit `yarn build` erstellst du am Ende deiner Arbeit eine Version zur Bereitstellung auf deinem Webhost.
