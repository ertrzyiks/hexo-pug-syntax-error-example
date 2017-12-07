# hexo-pug-syntax-error-example

The example repository showing that the syntax error in the Hexo theme does not affect exit code from `hexo generate`.

Related to: https://github.com/hexojs/hexo/pull/2886

## Installation

Use:
```
yarn install
```

## Reproduce issue

```
yarn build
echo $?
```


The current output:
```
> yarn build
yarn build v0.27.5
$ hexo generate
INFO  Start processing
ERROR Process failed: layout/index.pug
Error: /Users/mateuszderks/workspace/hexo-pug-syntax-error-example/themes/my-theme/layout/index.pug:2:1
    1| a(
  > 2| 
-------^

The end of the string reached with no closing bracket ) found.
    at makeError (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-error/index.js:32:13)
    at Lexer.error (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:52:15)
    at Lexer.bracketExpression (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:219:14)
    at Lexer.attrs (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:960:24)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1266:23)
    at Lexer.advance (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1303:15)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1266:23)
    at Lexer.getTokens (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1322:12)
    at Object.lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:12:42)
    at Function.loadString [as string] (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-loader/index.js:39:24)
    at compileBody (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:55:18)
    at Object.exports.compile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:152:16)
    at Function.pugCompile [as compile] (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-renderer-pug/lib/renderer.js:6:16)
    at View._precompile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo/lib/theme/view.js:119:29)
    at View (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo/lib/theme/view.js:13:8)
    at new Theme._View.View (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo/lib/theme/index.js:37:10)
INFO  Files loaded in 73 ms
WARN  No layout: 2017/12/06/hello-world/index.html
WARN  No layout: archives/index.html
WARN  No layout: index.html
WARN  No layout: archives/2017/index.html
WARN  No layout: archives/2017/12/index.html
INFO  0 files generated in 4.89 ms
Done in 1.89s.

> echo $?
0
```

with the fix:

```
> yarn build
yarn build v0.27.5
$ hexo generate
FATAL Cannot find module '/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-renderer-marked'
Error: Cannot find module '/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-renderer-marked'
    at Function.Module._resolveFilename (module.js:469:15)
    at Function.resolve (internal/module.js:27:19)
    at /Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo/lib/hexo/load_plugins.js:52:24
    at tryCatcher (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/util.js:16:23)
    at MappingPromiseArray._promiseFulfilled (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/map.js:61:38)
    at MappingPromiseArray.PromiseArray._iterate (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise_array.js:114:31)
    at MappingPromiseArray.init (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise_array.js:78:10)
    at Promise._settlePromise (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise.js:566:21)
    at Promise._settlePromise0 (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise.js:614:10)
    at Promise._settlePromises (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise.js:693:18)
    at Promise._fulfill (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise.js:638:18)
    at MappingPromiseArray.PromiseArray._resolve (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise_array.js:126:19)
    at MappingPromiseArray._filter (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/map.js:127:10)
    at MappingPromiseArray._promiseFulfilled (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/map.js:99:18)
    at Promise._settlePromise (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise.js:574:26)
    at Promise._settlePromise0 (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/bluebird/js/release/promise.js:614:10)
error Command failed with exit code 2.

> echo $?
1
```
