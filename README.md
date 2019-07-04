# setting-webpack

#package-json
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
