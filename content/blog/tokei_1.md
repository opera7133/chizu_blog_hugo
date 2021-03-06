---
title: "オレオレ流確率分布の手記"
author: "chizuchizu"
date: 2020-06-18
description: "できるだけ感覚を意識して確率分布について書きます。"
categories: ["統計学"]
tags: ["統計学"]
---

確率分布は忘れがちなので。



# 確率分布

　確率の分布である。

## コイントス系

最終更新（2020/06/18）

いわゆるベルヌーイ試行がベースになる。

> コイントスで表が出る回数がn回あるときの確率

中学数学でもやる内容。（この前学校でやった）それを一般化させたり拡張させたりすることで色んな分布が生まれる。



コインの表が出る確率をpとする。



普通のコイントスなら「表、裏が出る確率は同様に確からしい」とか言って0.5,0.5になるようになってるが、より一般的にするためにpとしている。コイントスと言っているが、同様に確からしくないコイントスも考える。

## ベルヌーイ分布(Be)

試行回数は1回。xには1か0が与えられるので、p=0.5だったら期待値も0.5。
$$
f_x(x)=p^x(1-p)^{1-x}
$$


## 二項分布(Bin)

ベルヌーイ分布を拡張させたもの。試行回数はn回。とても有名。Σとって二項展開すると全事象が1ということが示せる。
$$
f_x(x) = \binom{n}{x}p^x(1-p)^{n-x}, x=0, 1,...,n
$$

## ファーストサクセス分布(Fs)

初めて事象が起きるまでの試行回数が従う分布。マイナーかもしれない。
$$
f_x(x)=p(1-p)^{x-1}
$$

## 幾何分布(Ge)

初めて事象が起きるまでの失敗回数が従う分布。ファーストサクセス分布と似ている。名前からだと想像が付かない。😢
$$
f_x(x)=p(1-p)^{x}
$$

## 負の二項分布(NB)

n回成功するまでの失敗回数が従う分布。Be→Binの幾何分布verみたいなノリ。何でみんな失敗回数に注目するんだろう。と思ったら幾何分布の累乗がキリいいからか。
$$
f_x(x)=\binom{n+x-1}{x}p^{n}(1-p)^x
$$
というか、これだけだと暗記になりそうだからちゃんと導出してみるか。

とりあえず二項分布立ててみよう。

これが、Bin(n+x, x)。つまりn+x回の試行でn回成功し、x回失敗する確率分布。
$$
\binom{n+x}{n}p^{n}(1-p)^{x}
$$
ただ、最後は絶対成功だから試行回数と成功回数を1減らしてみる。
$$
\binom{n+x-1}{n-1}p^{n-1}(1-p)^{x}p = \binom{n+x-1}{n-1}p^{n}(1-p)^{x}
$$ {\binom{n+x}{n}p^{n}(1-p)^{x}
あれ、でも上の式と違う？？？

でも大丈夫！二項係数のところを計算してみたら一緒だから！！





# 更新記録

## 2020/06/18

- ベルヌーイ分布
- 二項分布
- ファーストサクセス分布
- 幾何分布
- 負の二項分布

の確率密度関数を書いた。期待値や分散はまだ書いてない。