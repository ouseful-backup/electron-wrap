#### electron-wrap

---

Package any local/static website folder (typically a `/public`) into a desktop application, electron/macOS. The process requires Node/npm installed on your machine.

To do so, `cd` to the folder that contains the files, and run:

```
bash <(curl -s https://raw.githubusercontent.com/ouseful-backup/electron-wrap/master/wrap.sh)
```

The script will ask for a name and a window size for the app. After that, the script will:

**➀** Download `package.json` and `index.js` from this repository

**➁** Install the dependencies (electron, express to serve the files)

**➂** Package the folder into an Electron executable

**➃** Cleanup the files it downloaded + `node_modules/`

---

Useful for prototyping, presenting, or for simple offline stuff.

## Building for a range of platforms

The electron application can be built for a range of different platforms by setting the command in the `package.json` file appropriately.

For example, to build for a Mac:

`electron-packager . --overwrite --prune --out=build --platform=darwin --arch=x64 --icon=icon-electron-wrap.icns`

To biuld for all platforms:

`electron-packager . --overwrite --prune --out=build --all --icon=icon-electron-wrap.icns`

See [electron/electron-packager](https://github.com/electron/electron-packager) for more detail.
