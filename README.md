# moment-locales-vite-plugin

> Easily remove unused Moment.js locales when building with webpack

Forked from [moment-locales-webpack-plugin](https://github.com/iamakulov/moment-locales-webpack-plugin) and converted with [webpack-to-vite](https://github.com/originjs/webpack-to-vite) with:  
```
webpack-to-vite /home/giovanni/Documents/Dev/moment-locales-webpack-plugin --projectType webpack --entry index.js
```

## Install

```sh
npm install --save-dev @giovannilaperna/moment-locales-vite-plugin
```

## Usage

#### `vite.config.js`
```js
import { defineConfig } from 'vite'
import MomentLocalesPlugin from ' @giovannilaperna/moment-locales-vite-plugin'

export default defineConfig({
  plugins: [
    MomentLocalesPlugin({
      localesToKeep: ['es', 'it']
    })
  ]
})
```

## Plugin Options

### **`localesToKeep: String[]`**

An array of locales to keep bundled (other locales would be removed).

Locale names follow Moment.js behavior – if a specific locale name (e.g. `ru-ru`) is absent, but a more generic locale (`ru`) is available, the generic one will be kept bundled.

### **`ignoreInvalidLocales: Boolean`**

A flag to ignore invalid or unsupported locales in the `localesToKeep` array.

Be careful! A typo in the `localesToKeep` array with this flag enabled will silently exclude the desired locale from your bundle.


## License

MIT © <a href="https://learntheropes.vercel.app">Giovanni La Perna</a>
