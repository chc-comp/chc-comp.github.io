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
    <!-- <a href="https://gitter.im/chc-comp/Lobby">Gitter</a> -->
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

CHC-COMP is associated with the Workshop on Horn-Clause Verification and Synthesis 
[HCVS 2025](https://www.sci.unich.it/hcvs25/).

<div style="clear: both" />

### Participation and Schedule (updated!)

- April 25: solver submission deadline.  
  **Participate here <https://forms.gle/Lh6VmRjRDaknZ4xU9>**.
  We aim to do some pre-runs to check for technical issues.

- April 25: benchmark submission deadline.  
  Benchmarks can be contributed by sending is the link to some Github repository.
  We will then fork it in the CHC-COMP Github organization.
  Benchmark contributions can be updated via pull requests.

- May 8: presentation of results at [SPIN 2025](https://spin-web.github.io/SPIN2025/), co-located with [ETAPS 2025](https://etaps.org/2025/), Hamilton, Canada.

### New: Mailing List

Please register here <https://software.imdea.org/mailman3/postorius/lists/chc-comp.software.imdea.org> to receive updates and to participate in the discussion

Note, there is also the ealier [Gitter](https://gitter.im/chc-comp/Lobby) chatroom, but this seemed to have little popularity.
Please be aware that we will not necessarily be responsive over there.

### Organizers

- [Gidon Ernst](https://www.sosy-lab.org/people/ernst/), LMU Munich, Germany
- [Jose F. Morales](https://jfmc.github.io/), IMDEA Software Institute, Spain
  

### Infrastructure

The key difference to earlier years will be that evaluations will run on the [SV-COMP](https://sv-comp.sosy-lab.org/) infrastructure at the LMU Munich.
- You can already test your solver in the [competition environment](https://gitlab.com/sosy-lab/benchmarking/competition-scripts/-/blob/main/test/Dockerfile.user.2025?ref_type=heads),
  which is provided as a Docker file. It is based on standard Ubuntu 24.04.
- If you are missing a *standard* software package from the list provided there, you may consider submitting a pull requests, but we do not guarantee that this will be honored.
- Please otherwise package all additional dependencies with your solver submission.
- We aim to keep the overhead on the side of participants *low*. This means we will offer a standard way to integrate, similar to the one on StarExec.
  Typical SV-COMP participation steps, like submitting a [toolinfo module](https://github.com/sosy-lab/benchexec/blob/main/doc/tool-integration.md)
  or [benchmark definitions](https://gitlab.com/sosy-lab/sv-comp/bench-defs) are *not* necessary for CHC-COMP.
- We will likely use this type of machine: Intel Xeon E3-1230 v5 @ 3.40 GHz, 4x2 cores with hyperthreading, 33GB of main memory.
  Results will be reported by wall-time and by CPU time to illustrate the benefits of solvers that can run parallel threads.

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

- LIA-Lin: Linear Integer Arithmetic, linear clauses
- LIA-Nonlin: Linear Integer Arithmetic, nonlinear clauses
- LIA-Lin-Arrays: Linear Integer Arithmetic + Arrays, linear clauses
- LIA-Nonlin-Arrays: Linear Integer Arithmetic + Arrays, nonlinear clauses
- ADT-LIA: Linear Integer Arithmetic + Arrays + non-recursive Algebraic data-types, nonlinear clauses
- ADT-LIA-Arrays: Algebraic data-types + Linear Integer Arithmetic, nonlinear clauses
- LRA: Linar Real Arithmetic (*tentative*)
- BV: Bitvectors (*tentative*)

In addition to the theories listed in the track names, benchmarks can also use the Bool theory.

### Novel features of CHC-COMP in 2025

- **Model Validation**: We introduce a model validation demo track. Participants can opt-in to have their `sat` models checked independently.
  We will report these results separately from the main standings. Details and format are being clarified at the moment.
- **Massively Parallel Track**: We may run selected evaluations with on a machine with 256 cores. Please get in touch if you think your solver may be able to make use of this.

### Big thanks to

- Everybody who organized and helped with the competition infrastructure over the last years, notably:  
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
