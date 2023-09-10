<!-- # Definitions, true/false statements, and proofs -->
# 定義，命題，証明

<!-- In contrast to ideas, the other parts of mathematics (the definitions, theorems/conjectures, and proofs) can be formalised in a foundational system, and hence can be created and stored on a computer in a precise way. By this, I don’t mean a pdf file! Pdf files are exactly what I want to move away from! I mean that people have designed computer programming languages which understand one of the various foundations of mathematics (set theory, type theory, category theory) and then mathematicians can write code in this language which represents the definition, true/false statement or proof in question. -->

アイデアとは対照的に，数学の他の部分（定義，定理/予想, 証明）は基礎的なシステムで形式化することができ，したがって精確な方法でコンピュータ上に作成・保存することができます．これは pdf ファイルのことではありません！pdf ファイルこそ，私が脱却したいものなのです！つまり，様々ある数学の基礎付け（集合論，型理論，圏論）のうち1つを理解するコンピュータプログラミング言語が設計されており，その言語で数学者が問題の定義，命題，証明を書くことができるということです．

<!-- I am certainly not qualified to explain how all this works in category theory. In set theory, let me just make one observation. A definition in set theory, for example the definition of the real numbers, or $\pi$, is a set. And a proof is a sequence of steps in *logic*. A definition and a proof seem to me to be two completely different things in set theory. A group is a mixture of these things — a group is an ordered quadruple $(G,m,i,e)$ satisfying some axioms, so it’s a set with some logic attached. -->

私には，圏論でどのように数学の基礎付けを行うのかを説明する資格はありません．集合論について，ひとつだけ観察してみましょう．集合論における定義，たとえば実数や $\pi$ の定義は集合です．そして証明とは，論理のステップをつなげたものです．集合論において，定義と証明は全く異なるもののように私には思えます．群とは，定義と証明の混合物です．―― 群とは，順序付き4つ組 $(G,m,i,e)$ であって，特定の公理を満たすもののことです．つまり，論理が付属した集合です．

<!-- In type theory however, things are surprisingly different. All three things — definitions, true/false statements, and proofs — are *all the same kind of thing*! They are all **terms**. A group, a proof, the real numbers — they are all terms. This unification of definitions and proofs — of sets and logic — are what seems to make type theory a practical foundational system for teaching all undergraduate level mathematics to computers. -->

しかし，型理論では驚くほど違います．今挙げた３つのもの ―― 定義，命題，証明 ―― はすべて同じ種類のものです！これらはすべて**項**です．群，証明，実数 ―― これらもすべて項です．定義と証明の統一，つまり集合と論理の統一が，型理論を実用的な基礎システムたらしめ，コンピュータに学部レベルのすべての数学を教えることを可能にしています．
