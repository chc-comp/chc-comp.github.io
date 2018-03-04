---
layout: page
title: Rules
---
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# 1st International Constrained Horn Clause Satisfiability Competition (CHC-COMP 2018): Rules and Procedures

(Revision: Mar 4, 2018)\\
(Based on rules and procedures of [SMT-COMP'17][smt-comp]

Comments on this document can be submitted through [Gitter][chc gitter] or emailed
directly to the organizers.

## Communication

All communication will be done through [Gitter][chc gitter]. Important
late-breaking news and any necessary clarifications and edits to the
rules and procedures will be announced there. Additional information
will appear on the competition web page at
[https://chc-comp.github.io][chc-comp].


## Important Dates

TBD

## Introduction

Constrained Horn Clauses (CHC) is a fragment of First Order Logic
(FOL) that is sufficiently expressive to describe many verification,
inference, and synthesis problems including inductive invariant
inference, model checking of safety properties, inference of procedure
summaries, regression verification, and sequential equivalence.

The Constrained Horn Clause Satisfiability competition (CHC-COMP) is
the annual competition among CHC solvers. The goal of the competition
is to advance development of solvers, facilitate standardization and
evolution of the input format, and collect benchmarks, and promote a
friendly competition.

CHC-COMP is co-located with the HCVS Workshop (July 13), which is
affiliated with the International Conference on Computer Aided
Verification (CAV 2018), International Conference on Logic Programming
(ICLP 2018) and International Joint Conference on Automated Reasoning
(IJCAR 2018) at International Federated Logic Conference (FLoC 2018).

Researchers are encouraged to submit new solvers and new benchmarks to
raise the level of the competition and advance the state-of-the-art.

CHC-COMP might have multiple tracks. These rules will be updated when
the tracks are finalized.

Each track will contain multiple divisions based on specific SMT-LIB
logic used for constrained and additional features specific to
CHC. Winners will be recognized based on number of instances solved,
and, potentially, other criteria such as CPU time.

This document is based significantly on the rules and procedures for
[SMT-COMP 2017][smt-comp].

## Entrants

__Solver submission.__ An entrant to CHC-COMP is an CHC solver
submitted by its authors using the [StarExec](http://www.starexec.org)
service. The execution service enables members of the SMT research
community (of which CHC is a fragment) to run solvers on jobs
consisting of benchmarks from the SMT-LIB benchmark library. Jobs are
run on a shared computer cluster. The execution service is provided
free of charge, but it does require registration to create a login
account. Registered users may then upload their own solvers to run, or
may run public solvers already uploaded to the service. Information
about how to configure and upload a solver is contained in the
StarExec user guide,

[https://wiki.uiowa.edu/display/stardev/User+Guide](https://wiki.uiowa.edu/display/stardev/User+Guide).
{: style="text-align: center;" }


For participation in CHC-COMP, a solver must be uploaded to StarExec
and made publicly available. StarExec supports solver configurations;
for clarity, each submitted solver must have one configuration
only. Moreover, the organizers must be informed of the solver’s
presence and the tracks and divisions in which it is participating via
the web form at

url-to-form-to-be-created
{: style="font-size: 130%; text-align: center;" }

{::comment}
A submission must also include a 32-bit unsigned integer. These
integer numbers, collected from all submissions, are used to seed the
benchmark scrambler.
{:/comment}

__System description.__ As part of a submission, CHC-COMP entrants are
encouraged to provide a short (1–2 pages) description of the
system. This should include a list of all authors of the system, their
present institutional affiliations, and any appropriate
acknowledgements. The programming language(s) and basic CHC solving
approach employed should be described (e.g., PDR, interpolation,
predicate abstraction, etc.) System descriptions are encouraged to
include a URL for a web site for the submitted tool. System
descriptions may be submitted after the solver deadline, but to be
useful should be sent to the organizers before the competition
ends. We intend to make system descriptions publicly available.

__Multiple versions.__ The organizers’ intent is to promote as wide a
comparison among solvers and solver options as possible. However, if
the number of solver submissions is too large for the computational
resources available to the competition, the organizers reserve the
right not to accept multiple versions of solvers from the same solver
team.

__Other solvers.__ The organizers reserve the right to include other
solvers of interest in the competition, e.g., for comparison purposes.

__Wrapper tools.__ A wrapper tool is defined as any solver which calls
one or more CHC solvers not written by the author of the wrapper
tool. The other solvers are called the wrapped solvers. A wrapper tool
must explicitly acknowledge any solvers that it wraps. Its system
description should make clear the technical innovations by which the
wrapper tool expects to improve on the wrapped solvers.

__Attendance.__ Participants of CHC-COMP need not be physically
present at the competition or the HCVS workshop to participate or win.


## Deadlines

CHC-COMP entrants must be submitted via StarExec (solvers) __and__ the
above web form (accompanying information) until the end of __SUBMIT
DATE__, anywhere on earth. After this date no new entrants will be
accepted. However, updates to existing entrants on StarExec will be
accepted until the end of __END ACCEPT DATE__ anywhere on earth.

We strongly encourage participants to use this grace period only for
the purpose of fixing any bugs that may be discovered, and not for
adding new features, as there may be no opportunity to do extensive
testing using StarExec after the initial deadline.

The solver versions that are present on StarExec at the conclusion of
the grace period will be the ones used for the competition. Versions
submitted after this time will not be used. The organizers reserve the
right to start the competition itself at any time after the opening of
the New York Stock Exchange on the day after the final solver
deadline.

These deadlines and procedures apply equally to all tracks of the
competition.


## Execution of the Solvers

Solvers will be publicly evaluated in all tracks and divisions into
which they have been entered. All results of the competition will be
made public.

### Logistics

### Main track

## Benchmarks and Problem Divisions

__Benchmark sources.__ Benchmarks for each division will be drawn from
the CHC-COMP benchmarks located at
[https://github.com/chc-comp](https://github.com/chc-comp).

__New benchmarks.__ The deadline for submission of new benchmarks is
__DATE__. The organizers, will be checking and curating these until
__DATE__.

__Benchmark demographics.__ In CHC-COMP repository, the benchmarks are
organized according to families. A benchmark family contains problems
that are similar in some significant way. Typically they come from the
same source or application, or are all output by the same tool. Each
top-level repository within the CHC-COMP GitHub organization
represents a distinct family.

__Benchmark selection.__ The competition will use a subset of CHC-COMP
benchmarks. The benchmark pool is culled as follows:

1. _Remove inappropriate benchmarks._ The competition organizers may
   remove benchmarks that are deemed inappropriate or uninteresting
   for competition, or cut the size of certain benchmark families to
   avoid their over-representation. CHC-COMP attempts to give
   preference to benchmarks that are "real-world", in the sense of
   coming from or having some intended application outside the
   competition.

All remaining benchmarks are eligible to be used for the
competition. The selection of the benchmarks for the competition will
be made by the organizers based on many factors, including, but not
limited to, benchmark difficulty and benchmark category.

The set of benchmarks selected for the competition will be published
as a repository on GitHub when the competition begins.

__Heats.__ Since the organizers at this point are unsure how long the
set of benchmarks may take (which will depend also on the number of
solvers submitted), the competition may be run in heats. For each
track and division, the selected benchmarks may be randomly divided
into a number of (possibly unequal-sized) heats. Heats will be run in
order. If the organizers determine that there is adequate time, all
heats will be used for the competition. Otherwise, incomplete heats
will be ignored.

__Benchmark scrambling.__ Benchmarks might be slightly scrambled
before the competition, using a simple benchmark scrambler. The
benchmark scrambler, if used, the scrambler will be made publicly
available before the competition.

Naturally, solvers must not rely on previously determined identifying
syntactic characteristics of competition benchmarks in testing
satisfiability. Violation of this rule is considered cheating.

__Pseudo-random numbers.__ Pseudo-random numbers used, e.g., for the
creation of heats or the scrambling of benchmarks, will be generated
using the standard C library function `random()`, seeded (using
`srandom()`) with the sum, modulo 2<sup>30</sup>, of the integer numbers
provided in the system descriptions (see Section 4) by all CHC-COMP
entrants other than the organizers. Additionally, the integer part of
the opening value of the New York Stock Exchange Composite Index on
the first day the exchange is open on or after the date specified in
the timeline (Section 2) will be added to the other seeding
values. This helps provide transparency, by guaranteeing that the
organizers cannot manipulate the seed in favour of or against any
particular submitted solver.

## Scoring

### Competitive Divisions

Scores will be computed for all solvers and divisions. However,
winners will be declared only for _competitive_ divisions. A division in
a track is competitive if at least two substantially different solvers
(i.e., solvers from two different teams) were submitted. Although the
organizers may enter other solvers for comparison purposes, only
solvers that are explicitly submitted by their authors determine
whether a division is competitive, and are eligible to be designated
as winners.

### Benchmark Scoring

A solver’s raw score for each benchmark is a quadruple $$⟨e, n, w,
c⟩$$, with $$e \in \{0, 1\}$$ the number of erroneous results (usually
$$e = 0$$), $$0 \leq n \leq N$$ the number of correct results, $$w \in
[0, T ]$$ the (real-valued) wall-clock time in seconds, and $$c \in
[0, 4T ]$$ the (real-valued) CPU time in seconds, measured across all
cores and sub-processes, until the solver process terminates.

__Main track.__ More specifically, for the main track, we have

- $$e = 0$$, $$n = 0$$ if the solver aborts without a response, or the
result of the __check-sat__ command is `unknown`,

- $$e = 0$$, $$n = 1$$ if the result of the __check-sat__ command is
`sat` or `unsat`, and the result either agrees with the benchmark
status or the benchmark status is `unknown`,

- $$e = 1$$, $$n = 0$$ if the result of the __check-sat__ command is
  incorrect.

Note that a (correct or incorrect) response is taken into
consideration even when the solver process terminates abnormally, or
does not terminate within the time limit. Solvers should take care not
to accidentally produce output that contains `sat` or `unsat`.

### Sequential performance (main track)

We intend to recognize both best sequential and best parallel solvers
in all competitive main track divisions.

The raw score, as defined above, favours parallel solvers, which may
utilize all available processor cores. To evaluate sequential
performance, we derive a sequential score by imposing a (virtual) CPU
time limit equal to the wall-clock time limit $$T$$. A solver result is
taken into consideration for the sequential score only if the solver
process terminates within this CPU time limit. More specifically, for
a given raw score $$(e, n, w, c)$$, the corresponding sequential score is
defined as $$(e_S , n_S , c_S )$$, where

- $$e_S =0$$ and $$n_S =0$$ if $$c>T$$, $$e_S =e$$ and $$n_S =n$$, otherwise,

- $$c_S = min\{c,T\}$$.

[smt-comp]: http://smtcomp.sourceforge.net/2017/rules17.pdf
[chc gitter]: https://gitter.im/chc-comp
[chc-comp]: https://chc-comp.github.io
