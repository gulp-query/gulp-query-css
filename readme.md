## gulp-query-css
Plugin for [gulp-query](https://github.com/gulp-query/gulp-query)

Uses [cssnano](http://cssnano.co/) with autoprefixer for optimization

This plugin provides automatic source maps, copy, combine and rename CSS, autoprefixing and minification.
Write your CSS rules without vendor prefixes — autoprefixer will do everything itself

```
npm install gulp-query gulp-query-css
```

### Example
Paste the code into your `gulpfile.js` and configure it
```javascript
let build = require('gulp-query')
  , css = require('gulp-query-css')
;
cocktail(function (query) {
    query.plugins([css])
      .css(['1.css','2.css'],'css/12.css','onetwo')
      .css('css_source/*.css','css/')

      .css({
        from: 'css_source/*.css',
        to: 'css/big.css',
        name: 'big'
      })
      ;
});
```
And feel the freedom
```
gulp
gulp --production // For production
gulp watch // Watching change
gulp css // Only for css
gulp css:onetwo
gulp css:big watch
...
```

### Options
```javascript
.css({
    name: "task_name", // For gulp css:task_name 
    from: 'css_source/*.css', // ['1.css','2.css']
    to: "css/",
    source_map: true,
    source_map_type: 'inline',
    full: false, // if set true is without compress in prod
    autoprefixer: {
      browsers: ["> 1%", "last 2 versions"],
    }
})
```