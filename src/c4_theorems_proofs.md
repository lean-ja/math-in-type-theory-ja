<!-- # Theorems and proofs -->
# 定理と証明

<!-- This is where the fun starts. So far, it just looks like a type is what a type theorist calls a set, and a term is what they call an element. But let’s now look at another universe in Lean’s type theory, the universe `Prop` of true/false statements, where our traditional mental model of what’s going on is quite different. We will see how theorem statements and proofs can be modelled in the same way as types and terms. -->

ここからが楽しいところです．ここまで，型とは型理論における集合の呼び名であり，項とは型理論における要素の呼び名でした．しかし，ここで Lean の型理論におけるもう一つの宇宙，命題の宇宙 `Prop` を見てみましょう．そこで起こることは，私たちの伝統的なメンタルモデルとは全く異なります．ここでは，定理のステートメントと証明が，型や項と同じようにどのようにモデル化できるかを見ていきます．

<!-- So, how does this all work? As well as the universe `Type`, there is a second universe in Lean’s type theory called `Prop`. The terms of type `Prop` are true/false statements. There is an unfortunate notation clash here. In mathematics, the word proposition is often used to mean a baby theorem, and theorems are true (or else they would be conjectures or counterexamples or something). Here we are using the the word Proposition in the same way as the logicians do — a Proposition is a generic true/false statement, whose truth value is of no relevance. -->

定理のステートメントと証明はどのようにモデル化されるのでしょうか？Lean の型理論には `Type` という宇宙だけでなく，`Prop` という第二の宇宙があります．`Prop` 型の項は命題です．ここで残念な表記の衝突があります．数学では，proposition (命題)という言葉はしばしば定理のこどもという意味で使われますが，定理は真です．（そうでなければ予想や反例と呼ばれます）したがって，数学において命題という言葉は真である文を指しますが，ここでは，論理学者と同じように命題という言葉を使います．つまり，命題とは一般的な真か偽かどちらかになる文のことであり，それが正しいか誤りかは関係ありません．

<!-- This will all be clearer with examples. 2 + 2 = 4 is a Proposition, so we can write `2 + 2 = 4 : Prop`. But 2 + 2 = 5 is also a Proposition, so `2 + 2 = 5 : Prop` as well. I’ll say it again — Propositions do not have to be true! Propositions are true/false statements. Let’s see some more complex examples. -->

例を見るとわかりやすいでしょう．$2 + 2 = 4$ は命題なので `2 + 2 = 4 : Prop` と書くことができます．しかし，$2 + 2 = 5$ も命題なので，`2 + 2 = 5 : Prop` と書くこともできます．何度も言いますが，命題が真である必要はありません！命題は真か偽かどちらかになる文のことです．もう少し複雑な例を見てみましょう．

<!-- The true/false statement that x+0=x for all natural numbers x is a Proposition: in Lean this can be expressed as `(∀ x : ℕ, x + 0 = x) : Prop` . A Proposition is a term of type `Prop` (just like the types we saw earlier were terms of type `Type`). Let RH denote the statement of the Riemann Hypothesis. Then `RH : Prop`. We don’t care if it’s true, false, independent of the axioms of mathematics, undecidable, whatever. A Proposition is a true/false statement. Let’s look at the part of Lean’s type theory hierarchy which lives in the `Prop` universe. -->

「すべての自然数 $x$ について $x + 0 = x$ である」という文は命題です．Lean では，これは `(∀ x : ℕ, x + 0 = x) : Prop` と表せます．命題は `Prop` 型を持つ項です．（先ほど見てきた項が型 `Type` を持っていたのと同様です）RH をリーマン仮説のステートメントとします．すると `RH : Prop` となります．それが真か偽か，特定の数学の公理と独立であるか，決定不能であるか，等は問いません．命題とは真か偽かどちらかになる文のことです．Lean の型理論の階層のうち，`Prop` 宇宙に住む部分を見てみましょう．

<!-- * Universe: `Prop` -->
* 宇宙 : `Prop`
<!-- * Examples of types : `2 + 2 = 4`, `2 + 2 = 5`, the statement of Fermat’s Last Theorem, the statement of the Riemann Hypothesis. -->
* 具体的な型 :  `2 + 2 = 4`, `2 + 2 = 5`, フェルマーの最終定理のステートメント，リーマン仮説のステートメント
<!-- * Examples of terms: ?? -->
* 具体的な項 : ??

<!-- So what are the terms in this three-layer `Prop` hierarchy? They are the proofs! -->

この３層構造の `Prop` 階層において，項にあたるものは何でしょうか？それは証明です！
