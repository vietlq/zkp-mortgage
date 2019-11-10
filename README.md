# zkp-mortgage

Short reference: http://extropy.foundation/workshops/zkp/zokrates.html

Read on `zokrates` CLI and toxic waste: https://zokrates.github.io/reference/cli.html

`zokrates` types: https://zokrates.github.io/concepts/types.html

Launch the Zokrates docker image:

```
$ docker run -v $PWD/code:/home/zokrates/code -ti zokrates/zokrates /bin/bash
```

Inside the docker image, run these to set up and create `verifier.sol`:

```
./zokrates compile -i ./code/results/mortgage.zok 
./zokrates setup
./zokrates export-verifier
```

Compute witness and generate proof after compilation and setup:

```
./zokrates compute-witness -a 500000 25 400 67 96000 101000 3000 31
./zokrates generate-proof
```

Use Remix https://remix.ethereum.org/ and paste the generated `verifier.sol`. Compile, deploy the `Verifier` contract and then run `verifyTx` using given parameters `a, b, c, and inputs` generated in the file `proof.json`
