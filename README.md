# Two layer RMIs on P4 capable network switches

## ABSTRACT

Recently several works proposed new approaches on how advancements in machine learning can be used to improve indexing strategies on sorted data. This led to the [SOSD benchmark](https://github.com/learnedsystems/SOSD) which enabled having a baseline for evaluating different competitors in a standardized way. At the same time, with a wider adoption of network programmability through P4, a trend towards outsourcing computationally intensive procedures to programmable switches started. Our goal is to combine these two advancements by maintaining recent progress that learned indexing algorithms offer and evaluate possibilities of further leveraging their performance by using the power of network programmability.

After careful evaluation we come to the decision that we continue our work focusing on the learned indexing algorithm [RMI](https://arxiv.org/abs/1712.01208), which suits our idea of implementing parts of it over the network best. Indeed we find that the [P4 specification](https://p4.org/p4-spec/docs/P4-16-v1.2.2.html) allows an implementation of the lookup part of RMI on the switch and attains perfect accuracy when tested on virtually simulated network hardware. At this point we analyze how far away our theoretical implementation is, from actually running on real world hardware and we find that there is a long way to go. From this result we then generalize our solution to any dataset and arbitrary RMI configuration by adapting the code generation part of the [RMI reference implementation](https://github.com/learnedsystems/RMI) to output P4 source code files. We finally conclude our work by coming up with a strategy to, even though having a theoretical implementation, estimate how much our idea of outsourcing RMI calculations to the network could benefit a closed system. We find that we could save around 50-100ns per lookup per last mile search worker, which would result in a constant speed up that scales horizontally with the amount of last mile search workers available to a single switch.

## The code

The proposed `RMI-P4` implementation can be found [here](https://github.com/Cobra8/RMI-P4).

Additionally the `RMI` reference implementation can be found [here](https://github.com/learnedsystems/RMI).

Finally the original `SOSD` benchmark can be found [here](https://github.com/learnedsystems/SOSD).

<!--- Create a directory template? Where I include the P4-RMI repo as submodule? => Could include the lookup script there with more explanation on how to run stuff --->

## Supervisors
- [Prof. Dr. Philippe Cudré-Mauroux](https://exascale.info/phil/)
- [Dr. Alberto Lerner](https://exascale.info/members/alberto-lerner/)

## Author
- [Lucas Bürgi](https://github.com/Cobra8)
