To trigger the issue, just execute rollup:

```shell
$ npx rollup -i src/index.ts -p @rollup/plugin-typescript
npm WARN cli npm v10.2.4 does not support Node.js v16.20.2. This version of npm supports the following node versions: `^18.17.0 || >=20.5.0`. You can find the latest version at https://nodejs.org/.

src/index.ts → stdout...
var foo = 5;

console.log(foo);
(!) Plugin typescript: @rollup/plugin-typescript TS2304: Cannot find name 'foo'.
src/invalid.ts: (1:1)

1 foo
  ~~~
```

Note how doing the same thing with `tsc` works perfectly:

```shell
$ tsc src/index.ts
```