
![Electron webview](screenshot.png)


#### Build MacOS, Windows and Linux package from the terminal

MacOS

```bash
$ electron-packager . --overwrite --platform=darwin --arch=x64 --icon=assets/icons/mac/icon.icns --prune=true --out=release-builds
```

Windows

```bash
$ electron-packager . --overwrite --asar=true --platform=win32 --arch=ia32 --icon=assets/icons/win/icon.ico --prune=true --out=release-builds --version-string.CompanyName=CE --version-string.FileDescription=CE --version-string.ProductName="Electron Webview"
```

Linux (Ubuntu)

```bash
$ electron-packager . --overwrite --platform=linux --arch=x64 --icon=assets/icons/png/1024x1024.png --prune=true --out=release-builds
```

#### Shortcuts

To make it easier to create new builds, scripts are added in `package.json`.

Now you can run:

```bash
$ npm run package-mac
```

```bash
$ npm run package-win
```

```bash
$ npm run package-linux
```

## Mac installer

To create a DMG installer for our Electron app we can use the [electron-installer-dmg](https://github.com/mongodb-js/electron-installer-dmg) package.

To create a DMG installer you first need to package the app as we saw in the Application chapter above.

### Install

```bash
# For use in npm scripts
$ npm install electron-installer-dmg --save-dev

# For use from cli
$ npm install electron-installer-dmg -g
```

### Create the DMG

```bash
$ electron-installer-dmg ./release-builds/Electron\ webview-darwin-x64/Electron\ webview.app electron-webview --out=release-builds --overwrite --icon=assets/icons/mac/icon.icns
```

An `electron-webview.dmg` file is now created in the `release-builds` folder.

### Shortcuts

To make it easier to create new DMG installer, a script is added in `package.json`.

Now you can run:

```bash
$ npm run create-installer-mac
```

## Source

Based on:

- [Electron Packager tutorial](https://www.christianengvall.se/electron-packager-tutorial/)
- [Browser](https://github.com/hokein/electron-sample-apps/tree/master/webview/browser)
- [Printing](https://github.com/hokein/electron-sample-apps/tree/master/printing)

## License

[MIT](LICENSE.md)
