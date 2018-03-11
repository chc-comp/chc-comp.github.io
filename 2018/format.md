---
layout: page
title: CHC-COMP Format
---

# CHC-COMP Benchmark Format
(Revision: Mar 7, 2018)

Comments on this document can be submitted through [Gitter][chc
gitter] or emailed directly to the organizers.

The format used for the CHC-COMP benchmarks is based on the
[SMT-LIB][smt-lib-lang] language version 2.6. Specifically, the format
is a syntactic fragment of SMT-LIB format with the restrictions
outlined in the rest of this document.

~~~ smt-lib
benchmark   ::=
   logic
   fun_decl+
   (assert chc_assert)*
   (assert chc_query)
   (check-sat)

logic       ::= (set-logic HORN)
fun_decl    ::= (declare-fun symbol ( sort* ) Bool)

chc_assert  ::=   ;; a well-formed first-order sentence of the form
  | (forall ( var_decl+ ) (=> chc_tail chc_head))
  | chc_head

var_decl    ::= (symbol sort)

chc_head    ::=
  | (u_predicate var*) , where all variables are DISTINCT

chc_tail    ::=
  | (u_predicate var*)
  | i_formula
  | (and (u_predicate var*)+ i_formula*)

chc_query   ::=  ;; a well-formed first-order sentence of the form
  | (forall ( var_decl+ ) (=> chc_tail false)

u_predicate ::= uninterperted predicate (i.e., Boolean function)

i_formula   ::=
   an SMT-LIB formula over variables, and interpreted functions and predicates
~~~

An example of an input in the CHC-COMP format is shown below:
~~~ smt-lib
(set-logic HORN)
(set-info :status sat)

(declare-fun Inv (Int) Bool)

;; fact
(assert (forall ((x Int)) (=> (= x 0) (Inv x))))
;; chc
(assert (forall ((x Int) (y Int))
                (=> (and (Inv x) (<= x 10) (= y (+ x 1)))
                   (Inv y))))
;; query
(assert (forall ((x Int)) (=> (and (Inv x) (> x 15)) false)))

(check-sat)
~~~

[smt-comp]: http://smtcomp.sourceforge.net/2017/rules17.pdf
[chc gitter]: https://gitter.im/chc-comp
[chc-comp]: https://chc-comp.github.io
[smt-lib-lang]: http://smtlib.cs.uiowa.edu/language.shtml
