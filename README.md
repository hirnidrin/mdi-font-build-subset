# mdi-font-build-subset

[![JavaScript Style Guide](https://img.shields.io/badge/code_style-standard-brightgreen.svg)](https://standardjs.com) [![License: Unlicense](https://img.shields.io/badge/license-Unlicense-blue.svg)](http://unlicense.org/)

## Synopsis

Dev helper package to build a reduced version of the [Material Design Icons](https://materialdesignicons.com/) webfont:
* Skips ttf and eot fonts, only generates woff and woff2 fonts and matching css - that's enough for the modern web. 
* The font contains only the given subset of icons - can save a lot of space.

## Define, build, use

### Generate a new, reduced mdi webfont
1. Prerequisite: Have a working [Node.js](https://nodejs.org/) environment. 
1. `cd` into this dir, run `npm install` or `yarn install` to load the dev dependencies.
1. Add the names of the icons you want to the `./subset.json` file. Leave the top 3 there, they are required for the `./dist/index.html` sample page.
1. `npm build` or `yarn build` creates the fonts, css, and sample page in the `./dist` folder. 
1. Optional: `cd dist`, run `http-server` and check the sample page containing your icon selection at `http://localhost:8080`.

### Use the font in an app
1. From `./dist`, copy the `css` and `fonts` folder as peers into the app assets folder.
1. Include the `css/materialdesignicons.css` into the app css structure.
1. Accessing the icons in the reduced webfont is the same as with the full mdi font.

## Notes
* The package is basically a clone of the original `@mdi/font-build` package. 2 files have been slightly adapted:
  * `./bin/index.js`
  * `./src/scss/_path.scss`
* In addition to `./dist`, the build also creates an `./icon` folder that contains the specified icon svg files. You can safely delete that folder after a successful build.

## Credits
Full credits go to the creators and contributors of the [@mdi/font-build](https://www.npmjs.com/package/@mdi/font-build) package, released under the MIT license. My additions make it worse.
