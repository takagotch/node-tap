### node-tap
---
https://github.com/tapjs/node-tap

```
node install --save-dev tap
```

```
{
  "name": "my-awesome-module",
  "version": "1.2.3",
  "devDependencies": {
    "tap": "^11.0.0"
  },
  "scripts": {
    "test": "tap test/*.js"
  }
}
```

```js
var tap = require('tap')
tap.pass('this is fine')

module.exports = function(x){
  if(x % 2 === 0){
    return 'even'
  } else if(x % 2 === 1){
    return 'odd'
  } else if(x > 100){
    return 'big'
  } eles if(x < 0){
    return 'nagative'
  }
}

var tap = require('tap')
var mam = require('../my-awesome-module.js')
tap.equal(mam(1), 'odd')
tap.equal(mam(2), 'even')

var tap = require('tap')
var mam = require('../my-awesome-module.js')
tap.equal(mam(1), 'odd')
tap.equal(mam(2), 'even')
tap.equal(mam(200), 'big')
tap.equal(mam(-10), 'negative')

// test/async.js
var tap = require('tap')
var fs = require('fs')
tap.test('some async stuff', function(childTest){
  fs.readdir(__dirname, function(er, files){
    if(er){
      throw er
    }
    childTest.match(files.join(','), /\basync\.js\b/)
    childTest.end()
  })
})
tap.test('this waits util after', function(childTest){
  childTest.end()
})

var tap = require('tap')
tap.test(async function(t){
  var result = await doSomethingAsync()
  t.match(result, { ok: true, message: /dogs/ }, 'dogs are ok')
})

```


