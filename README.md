# vuenews

> A simple news list powered by [newsapi.org](https://newsapi.org)

Followed instruction on [youtubue clip](https://www.youtube.com/watch?v=p-7Zi9xYt2M) by CodingTheSmartWay.com

Note: There's some wrong syntax of ES6 in the video, so I reproduce them.

You MUST create `prod.env.js` file in `config` folder and set API Key.

```javascript
# config/prod.env.js

module.exports = {
  NODE_ENV: '"production"',
  NEWSAPI_KEY: '"YOUR API KEY"'
}
```

## Build Setup

``` bash
# install dependencies
npm install

# serve with hot reload at localhost:8080
npm run dev

# build for production with minification
npm run build

# build for production and view the bundle analyzer report
npm run build --report
```

For detailed explanation on how things work, checkout the [guide](http://vuejs-templates.github.io/webpack/) and [docs for vue-loader](http://vuejs.github.io/vue-loader).
