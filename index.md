---
layout: page
title: CHC-COMP
---
<div style="text-align: center; ">
  <p style="padding-bottom: 0pt; padding-top: 0pt; " class="Heading_2">
    <a href="/">2025</a> |
    <a href="{% link format.md %}">Format</a> |
    <a href="{% link 2018/rules.md %}">Rules</a> |
    <!-- <a href="https://tacas.info/toolympics2023.php">TOOLympics</a> | -->
    <a href="https://github.com/chc-comp">Github</a> |
    <a href="https://gitter.im/chc-comp/Lobby">Gitter</a>
  </p>
</div>

![CHC-COMP](/logo.png){:width="30%" style="float: left; margin-right: 12pt" }

Constrained Horn Clauses (CHC) is a fragment of First
Order Logic (FOL) that is sufficiently expressive to
describe many verification, inference, and synthesis
problems including inductive invariant inference, model
checking of safety properties, inference of procedure
summaries, regression verification, and sequential
equivalence. The CHC competition (CHC-COMP) will compare
state-of-the-art tools for CHC solving with respect to
performance and effectiveness on a set of publicly
available benchmarks. The winners among participating
solvers are recognized by measuring the number of
correctly solved benchmarks as well as the runtime.

### Organizers

- [Gidon Ernst](https://www.sosy-lab.org/people/ernst/), LMU Munich, Germany
- [Jose F. Morales](https://jfmc.github.io/), LMU Munich, Germany

### Participation and Schedule

Participation guidelines and important dates for 2025 will be announced shortly.

### Benchmarks

The competition benchmarks will be selected among the
benchmarks available on [GitHub](https://github.com/chc-comp).
If you have benchmarks of any kind that can be made public, and that are not
yet on Github, please upload!
The format of the benchmarks is described [here](./format.md);
a detailed description of the benchmark selection process can be found in
[CHC-COMP 2022: Competition Report](https://dx.doi.org/10.4204/EPTCS.373.5).
The final list of benchmarks used in the competition will be made
public, together with the competition results.

The following tracks are planned for CHC-COMP 2025

- LIA-lin: Linear Integer Arithmetic, linear clauses
- LIA-nonlin: Linear Integer Arithmetic, nonlinear clauses
- LIA-lin-Arrays: Linear Integer Arithmetic + arrays, linear clauses
- LIA-nonlin-Arrays: Linear Integer Arithmetic + arrays, non-linear clauses
- LIA-nonlin-Arrays-nonrecADT: Linear Integer Arithmetic + arrays + non-recursive Algebraic data-types, nonlinear clauses
- ADT-LIA-nonlin: Algebraic data-types + Linear Integer Arithmetic, nonlinear clauses 


In addition to the theories listed in the track names, benchmarks can also use the Bool theory.


### Big thanks to

- Everybody who organized and helped with the competition infrastructure over the last years:  
      Nikolaj Bjørner,
      Adrien Champion,
      Emanuele De Angelis,
      Grigory Fedyukovich,
      Hari Govind V K,
      Arie Gurfinkel,
      Dejan Jovanovic, and
      Philipp Ruemmer

- Aaron Stump and [StarExec](https://www.starexec.org)!

### Previous Editions

- [2024](/2024/)
- [2023](/2023/)
- [2022](/2022/)
- [2021](/2021/)
- [2020](/2020/)
- [2019](/2019/)
- [2018](/2018/)

Last updated: {{site.time}}
