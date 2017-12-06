# hexo-pug-syntax-error-example

The example repository showing that the syntax error in the Hexo theme does not affect exit code from `hexo generate`.

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
