# 2章

## 2.1　Elementary Probability Theory

本書で使われる確率論の要点を流れの中で挙げるスタイルなので、
勉強するなら別途教科書等を読むのが良い。

2.1.2以降はPRML1.2-1.2.4とほぼ対応しており、
個人的には黄色いほうがわかりやすいと思う。

ので、若干、本書の流れを無視して、先に説明を書く。

----

2つの事象`X`と`Y`が同時に起きる確率をsimultaneous probability(同時確率)[p.43]と呼ぶ。

<img src="https://latex.codecogs.com/gif.latex?p(X\cap&space;Y)" /> 若しくは <img src="https://latex.codecogs.com/gif.latex?p(X,Y)" />

これを全ての`Y`について合算したものを **sum rule(加法定理)** と呼ぶ。

<img src="https://latex.codecogs.com/gif.latex?p(X)=\sum_{Y}p(X,Y)" />

これは`Y`についての周辺化なのでmarginal probability(周辺確率)[p.43]とも。

事象`Y`が起きたもとでの事象`X`の起こる確率をconditional probability(条件付き確率)[p.38]と呼び、

<img src="https://latex.codecogs.com/gif.latex?p(X\mid&space;Y)" />

同時確率との間に **product rule(乗法定理)** が成り立つ。

<img src="https://latex.codecogs.com/gif.latex?p(X,Y)=p(X|Y)p(Y)" />

乗法定理の対称性から以下が成り立ち、これを **Bayes' theorem(ベイズの定理)** と呼ぶ。

<img src="https://latex.codecogs.com/gif.latex?p(Y\mid&space;X)=\frac{p(X\mid&space;Y)p(Y)}{p(X)}" />


## 2.1.1 Probability spaces

以下、用語を覚えよう

- experiment 実験
- trial 試行
- basic outcome 基本結果
- sample space 標本空間
- event 事象
- σ-field 完全加法族
- event space 事象空間

- descrete 離散的
- continuous 連続的

## 2.1.2 Conditional probability and independence

条件確率は上の通り。

ベイズの定理で考えると、

- prior brobability(事前確率)

事象`X`が得られるより以前に得ている確率である<img src="https://latex.codecogs.com/gif.latex?p(Y)" />

- posterior probability(事後確率)

事象`X`が得られた後に得られる確率である<img src="https://latex.codecogs.com/gif.latex?p(Y\mid&space;X)" />

chain ruleはproduct ruleから導ける。

同時確率において、各事象が互いに影響しない場合、**独立** と呼び

<img src="https://latex.codecogs.com/gif.latex?p(X,Y)=p(X)p(Y)" />

を満たす。

## 2.1.3 Bayes’ theorem

ベイズの定理は上の通り。

## 2.1.4 Random variables

確率変数（かくりつへんすう、英: random variable, aleatory variable, stochastic variable）とは、確率論ならびに統計学において、ランダムな実験により得られ得る全ての結果を指す変数である[1]:391。 数学で言う変数は関数により一義的に決まるのに対し、確率変数は確率に従って定義域内の様々な値を取ることができる。
cite:https://ja.wikipedia.org/wiki/%E7%A2%BA%E7%8E%87%E5%A4%89%E6%95%B0

## 2.1.5 Expectation and variance

確率変数の平均のことを期待値と呼ぶ。

<img src="https://latex.codecogs.com/gif.latex?E[x]=\sum_{x}xp(x)" />

確率変数のばらつきを分散と呼ぶ。

<img src="https://latex.codecogs.com/gif.latex?Var[x]=E[x^2]-E[x]^2" />

分散の平方根を標準偏差と呼ぶ。

離散的なのはコーパスを前提としているから？

## 2.1.6 Notation

- 大文字の`P`は確率関数
- 小文字の`p`は確率変数

## 2.1.7 Joint and conditional distributions

結合分布は同時分布のまたの名。

なんで2.1.9より先に分布が出てくるのか。。。

## 2.1.8 Determining P

- パラメトリック

母集団の分布に仮定を置く

- ノンパラメトリック

母集団の分布に仮定を置かない

## 2.1.9 Standard distributions

- 二項分布

連続する単語間の依存性を無視したならば、単語の出現は二項分布に従うと見なせる（が。。。まあ）

- ガウシアン(正規分布)

## 2.1.10 Bayesian statistics

ここはPRML準拠で

以上の、確率をランダムな試行の繰り返しとみなす考え方をclassical probability(古典的確率)またはfrequentist(頻度主義的)と呼ぶ。

古典的確率では例えば、1000羽のカラスを調べて全て黒だったときに1001羽目が白である確率は0になるが、ベイズ統計なら0にならないように出来る。

事前確率分布を<img src="https://latex.codecogs.com/gif.latex?p(w)" />、観測データを`D`としたとき、
ベイズの定理から、

<img src="https://latex.codecogs.com/gif.latex?p(w\mid&space;D)=\frac{p(D\mid&space;w)p(w)}{p(D)}" />

この時、右辺の<img src="https://latex.codecogs.com/gif.latex?p(D\mid&space;w)" />は`w`の元での`D`の起こりやすさを表し、尤度関数と呼ばれる。
なので、ベイズの定理は以下の関係性を満たす。

事後確率 ∝ 尤度 × 事前確率

頻度主義では尤度関数を最大にする`w`を選ぶ（最尤推定）。
ベイズ統計では`w`は不確実性を与える確率分布に従うと考える。

この時、事後確率は観測によって事前確率を修正したものと見なせる。
このようにして、事前確率を更新していくことをベイズ更新と呼ぶ。
