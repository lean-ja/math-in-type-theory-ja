<!-- # The proof of Fermat’s Last Theorem is a function -->
# フェルマーの最終定理の証明は関数

<!-- So what does a proof of `∀ x y z : ℕ, n > 2 ∧ x^n + y^n = z^n → x*y = 0` look like? Well, there is an arrow involved in that Proposition, so the statement of Fermat’s Last Theorem is some kind of set of the form $\mathrm{Hom}(A,B)$, which means that in Lean, a proof of Fermat’s Last Theorem is actually a function! And here is what that function does. It has four inputs. The first three inputs are natural numbers `x`, `y` and `z`. The fourth input is a proof: it is a proof of the Proposition `n > 2 ∧ x^n + y^n = z^n`. And the output of this function is a proof of the Proposition `x*y = 0`. This is quite an unconventional way to think about what the proof of Fermat’s Last Theorem is, and let me stress that it does not help at all with actually trying to understand the proof — but it is a completely consistent mental model for how mathematics works. Unifying the concept of a number and a proof — thinking of them both as terms — enables you to think of proofs as functions. Lean is a functional programming language, and in particular it is designed with functions at its heart. This, I believe, is why theorem provers such as Lean, Coq and Isabelle/HOL, which use type theory, are now moving ahead of provers such as Metamath and Mizar, which use set theory. -->

では `∀ x y z : ℕ, n > 2 ∧ x^n + y^n = z^n → x*y = 0` の証明とはどのようなものでしょうか？この命題には矢印が含まれているので，フェルマーの最終定理のステートメントは $\mathrm{Hom}(A,B)$ という形の集合の一種です．Lean では，フェルマーの最終定理の証明は実際に関数です！その関数が何をするかは次の通りです．それは４つの入力を持ちます．最初の３つの入力は自然数 `x`, `y`, `z` です．４番目の入力は証明で，命題 `n > 2 ∧ x^n + y^n = z^n` の証明です．そして出力は命題 `x*y=0` の証明です．これは「フェルマーの最終定理の証明とは何か」という問いについてのきわめて型破りな考え方であり，証明を実際に理解しようとする際には全く役に立たないことを強調しておきましょう． ―― しかし，これは数学がどのように機能するかについての完全に一貫したメンタルモデルです．数と証明の概念を統一することで，―― つまり両方を項として考えることで，―― 証明を関数として考えることができます．Lean は関数型プログラミング言語であり，特に関数を中心に設計されています．現在 Lean や Coq や Isabelle/HOL といった型理論を使用する証明支援系が，Metamath や Mizar のような集合論を使用する証明支援系より進んでいるのは，このためだと私は確信しています．

<!-- Prove a theorem! Write a function! -->

定理を証明しましょう！関数を書きましょう！

|        |        |                                 |
| :----- | :----- | :------------------------------ |
| 宇宙   | `Type` | `Prop`                          |
| 型の例 | ℝ      | 2 + 2 = 5, (∀ a : ℕ, a + 0 = a) |
| 項の例 | 37, π  | `add_zero`, `rfl`               |

<!-- Cheat sheet -->
