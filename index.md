---
layout: page
title: CHC-COMP
---
<div style="text-align: center; ">
  <p style="padding-bottom: 0pt; padding-top: 0pt; " class="Heading_2">
    <a href="/">2026</a> |
    <a href="{% link format.md %}">Format</a> |
    <a href="{% link 2018/rules.md %}">Rules</a> |
    <a href="https://github.com/chc-comp">Github</a>
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
The results of CHC-COMP 2026 will be announced at the
HCVS workshop affiliated with
[CAV 2026](https://conferences.i-cav.org/2026/) @ 
[FLoC 2026](https://www.floc26.org/).

<div style="clear: both" />

### Organizers

- [Konstantin Britikov](https://britikovki.com/), University of Lugano, Switzerland
- [Levente Bajczi](https://leventebajczi.com/), BME-MIT, Hungary

### Mailing List

Please register here <https://software.imdea.org/mailman3/postorius/lists/chc-comp.software.imdea.org> to receive updates and to participate in the discussion

### Participants

The list of participants will be made public, together with the
competition results, at the [HCVS workshop](https://www.sci.unich.it/hcvs26/).

### Solver Submission

Details on solver submission will be announced in due time.
If you would like to participate, please get in touch with the organisers:
[Konstantin Britikov](mailto:konstantin.britikov@usi.ch) and [Levente Bajczi](mailto:levente.bajczi@edu.bme.hu).

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

The following tracks are planned for CHC-COMP 2026:

- LIA-Lin: Linear Integer Arithmetic, linear clauses
- LIA-Nonlin: Linear Integer Arithmetic, nonlinear clauses
- LIA-Lin-Arrays: Linear Integer Arithmetic + Arrays, linear clauses
- LIA-Nonlin-Arrays: Linear Integer Arithmetic + Arrays, nonlinear clauses
- ADT-LIA: Linear Integer Arithmetic + non-recursive Algebraic data-types, nonlinear clauses
- ADT-LIA-Arrays: Algebraic data-types + Arrays + Linear Integer Arithmetic, nonlinear clauses

In addition to the theories listed in the track names, benchmarks can also use the Bool theory.

### Important Dates for 2026

To be announced.

- Benchmark submission deadline: 25 April, 2026
- Solver submission deadline: 25 April, 2026
- Solver resubmission deadline (technical issues): 02 May, 2026
- Presentation of results: 25 July, 2026

### Solvers Evaluation & Ranking

The description for the basis of the evaluation process and the ranking method of solvers
is described in [CHC-COMP 2022: Competition Report](https://dx.doi.org/10.4204/EPTCS.373.5). 
Exact methods subject to change.

### Big thanks to

- Everybody who organized and helped with the competition infrastructure over the last years, notably:  
      Nikolaj Bjørner,
      Adrien Champion,
      Emanuele De Angelis,
      Gidon Ernst,
      Grigory Fedyukovich,
      Hari Govind V K,
      Arie Gurfinkel,
      Dejan Jovanovic,
      Jose F. Morales, and
      Philipp Ruemmer
- [SoSy-Lab](https://www.sosy-lab.org/) at [LMU Munich](https://www.lmu.de/en/), Aaron Stump and [StarExec](https://www.starexec.org) for computing resources in past years

### Previous Editions

- [2025](/2025/)
- [2024](/2024/)
- [2023](/2023/)
- [2022](/2022/)
- [2021](/2021/)
- [2020](/2020/)
- [2019](/2019/)
- [2018](/2018/)

Last updated: {{site.time}}
