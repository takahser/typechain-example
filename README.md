# typechain-example

## Build smart contract

Run this command to build the smart contract and generate its artifacts:

```
cargo +nightly contract build
```

## Generate types using `typechain-polkadot`

Example project to test [typechain-polkadot](https://github.com/Supercolony-net/typechain-polkadot/)

Currently, the types are not generated when using the following command:

```bash
npx @727-ventures/typechain-polkadot --in ./flipper/target/ink --out ./output
```

See also [this comment](https://github.com/w3f/Grant-Milestone-Delivery/pull/623#pullrequestreview-1182848678) in the typechain-polkadot delivery (w3f grants program).

## Reproduction instructions

When following these steps, I'd expect to have the types produced. However, the `out` directory is empty, with exception of the `out/_sdk` directory which seems to be scaffolded.

```bash
git clone git@github.com:takahser/typechain-example.git
cd typechain-example
npm i
npx @727-ventures/typechain-polkadot --in flipper --out out
```

When running the command in the directory where the `flipper.json` is located, it fails with an error:

```bash
% npx @727-ventures/typechain-polkadot --in ./flipper/target/ink --out ./output
Error: ENOENT: no such file or directory, scandir '/Users/xxx/repos/typechain-example/flipper/flipper/target/ink'
    at Object.readdirSync (node:fs:1392:3)
    at Object.<anonymous> (/Users/xxx/repos/typechain-example/node_modules/@727-ventures/typechain-polkadot/index.ts:86:29)
    at Module._compile (node:internal/modules/cjs/loader:1103:14)
    at Module.m._compile (/Users/xxx/repos/typechain-example/node_modules/ts-node/src/index.ts:1618:23)
    at Module._extensions..js (node:internal/modules/cjs/loader:1157:10)
    at Object.require.extensions.<computed> [as .ts] (/Users/xxx/repos/typechain-example/node_modules/ts-node/src/index.ts:1621:12)
    at Module.load (node:internal/modules/cjs/loader:981:32)
    at Function.Module._load (node:internal/modules/cjs/loader:822:12)
    at Module.require (node:internal/modules/cjs/loader:1005:19)
    at require (node:internal/modules/cjs/helpers:102:18) {
  errno: -2,
  syscall: 'scandir',
  code: 'ENOENT',
  path: '/Users/xxx/repos/typechain-example/flipper/flipper/target/ink'
}
```
