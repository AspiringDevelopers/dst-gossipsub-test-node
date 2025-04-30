# dst-gossipsub-test-node for Libp2p

* DST gossipsub test node
* incl shadow simulation setup

# Shadow and Dockerized Set-up and Performance Metrics for go-libp2p, rust-libp2p and nim-libp2p

Please visit https://github.com/AspiringDevelopers/dst-gossipsub-test-node//tree/fc3c3a686c5b85f8b364148887b258f1325b10e6 

Dockerized set-up with performance metrics in real-time: https://github.com/vacp2p/dst-gossipsub-test-node/tree/dockerized

Go-libp2p is the module used in Optimism mainnet infrastructure.


# Performance Metrics in Libp2p, Progress Update and Milestones

1. Shadow simulator experiment: https://vac.dev/rlog/gsub-idontwant-perf-eval/

2. https://vac.dev/rlog/gsub-largemsg-improvements/

3. Roadmap: https://roadmap.vac.dev/p2p/

4. Batch Publishing: https://ethresear.ch/t/improving-das-performance-with-gossipsub-batch-publishing/21713

5. DAS Simulator: https://github.com/cskiraly/das-simulator-nim

6. Gossipsub test node: https://github.com/vacp2p/dst-gossipsub-test-node

## Discussions in Libp2p Specifications Weekly Meetings

   Please visit https://docs.google.com/document/d/14CYAxPjYqmujovC-vHPBSXqJVvfbtImV/edit?usp=sharing&ouid=109169901542566286145&rtpof=true&sd=true 


## Shadow example

```sh
nimble install -dy
cd shadow
# the default shadow.yml will start 5k nodes, you might want to change that by removing
# lines and setting PEERS to the number of instances
./run.sh
# the output is a "latencies" file, or you can find each host output in the
# data.shadow folder

# you can use the plotter tool to extract useful metrics & generate a graph
cd ../tools
nim -d:release c plotter
./plotter ../shadow/latencies "Clever graph name"
# will output averages, and generate a "test.svg" graph
```

The dependencies will be installed in the `nimbledeps` folder, which enables easy tweaking
