---
layout: page
title: Rules
---
<script src="https://cdnjs.cloudflare.com/ajax/libs/mathjax/2.7.0/MathJax.js?config=TeX-AMS-MML_HTMLorMML" type="text/javascript"></script>

# 1st International Constrained Horn Clause Satisfiability Competition (CHC-COMP 2018): Rules and Procedures

(Revision: Mar 4, 2018)\\
(Based on rules and procedures of [SMT-COMP'17][smt-comp])

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

__Dates of competition.__ The bulk of the computation will take place
during the weeks leading up to FLoC 2018. Intermediate results will be
regularly posted to the CHC-COMP website as the competition runs.

The organizers reserve the right to prioritize certain competition
tracks or divisions to ensure their timely completion, and in
exceptional circumstances to complete divisions after the HCVS
workshop.

__Input and output.__ In the main track, a participating solver must
read a single benchmark script, whose filename is presented as the
solver’s first command-line argument.

The benchmark script is in the concrete syntax of the SMT-LIB format,
version 2.6, though with a restricted set of commands. A benchmark
script is a text file containing a sequence of SMT-LIB commands that
satisfies the following requirements:

1. The script starts with the single `(set-logic HORN)` command.
2. The script may contain any number of `set-info` commands.
3. The script may contain any number of `declare-fun` commands.
4. The script may contain any number of `assert` commands.
5. There is exactly one `check-sat` command.
6. The script might optionally contain an `(exit)` command.
7. No other commands besides the ones mentioned above should be used.

Additional restrictions will be placed on the format and will be made
available on the web site at [https://chc-comp.github.io][chc-comp].

__Time and memory limits.__ Each CHC-COMP solver will be executed on a
dedicated processor of a competition machine, for each given
benchmark, up to a fixed wall-clock time limit $$T$$ . Each processor
has 4 cores. Detailed machine specifications are available on the
competition web site.

The time limit $$T$$ is yet to be determined, but it is anticipated to
be at most 40 minutes of wall-clock time per solver/benchmark
pair. Solvers that take more than this time limit will be
killed. Solvers are allowed to spawn other processes; these will be
killed at approximately the same time as the first started process.

The StarExec service also limits the memory consumption of the solver
processes. We expect the memory limit per solver/benchmark pair to be
on the order of 60 GB. The values of both the time limit and the
memory limit are available to a solver process through environment
variables. See the StarExec user guide for more information.

### Main track

The main track competition will consist of selected benchmarks in each
of the logic divisions. Each benchmark script will be presented to the
solver as its first command-line argument. The solver is then expected
to attempt to report on its standard output channel whether the
formula is satisfiable (`sat`, in lowercase) or unsatisfiable
(`unsat`). A solver may also report `unknown` to indicate that it
cannot determine satisfiability of the formula.  The main track
competition uses a StarExec post-processor (named "CHC-COMP 2018") to
accumulate the results.

__Aborts and unparsable output.__ Any `success` outputs will be
ignored. Solvers that exit before the time limit without reporting a
result (e.g., due to exhausting memory or crashing) and do not produce
output that includes `sat`, `unsat` or `unknown` will be considered to
have aborted.

__Persistent state.__ Solvers may create and write to files and
directories during the course of an execution, but they must not read
such files back during later executions. Each solver is executed with
a temporary directory as its current working directory. Any generated
files should be produced there (and not, say, in the system’s `/tmp`
directory). The StarExec system sets a limit on the amount of disk
storage permitted -- typically 20 GB. See the StarExec user guide for
more information. The temporary directory is deleted after the job is
complete. Solvers must not attempt to communicate with other machines,
e.g., over the network.


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

- _Remove inappropriate benchmarks._ The competition organizers may
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
provided in the system descriptions  by all CHC-COMP
entrants other than the organizers. Additionally, the integer part of
the opening value of the New York Stock Exchange Composite Index on
the first day the exchange is open on or after the date specified in
the timeline  will be added to the other seeding
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

### Division Scoring

__Main track: removal of disagreements.__ Before division scores are
computed for the main track, benchmarks with `unknown` status are
removed from the competition results if two (or more) solvers that are
sound on benchmarks with known status disagree on their result. More
specifically, a solver (including a solver that was entered into the
competition by the organizers for comparison purposes) is _sound on
benchmarks with known status_ for a division if its raw score is of the
form $$(0, n, w, c)$$ for each benchmark in the division, i.e., if it
did not produce any erroneous results. Two solvers disagree on a
benchmark if one of them reported `sat` and the other reported
`unsat`. Only the remaining benchmarks are used in the following
computation of division scores.

To compute a solver’s score for a division, the solver’s individual
benchmark scores for all benchmarks in the division are first
multiplied by a scalar weight that depends on the benchmark’s family,
and then summed component-wise.

For a given competition benchmark $$b$$, let $$F_b \geq 1$$ be the
total number of benchmarks in $$b$$’s benchmark family that were used
in the competition track to which the division belongs (and not
removed because of disagreements). We define the weight for benchmark
$$b$$ as $$\alpha_b = (1 +log_e F_b)/F_b$$. We define the _normalized
weight_ for benchmark $$b$$ as
$$\alpha_{b′} = \alpha_b / ( \sum_{b′} \alpha_{b′})$$,
where the sum is over all benchmarks in the
division. Let $$N$$ be the total number of benchmarks in the division.

For the main track, we will separately compute the weighted sum of all
raw scores:

$$
\sum_{b} \alpha'_b \cdot (e_b \cdot N, n_b \cdot N, w_b, c_b)
$$

where the sum is over all benchmarks in the division to assess
parallel performance, and the weighted sum of all sequential scores to
assess sequential performance.

Division scores are compared lexicographically:

- A weighted sum of raw scores $$(e,n,w,c)$$ is better than
  $$(e',n',w',c')$$ iff $$e < e'$$ or ($$e = e'$$ and $$n>n'$$) or
  ($$e=e'$$ and $$n=n'$$ and $$w<w'$$) or ($$e=e'$$ and $$n=n'$$ and
  $$w=w'$$ and $$c<c'$$). That is, fewer errors takes precedence over
  more correct solutions, which takes precedence over less wall-clock
  time taken, which takes precedence over less CPU time taken.

- A weighted sum of sequential scores $$(e_S,n_S,c_S)$$ is better than
  $$(e'_S,n'_S,c'_S)$$ iff $$e_S < e'_S$$ or ($$e_S =e'_S$$ and $$n_S >n'_S$$)
  or ($$e_S =e'_S$$ and $$n_S =n'_S$$ and $$c_S
  <c'_S$$). That is, fewer errors takes precedence over more correct
  solutions, which takes precedence over less CPU time taken.

We will not make any comparisons between raw scores and sequential
scores, as these are intended to measure fundamentally different
performance characteristics.

### Competition-wide scoring (main track)

We define a competition-wide metric for the main track, separately for
parallel and sequential performance, as follows. Let $$N_i$$ be the
total number of benchmarks in division $$i$$ that were used in the
competition (and not removed because of disagreements), and let
$$(e_i, n_i, w_i, c_i)$$ be a solver’s raw score for this
division. The solver’s competition-wide raw score is

$$
\sum_{i} (e_i = 0 \;?\; (n_i / N_i)^2 : -4) \log_e N_i
$$

where the sum is overall competitive divisions in to which the solver
was entered. The solver’s competition-wide sequential score is
computed from its sequential division scores according to the same
formula. We will recognize the best three solvers according to these
metrics.

## Other Awards and Mentions

The organizers might recognize solvers and participants based on other
criteria such as contribution of new benchmarks.

## Judging

The organizers reserve the right, with careful deliberation, to remove
a benchmark from the competition results if it is determined that the
benchmark is faulty (e.g., syntactically invalid in a way that affects
some solvers but not others); and to clarify ambiguities in these
rules that are discovered in the course of the competition. Authors of
solver entrants may appeal to the organizers to request such
decisions. Organizers that are affiliated with solver entrants will be
recused from these decisions. The organizers’ decisions are final.

## Acknowledgements

The organizing team for CHC-COMP 2018 is

- Arie Gurfinkel -- University of Waterloo, Canada
- Philipp Ruemmer -- Uppsala University, Sweden
- Grigory Fedyukovich -- Princeton University, USA
- Adrien Champion -- University of Tokyo, Japan

The rules are substantially based on the rules and procedures of the
[SMT-COMP][smt-comp] competition.

__Disclosures.__ The organizers might be participants. In this case,
the association between tools and organizers should be described here.



[smt-comp]: http://smtcomp.sourceforge.net/2017/rules17.pdf
[chc gitter]: https://gitter.im/chc-comp
[chc-comp]: https://chc-comp.github.io
