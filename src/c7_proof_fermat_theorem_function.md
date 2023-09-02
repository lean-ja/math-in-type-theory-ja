# The proof of Fermat’s Last Theorem is a function

So what does a proof of `∀ x y z : ℕ, n > 2 ∧ x^n + y^n = z^n → x*y = 0` look like? Well, there is an arrow involved in that Proposition, so the statement of Fermat’s Last Theorem is some kind of set of the form $\mathrm{Hom}(A,B)$, which means that in Lean, a proof of Fermat’s Last Theorem is actually a function! And here is what that function does. It has four inputs. The first three inputs are natural numbers `x`, `y` and `z`. The fourth input is a proof: it is a proof of the Proposition `n > 2 ∧ x^n + y^n = z^n`. And the output of this function is a proof of the Proposition `x*y = 0`. This is quite an unconventional way to think about what the proof of Fermat’s Last Theorem is, and let me stress that it does not help at all with actually trying to understand the proof — but it is a completely consistent mental model for how mathematics works. Unifying the concept of a number and a proof — thinking of them both as terms — enables you to think of proofs as functions. Lean is a functional programming language, and in particular it is designed with functions at its heart. This, I believe, is why theorem provers such as Lean, Coq and Isabelle/HOL, which use type theory, are now moving ahead of provers such as Metamath and Mizar, which use set theory.

Prove a theorem! Write a function!

|Universe     |Type |Prop                            |
|:------------|:----|:-------------------------------|
|Type examples|ℝ    |2 + 2 = 5, (∀ a : ℕ, a + 0 = a)|
Term examples |37, π|`add_zero`, `rfl`               |

Cheat sheet