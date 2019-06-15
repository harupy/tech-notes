# Chrome Extension

## Webpack and Babel

```console
npm install webpack webpack-cli babel-loader @babel/core @babel/preset-env --save-dev
```

webpack.config.js

```javascript
const path = require('path');

module.exports = {
  mode: 'development',
  entry: {
    file1: './src/js/file1.js',
    file2: './src/js/file2.js',
  },
  output: {
    path: path.join(__dirname, 'src/dist/'),
    filename: '[name].js',
  },
  module: {
    rules: [
      {
        test: /\.js$/,
        exclude: /node_modules/,
        use: [
          {
            loader: 'babel-loader',
            options: {
              presets: [['@babel/preset-env', { modules: false }]],
            },
          },
        ],
      },
    ],
  },
};
```
