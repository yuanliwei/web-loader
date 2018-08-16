# web-loader
load javascript or css files in browser by javascript

## load javascript or css
- basic use
  ```javascript
  const LoadES6 = require('web-loader');
  new LoadES6()
    .load("/src/js/jquery.js")
    .load("/jquery-ui.min.css")
    .wait(500)
    .then(()=>console.log('init!'))
    .load("/app.js")
    .then(()=>console.log('over!'))
  ```

## use load with config
- config.js
  ```javascript
  LoadES6.config({
    "jquery":[
      "https://cdn.bootcss.com/jquery/3.1.1/jquery.min.js"
    ],
    "jqueryui":[
      "https://cdn.bootcss.com/jqueryui/1.12.1/jquery-ui.structure.min.css",
      "https://cdn.bootcss.com/jqueryui/1.12.1/jquery-ui.theme.min.css",
      "https://cdn.bootcss.com/jqueryui/1.12.1/jquery-ui.min.js",
      "https://cdn.bootcss.com/jqueryui/1.12.1/jquery-ui.min.css"
    ]})
  ```
- script
  ```javascript
  const LoadES6 = require('web-loader');
  new LoadES6()
    .load("/config.js")
    .load("jquery", "jqueryui")
    .wait(500)
    .then(()=>console.log('init!'))
    .load("/app.js")
    .then(()=>console.log('over!'))
  ```
