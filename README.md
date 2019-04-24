# react-env-config

mkdir my-app

cd my-app

npm init -y

mkdir app && touch index.js index.css


npm install --save-dev @babel/core @babel/preset-env @babel/preset-react webpack webpack-cli webpack-dev-server babel-loader css-loader style-loader html-webpack-plugin




### package.json

```
{
  "name": "recipes",
  "version": "1.0.0",
  "description": "",
  "main": "index.js",
  "babel": {
    "presets":[
      "@babel/preset-env",
      "@babel/preset-react"
    ]
  },
  "scripts": {
    "start": "webpack-dev-server --open"
   },
  "keywords": [],
  "author": "",
  "license": "ISC",
  "dependencies": {
    "react": "^16.8.6",
    "react-dom": "^16.8.6"
  },
  "devDependencies": {
    "@babel/core": "^7.4.3",
    "@babel/preset-env": "^7.4.3",
    "@babel/preset-react": "^7.0.0",
    "babel-loader": "^8.0.5",
    "css-loader": "^2.1.1",
    "html-webpack-plugin": "^3.2.0",
    "style-loader": "^0.23.1",
    "webpack": "^4.30.0",
    "webpack-cli": "^3.3.1",
    "webpack-dev-server": "^3.3.1"
  }
}
```

### webpack.config.js

```
var path = require('path')
var HtmlWebpackPlugin = require('html-webpack-plugin')


module.exports = {
    entry: './app/index.js',
    output:{
        path: path.resolve(__dirname, 'dist'),
        filename: 'index_bundle.js'
    },
    module:{
        rules:[
            {test: /\.(js)$/, use: 'babel-loader'},
            {test: /\.css$/, use: [ 'style-loader', 'css-loader']}
        ]
    },
    mode: 'development',
    // mode: 'production'
    plugins: [
        new HtmlWebpackPlugin({
            template: 'app/index.html'
        })
    ]
}

```


