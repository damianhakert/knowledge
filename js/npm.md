# npm

## show latest tag for package
```sh
$ npm dist-tag ls <package>
```

## import npm scripts to shell
```sh
dirname=$(dirname "$(readlink -f "$0")")
node_modules="$(readlink -f "$dirname/../node_modules/.bin")"
PATH="$PATH:$node_modules"
```

## create release candidate
The `next` tag is commonly used to specify an rc. The `npm version
[premajor|preminor|prepatch]` commands can be used for this:

```sh
# publish a major RC
$ npm version premajor
$ npm publish --tag=next
$ npm install <package>@latest
```

## fix .DS_Store file stuff
```js
// os x adds this if you view the fixtures in finder and breaks the file count assertions
try { fs.unlinkSync(path.join(__dirname, 'fixtures', '.DS_Store')) } catch (e) { /* ignore error */ }
```
- https://docs.npmjs.com/cli/dist-tag
- https://docs.npmjs.com/cli/publish
- https://docs.npmjs.com/cli/version

## save a github url as an npm dep
```json
{
  "dependencies": {
    "opener": "yoshuawuyts/opener#split-bin",
  }
}
```
