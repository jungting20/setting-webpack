# vscode의 크롬 디버거를 사용
-typescript,webpack,크롬디버거 연동

# package-json
```
{
  "name": "mytodolist",
  "version": "1.0.0",
  "description": "",
  "main": "webpack.config.js",
  "dependencies": {
    "awesome-typescript-loader": "^5.2.1",
    "css-loader": "^3.0.0",
    "source-map-loader": "^0.2.4",
    "ts-loader": "^6.0.4",
    "tslint": "^5.18.0",
    "tslint-loader": "^3.5.4",
    "typescript": "^3.5.2",
    "webpack": "^4.35.2"
  },
  "devDependencies": {
    "webpack-cli": "^3.3.5",
    "webpack-dev-server": "^3.7.2"
  },
  "scripts": {
    "build": "webpack",
    "watch": "webpack --watch",
    "dev": "webpack-dev-server"
  },
  "author": "",
  "license": "ISC"
}
```
# tsconfig.json
```
{
  "compilerOptions": {
    "target": "es5",
    "module": "es6",
    "outDir": "dist",
    "sourceMap": true
  },
  "include": ["src/**/*/"]
}
```
# webpack.config.js
```
const path = require('path');

module.exports = {
  entry: './src/app.ts',
  module: {
    rules: [
      {
        test: /\.tsx?$/,
        use: 'ts-loader',
        exclude: /node_modules/
      }
    ]
  },
  devtool: 'source-map',
  devServer: {
    contentBase: path.join(__dirname, 'dist'),
    compress: true,
    port: 9000
  },
  resolve: {
    extensions: [ '.tsx', '.ts', '.js' ]
  },
  output: {
    filename: 'bundle.js',
    path: path.resolve(__dirname, 'dist')
  }
};
```

# ./vscode/launch.json
```
{
    "version": "0.2.0",
    "configurations": [
        {
            "name": "Launch Chrome against localhost, with sourcemaps",
            "type": "chrome",
            "request": "launch",
            "url": "http://localhost:9000",
            "sourceMaps": true,
            "webRoot": "${workspaceRoot}",
            "sourceMapPathOverrides": {
                "webpack:///./*": "${webRoot}/*"
            }
        }
    ]
}
```
