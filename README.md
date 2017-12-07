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
INFO  Files loaded in 67 ms
Unhandled rejection Error: /Users/mateuszderks/workspace/hexo-pug-syntax-error-example/themes/my-theme/layout/index.pug:2:1
    1| a(
  > 2| 
-------^

The end of the string reached with no closing bracket ) found.
    at makeError (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-error/index.js:32:13)
    at Lexer.error (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:58:15)
    at Lexer.bracketExpression (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:234:14)
    at Lexer.attrs (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1011:24)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.advance (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1356:15)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.getTokens (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1375:12)
    at lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:12:42)
    at Object.lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:99:27)
    at Function.loadString [as string] (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-load/index.js:44:24)
    at compileBody (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:86:18)
    at Object.exports.compile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:243:16)
    at pugCompile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:7:14)
    at pugRenderer (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:13:10)
    at Hexo.<anonymous> (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/index.js:12:10)

Unhandled rejection Error: /Users/mateuszderks/workspace/hexo-pug-syntax-error-example/themes/my-theme/layout/index.pug:2:1
    1| a(
  > 2| 
-------^

The end of the string reached with no closing bracket ) found.
    at makeError (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-error/index.js:32:13)
    at Lexer.error (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:58:15)
    at Lexer.bracketExpression (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:234:14)
    at Lexer.attrs (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1011:24)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.advance (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1356:15)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.getTokens (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1375:12)
    at lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:12:42)
    at Object.lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:99:27)
    at Function.loadString [as string] (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-load/index.js:44:24)
    at compileBody (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:86:18)
    at Object.exports.compile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:243:16)
    at pugCompile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:7:14)
    at pugRenderer (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:13:10)
    at Hexo.<anonymous> (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/index.js:12:10)

Unhandled rejection Error: /Users/mateuszderks/workspace/hexo-pug-syntax-error-example/themes/my-theme/layout/index.pug:2:1
    1| a(
  > 2| 
-------^

The end of the string reached with no closing bracket ) found.
    at makeError (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-error/index.js:32:13)
    at Lexer.error (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:58:15)
    at Lexer.bracketExpression (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:234:14)
    at Lexer.attrs (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1011:24)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.advance (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1356:15)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.getTokens (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1375:12)
    at lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:12:42)
    at Object.lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:99:27)
    at Function.loadString [as string] (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-load/index.js:44:24)
    at compileBody (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:86:18)
    at Object.exports.compile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:243:16)
    at pugCompile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:7:14)
    at pugRenderer (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:13:10)
    at Hexo.<anonymous> (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/index.js:12:10)

Unhandled rejection Error: /Users/mateuszderks/workspace/hexo-pug-syntax-error-example/themes/my-theme/layout/index.pug:2:1
    1| a(
  > 2| 
-------^

The end of the string reached with no closing bracket ) found.
    at makeError (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-error/index.js:32:13)
    at Lexer.error (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:58:15)
    at Lexer.bracketExpression (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:234:14)
    at Lexer.attrs (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1011:24)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.advance (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1356:15)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.getTokens (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1375:12)
    at lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:12:42)
    at Object.lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:99:27)
    at Function.loadString [as string] (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-load/index.js:44:24)
    at compileBody (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:86:18)
    at Object.exports.compile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:243:16)
    at pugCompile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:7:14)
    at pugRenderer (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:13:10)
    at Hexo.<anonymous> (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/index.js:12:10)

Unhandled rejection Error: /Users/mateuszderks/workspace/hexo-pug-syntax-error-example/themes/my-theme/layout/index.pug:2:1
    1| a(
  > 2| 
-------^

The end of the string reached with no closing bracket ) found.
    at makeError (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-error/index.js:32:13)
    at Lexer.error (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:58:15)
    at Lexer.bracketExpression (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:234:14)
    at Lexer.attrs (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1011:24)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.advance (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1356:15)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.getTokens (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1375:12)
    at lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:12:42)
    at Object.lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:99:27)
    at Function.loadString [as string] (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-load/index.js:44:24)
    at compileBody (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:86:18)
    at Object.exports.compile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:243:16)
    at pugCompile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:7:14)
    at pugRenderer (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:13:10)
    at Hexo.<anonymous> (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/index.js:12:10)

Done in 1.16s.

> echo $?
0
```

with the fix:

```
> yarn build
yarn build v0.27.5
$ hexo generate
INFO  Start processing
INFO  Files loaded in 65 ms
FATAL Something's wrong. Maybe you can find the solution here: http://hexo.io/docs/troubleshooting.html
Error: /Users/mateuszderks/workspace/hexo-pug-syntax-error-example/themes/my-theme/layout/index.pug:2:1
    1| a(
  > 2| 
-------^

The end of the string reached with no closing bracket ) found.
    at makeError (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-error/index.js:32:13)
    at Lexer.error (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:58:15)
    at Lexer.bracketExpression (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:234:14)
    at Lexer.attrs (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1011:24)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.advance (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1356:15)
    at Lexer.callLexerFunction (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1319:23)
    at Lexer.getTokens (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:1375:12)
    at lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-lexer/index.js:12:42)
    at Object.lex (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:99:27)
    at Function.loadString [as string] (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug-load/index.js:44:24)
    at compileBody (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:86:18)
    at Object.exports.compile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/pug/lib/index.js:243:16)
    at pugCompile (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:7:14)
    at pugRenderer (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/lib/renderer.js:13:10)
    at Hexo.<anonymous> (/Users/mateuszderks/workspace/hexo-pug-syntax-error-example/node_modules/hexo-render-pug/index.js:12:10)
error Command failed with exit code 2.

> echo $?
1
```
