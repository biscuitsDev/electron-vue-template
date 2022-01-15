# Electron Vue Template

A starter template that's bundled together with **VueJS 3.x**, **Electron 16.x**, **ViteJS** and **Electron Builder** 👌

## About

This project got inspired by [electron-vue](https://github.com/SimulatedGREG/electron-vue)

This template uses [ViteJS](https://vitejs.dev) for the development server providing HMR (Hot Reload) while developing your Electron app.\
Building the Electron application is done by [Electron Builder](https://www.electron.build/), making your application cross-platform and easily distributable, it also supports cross-platform compilation!

This template doesn't come with any unnecessary dependencies and is unopinionated, so you can start developing your Electron / Vue applications however you want.

## Getting started

Execute the following commands to start developing straight away:

```bash
git clone https://github.com/Deluze/electron-vue-template
cd electron-vue-template
npm install
npm run dev
```

That's all!

## Commands

```bash
npm run dev # starts application with hot reload
npm run build # builds application

# OR

npm run build:win # uses windows as build target
npm run build:mac # uses mac as build target
npm run build:linux # uses linux as build target
```

Optional configuration options can be found in the [Electron Builder CLI docs](https://www.electron.build/cli.html).

## Project Structure

```bash
- root
  - config/
    - vite.js # ViteJS configuration
    - electron-builder.json # Electron Builder configuration
  - scripts/ # all the scripts used to build or serve your application, change as you like.
  - src/
    - main/ # Main thread (Electron application source)
    - renderer/ # Renderer thread (VueJS application source)
```

## Using static files

If you have any files that you want to copy over to the app directory after installation, you will need to add those files in your `src/main/static` directory.

#### Referencing static files from your main process

```js
/* Assumes src/main/static/yourFile.txt exists */

const { app } = require('electron');
const FileSystem = require('fs');
const Path = require('path');

const path = Path.join(app.getAppPath(), 'static', 'yourFile.txt');
const contents = FileSystem.readFileSync(path);
```
