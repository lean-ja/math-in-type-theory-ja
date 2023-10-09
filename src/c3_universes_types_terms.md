<!-- # Universes, types, and terms. -->
# 宇宙，型，項

<!-- In type theory, everything is a term. But some terms are types. Not every term is a type, but every term has a type. A colon is used to express the type of a term in Lean — the notation `x : T` means that `x` is a term of type `T`. For example, the real number $\pi$ (pi) is a term in Lean, and the real numbers ℝ is a type, and we have $\pi$ : ℝ , that is, $\pi$ is a term of type ℝ. In set theory one writes $\pi\in\mathbb{R}$ , in type theory we write $\pi$ : ℝ. They both express the same mathematical concept, namely “$\pi$ is a real number”. -->

型理論では，すべてが項です．そしていくつかの項は型でもあります．すべての項が型であるわけではありませんが，すべての項は型を持っています．Lean では，コロンを使って項の型を表します．―― `x : T` という表記で，`x` が `T` という型の項であることを表します．たとえば，実数 $\pi$ は Lean の項であり，実数全体 $\mathbb{R}$ は型であり，`π : ℝ` が成り立ちます．つまり，$\pi$ は型 $\mathbb{R}$ の項です．集合論では $\pi\in\mathbb{R}$ と書きますが，型理論では `π : ℝ` と書きます．どちらも同じ数学的概念，つまり「$\pi$ は実数である」を表します．

<!-- Now $\pi$ is a term but it’s not a type. In Lean, `x : π` makes no sense. In set theory, $x\in\pi$ does happen to make sense, but this is a weird coincidence because everything is a set. Furthermore, the actual elements of $\pi$ will depend on how the real numbers are implemented (as Dedekind cuts or Cauchy sequences, for example), and hence in set theory $x\in\pi$, whilst being syntactically valid in theory, has no mathematical meaning; it happens to make sense, but this is a quirk of the system. If you’re adamant that $x\in\pi$ should make sense then I say you’ve been brainwashed by set theory. Gauss and Euler will put you right: they were proving theorems about the real numbers before Cauchy and Dedekind came along with their sequences and cuts. There is no reason that $\pi$ needs to have elements, this is a quirk of the set-theoretic foundations of mathematics, and this quirk is eliminated in a type theoretic foundation. -->

いま $\pi$ は項ですが，型ではありません. Lean では `x : π` は意味を持ちません．集合論では，$x\in\pi$ は意味を持ちますが，これは集合論において全てが集合であることに起因する，奇妙な偶然です．さらに，$\pi$ の実際の要素は，実数がどのように実装されるか（たとえばデデキント切断としてか，コーシー数列としてか）に依存するため，集合論での $x\in\pi$ は，構文的には意味を持つものの，数学的な意味はありません．たまたま意味をなすだけで，システムの癖に過ぎません．もし「 $x \in \pi$ には意味があるはずだ」
とあなたが断固として言うなら，「あなたは集合論に洗脳されているのだ」と私は言うでしょう．ガウスとオイラーがあなたを正しい方向に導いてくれるでしょう：ガウスとオイラーは，コーシーとデデキントが数列と切断を導入する以前に，実数に関する定理を証明していました．$\pi$ が要素を持つべき理由はありません．これは数学の基礎に集合論を使った際の癖であり，その癖は型理論を使った場合には解消されます．

<!-- I claimed above that every term has a type. So what is the type of ℝ? It turns out that `ℝ : Type`. The real numbers are a term of a “universe” type called `Type` — the type theory analogue of the class of all sets. -->

先ほど，すべての項は型を持つと書きました．では `ℝ` の型はなんでしょうか？`ℝ : Type` が答えです．実数全体は，`Type` と呼ばれる「宇宙」型の項です ―― これは「すべての集合がなすクラス」の型理論における類似物です．

<!-- Many of the mathematical objects which mathematicians think of as definitions either have type `Type`, or have type `T` where `T : Type`. As a vague rule of thumb, the stuff which has elements (groups, rings, fields etc) has type `Type`, and the stuff which doesn’t have elements ($\pi$, $\sqrt{2}$ or an element $g$ of a general group) has type `T` where T is some type. As another vague rule of thumb, things we write using capital letters (a group, a ring,…) or fancy letters (the reals, the rationals) tend to have type `Type`, and things we write using small letters (an element g of a group, a real number r or an integer n) tend to have type `T` where T is what we think of as the set which contains these things. For example `2 : ℕ` and `ℕ : Type`, or if $g$ is an element of the group $G$ then in Lean we have `g : G` and `G : Type`. You can see that there is a three-layer hiearchy here — terms at the bottom, types above them, and the universe at the top. -->

数学者が定義する数学的対象の多くは，型 `Type` を持つか，あるいは `T : Type` であるような型 `T` を持ちます．漠然とした経験則ですが，要素を持つもの（群，環，体など）は `Type` 型を持ち，要素を持たないもの（$\pi$, $\sqrt{2}$ や一般の群の要素 $g$）は `T` 型を持ちます．もう一つのあいまいな経験則として，大文字で書くもの（群や環など）や fancy letter（実数 ℝ や有理数 ℚ ）で書くものは `Type` 型を持ち，小文字で書くもの（群の要素 $g$ や実数 $r$, 整数 $n$）は `T` 型を持つ傾向にあります．たとえば `2 : ℕ` と `ℕ : Type` が成り立ちます．また $g$ が群 $G$ の要素であるとき，Lean では `g : G` と `G : Type` が成り立ちます．ここには３層の階層があります ―― 一番下に項があり，その上に型があり，最上部に宇宙があります．

<!-- * Universe : `Type` -->
* 宇宙 : `Type`
<!-- * Examples of types : `ℝ`, `ℕ`, `G` (a group), `R` (a ring), `X` (something a set theorist would call a set), a Banach space, etc. Formally, we say `ℝ : Type`. -->
* 具体的な型 : `ℝ`, `ℕ`, `G` (群), `R` (環), `X` (集合論者が集合と呼ぶなにか), バナッハ空間など. 形式的には `ℝ : Type` などと書きます.
<!-- * Examples of terms: `π` (a term of type `ℝ`), `g` (an element of the group `G`, so a term of type `G`), `x` (an element of `X`, so a term of type `X`). Formally, we say `g : G`. -->
* 具体的な項 : `π` (型 `ℝ` の項), `g` (群 `G` の要素, つまり型 `G` の項), `x` (`X` の要素, つまり型 `X` の項). 形式的には `g : G` などと書きます.

<!-- This hierarchy is more expressive than the hierarchy in set theory, where there are only two levels: classes (e.g. the class of all sets), and sets. -->

この階層は，クラス（たとえばすべての集合のクラス）と集合の２つのレベルしかない集合論の階層よりも，表現力が高いです．

<!-- There is a standard use of the colon in mathematics — it’s in the notation for functions. If X and Y are sets (if you’re doing set theory) or types (if you’re doing type theory), then the notation for a function from `X` to `Y` is `f : X → Y`. This is actually consistent with Lean’s usage of the colon; Lean’s notation for the collection $\mathrm{Hom}(X,Y)$ of functions from `X` to `Y` is `X → Y` , which is a type (i.e. `X → Y : Type`, corresponding to the fact that set theorists think of $\mathrm{Hom}(X,Y)$ as a set), and `f : X → Y` means that `f` is a term of type `X → Y`, the type-theoretic version of $f \in \mathrm{Hom}(X,Y)$, and the way to say that `f` is a function from `X` to `Y` in type theory. -->

数学におけるコロンの標準的な使い方があります．―― 関数を書くための記法です．`X` と `Y` が集合（集合論を使っている場合）または型（型理論を使っている場合）であるとき，`X` から `Y` への関数を `f : X → Y` と書きます．これは実は Lean におけるコロンの使い方と一致しています．`X` から `Y` への関数の集まり $\mathrm{Hom}(X,Y)$ に対する Lean の表記法は `X → Y` であり，これは型です．（つまり `X → Y : Type` です．これは集合論で $\mathrm{Hom}(X,Y)$ を集合と考えることに対応しています）`f : X → Y` は `f` が `X → Y` 型の項であることを意味し．集合論でいう $f \in \mathrm{Hom}(X,Y)$ に対応します．これは型理論において，`f` が `X` から `Y` への関数であることを書き表すやり方です．

<!-- (Not for exam) Strictly speaking, universes are types, and types are terms, but this is a linguistic issue: often when people speak of types, they mean types which are not universes, and when people speak of terms they mean terms which are not types. But not always. This confused me when I was a beginner. -->

（これは試験に出ません）厳密に言えば，宇宙は型であり，型は項ですが，これは用語の問題です．多くの場合，ひとが型について語るとき，それは宇宙ではない型を意味し，ひとが項について語るとき，それは型ではない項を意味します．しかし常にそうとは限りません．私が初心者の頃は，これで混乱しました．
