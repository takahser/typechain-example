# typechain-example

Example project to test [typechain-polkadot](https://github.com/Supercolony-net/typechain-polkadot/)

Currently, the types are not generated when using the following command:

```bash
npx @727-ventures/typechain-polkadot --in ./flipper/target/ink/flipper.contract --out ./output
```

See also [this comment](https://github.com/w3f/Grant-Milestone-Delivery/pull/623#pullrequestreview-1182848678) in the typechain-polkadot delivery (w3f grants program).

## Reproduction instructions

```bash
git clone git@github.com:takahser/typechain-example.git
cd typechain-example
npm i
npx @727-ventures/typechain-polkadot --in flipper --out out
```