# DOS

A DOS emulator with mobile compatibility designed for running in pure JavaScript pre-ECMAScript 2015 (no WebAssembly). Simply open the link below, click the red icon, and select the `ZIP` file from your computer; it will be decompressed in the C drive and DOSBox will start automatically and try to run `AUTORUN.BAT`. If you create your own custom mapper file, add it to the `ZIP` file as `MAPPER.MAP`.

## Links:

- [DOS emulator](https://lrusso.github.io/DOS/DOS.htm)
- [Demo booting a sample game](https://lrusso.github.io/DOS/DOS.htm?demo)

## Screenshots:

![alt screenshot1](https://lrusso.github.io/DOS/SCREENSHOT1.jpg)

![alt screenshot2](https://lrusso.github.io/DOS/SCREENSHOT2.jpg)

![alt screenshot3](https://lrusso.github.io/DOS/SCREENSHOT3.jpg)

![alt screenshot4](https://lrusso.github.io/DOS/SCREENSHOT4.jpg)

## How to use it:

Examples of loading local and online files can be found [here](https://github.com/lrusso/DOS/blob/main/DOS.htm#L139-L162) and [here](https://github.com/lrusso/DOS/blob/main/DOS.htm#L190-L208).

```js
embedDOSBox({
  container: "game",
  name: "Doom",
  zipFile: zipFile,
  soundEnabled: true,
  showMobileControls: true,
  backText: "BACK",
  soundText: "SOUND",
  saveText: "SAVE",
  cbStarted: function cbStarted() {
    console.log("Emulator started.")
  },
})
```

| Parameter          |    Type     | Required | Default value | Description                |
| :----------------- | :---------: | :------: | :-----------: | :------------------------- |
| container          |   string    |   yes    |       –       | Target element ID.         |
| name               |   string    |   yes    |       –       | Game name.                 |
| zipFile            | ArrayBuffer |   yes    |       –       | ZIP file with the game.    |
| soundEnabled       |   boolean   |    no    |     true      | Initial sound state.       |
| showMobileControls |   boolean   |    no    |     false     | Show mobile controls.      |
| backText           |   string    |    no    |     BACK      | Text for the Back button.  |
| soundText          |   string    |    no    |     SOUND     | Text for the Sound button. |
| saveText           |   string    |    no    |     SAVE      | Text for the Save button.  |
| cbStarted          |  function   |    no    |       -       | Called on emulator start.  |

## Special keys:

| Action                       | macOS Shortcut | Windows Shortcut | Safari Shortcut |
| :--------------------------- | :------------: | :--------------: | :-------------: |
| Download hard disk           |  Command + 1   |     Ctrl + 1     |    Ctrl + 1     |
| Download file from hard disk |  Command + 2   |     Ctrl + 2     |    Ctrl + 2     |
| Toggle sound                 |  Command + 3   |     Ctrl + 3     |    Ctrl + 3     |
| Fullscreen mode              |  Command + F   |     Ctrl + F     |    Ctrl + F     |

## Author's note:

This emulator is compatible with both Android and iOS devices. However, WebKit on iOS has historically lagged behind; for instance, it took nearly a decade for Apple to allow developers to set a custom download filename for an `a` tag. This feature was implemented recently on iOS, so you can now download the game state. Another three iOS quirks: 1) if a slow connection causes the script to take several seconds to load, WebKit may fail to initialize the AudioContext; 2) if you send Safari to the background and return to it, there will be no audio; 3) if you click on the file selector and it takes you several seconds to choose a ROM file, there will be no audio. In any case, a manual tap on the screen is required to enable or re-enable the audio.

## Differences with the original project:

- Transpiled JS to pre-ES2015 via `node ConverterES5.js dosbox.js`.

## This is a modified version of em-dosbox:

https://github.com/lrusso/em-dosbox

**NOTE:** Emscripten 4.0.23 was used to build the emulator.

## Virtual joystick code:

https://github.com/lrusso/VirtualJoystick
