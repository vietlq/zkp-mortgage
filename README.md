# zkp-mortgage

zkp-mortgage

Main reference: http://extropy.foundation/workshops/zkp/zokrates.html

Launch the Zokrates docker image:

```
$ docker run -v $PWD/code:/home/zokrates/code -ti zokrates/zokrates /bin/bash
```

Inside the docker image:

```
./zokrates compile -i ./code/results/mortgage.zok 
./zokrates setup
./zokrates export-verifier
```
