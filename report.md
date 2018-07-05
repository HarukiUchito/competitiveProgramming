### 行き詰まったら考えること
 - 制約を確認，明らかに少ないところを利用することを考える．
 - DP, 2分探索
 - 答えを式で表してみる．簡単にできる場所があるはず．


### 要分類！テクニック
#### Backfront
https://beta.atcoder.jp/contests/agc024/tasks/agc024_b
1ずつ増えてく最長増加部分列を求める．
単にLISのライブラリを貼るだけではできない．


### 要復習
https://csacademy.com/contest/round-77/task/expected-lcp/statement/
http://codeforces.com/contest/959/problem/D　　
https://beta.atcoder.jp/contests/abc058/tasks/arc071_b

#### 倍々ゲーム
https://beta.atcoder.jp/contests/abc027/submissions/2272402  
無理

#### Minimum Sum
https://beta.atcoder.jp/contests/agc005/submissions/2292338  
区間を管理するという発想．天才の所業．

### AtCoder Grand Contest

#### BBuBBBlesort!
https://beta.atcoder.jp/contests/agc003/submissions/2290865  
3要素を反転するのは，1要素目と3要素目を入れ替えているだけなので，数列全体の偶数番目にあったものは入れ替えても偶数番目である．2要素を反転すると偶奇を入れ替えられる．

### Setが便利に使えるやつ
#### Merge Squares
http://codeforces.com/contest/962/submission/37292780  
値と場所をペアにしてSetで持つ．すると，同じ値が並ぶので同じとこがあったら両方消して和を入れる．一つだけになったのは消さないと，最初から見ていくのでTLEする．

### ゲーム木
#### 双子と○×ゲーム
https://beta.atcoder.jp/contests/abc025/submissions/2272738  
五目並べみたいなゲーム，再帰で全通りシミュレーション  

#### 収集王
https://beta.atcoder.jp/contests/abc023/submissions/2271970  
基本的によくわからない  
N個の個数を数える配列を作るときは0個の場合も含めてN+1個の要素が必要  


### 貪欲法

#### 飛行機乗り
https://beta.atcoder.jp/contests/abc030/submissions/2272262  
貪欲法は行けるとこまでインデックスを移動させて配列の外に出そうだったらすぐ抜けるという戦略が大事なのかも  


### 2分探索

#### Maximizing the Profit
https://www.hackerrank.com/contests/hourrank-27/challenges/maximizing-the-profit/submissions/code/1306977772  
ある場所における積を求めるときにその左右の集合（重複を許すのでMultiset）を管理しておいて単に最大値か最小値を取るのが最適   
使える値は2分探索できるが，lower_bound(begin, end, v)ではなく, multiset.lower_bound(v)を使わないと遅い  

#### 花束
https://beta.atcoder.jp/contests/arc050/submissions/2273389  
midの条件を花束についての不等式の上で考える  
最初のlb, ubの範囲をきちんととる  

#### 射撃王
https://beta.atcoder.jp/contests/abc023/submissions/2291920  
解を仮定 -> ある高さX以下を保って全てを割れるか？  
Xを2分探索  

### 45度回転

#### Moving the Kings
https://www.hackerrank.com/contests/hourrank-27/challenges/moving-the-kings  
マス上での8方向の移動を考える時，コストはmax(x-x', y-y')  
このようなmax関数の和は，45度回転した座標系の上では絶対値だけの式になる  
配列中の各値とある一つの値の差の絶対値の総和は，最初にソートしておくことでO(1)で得られる  
ソートしておくと，ある一つの値より大きいものと小さいものの集合を考えると絶対値記号を外せる  


### 条件を満たすように構築する問題
https://beta.atcoder.jp/contests/arc093/submissions/2375874  
最初は余裕を持って構築してみてできないかを考える



### 動的計画法

#### Two Rows
https://csacademy.com/contest/archive/task/two-rows  
片方は最大化，片方は最小化を目指す形式  
空間のテーブルを両者分持って，どちらも最適に動いた場合を相手のテーブルを参照しながら計算する  

#### yuki No.472 平均順位
https://yukicoder.me/submissions/255233  
x問これまでに正解しているという状態を考えたい時，
今回正解する数a＋前回までにx-a問正解したときの最小値が答えになる．  
愚直に全状態を計算すると空間計算量オーバー．  
必要なのは前回の状態だけなので，問題数だけの配列が2本あれば足りる．  

#### Mixing Experiment
https://beta.atcoder.jp/contests/abc054/submissions/2451784  
dp[iまでの薬品で][物質Aがjグラム][物質Bがkグラム] になるときの最小コスト  
上のようにテーブルをとると，ある状態から，薬品iを使うかどうかで2箇所決められる．  
全体を順次最小化していく．  
