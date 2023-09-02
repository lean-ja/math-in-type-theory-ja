# Theorems and proofs

This is where the fun starts. So far, it just looks like a type is what a type theorist calls a set, and a term is what they call an element. But let’s now look at another universe in Lean’s type theory, the universe `Prop` of true/false statements, where our traditional mental model of what’s going on is quite different. We will see how theorem statements and proofs can be modelled in the same way as types and terms.

So, how does this all work? As well as the universe `Type`, there is a second universe in Lean’s type theory called `Prop`. The terms of type `Prop` are true/false statements. There is an unfortunate notation clash here. In mathematics, the word proposition is often used to mean a baby theorem, and theorems are true (or else they would be conjectures or counterexamples or something). Here we are using the the word Proposition in the same way as the logicians do — a Proposition is a generic true/false statement, whose truth value is of no relevance.

This will all be clearer with examples. 2 + 2 = 4 is a Proposition, so we can write `2 + 2 = 4 : Prop`. But 2 + 2 = 5 is also a Proposition, so `2 + 2 = 5 : Prop` as well. I’ll say it again — Propositions do not have to be true! Propositions are true/false statements. Let’s see some more complex examples.

The true/false statement that x+0=x for all natural numbers x is a Proposition: in Lean this can be expressed as `(∀ x : ℕ, x + 0 = x) : Prop` . A Proposition is a term of type `Prop` (just like the types we saw earlier were terms of type `Type`). Let RH denote the statement of the Riemann Hypothesis. Then `RH : Prop`. We don’t care if it’s true, false, independent of the axioms of mathematics, undecidable, whatever. A Proposition is a true/false statement. Let’s look at the part of Lean’s type theory hierarchy which lives in the `Prop` universe.

* Universe: `Prop`
* Examples of types : `2 + 2 = 4`, `2 + 2 = 5`, the statement of Fermat’s Last Theorem, the statement of the Riemann Hypothesis.
* Examples of terms: ??

So what are the terms in this three-layer `Prop` hierarchy? They are the proofs!