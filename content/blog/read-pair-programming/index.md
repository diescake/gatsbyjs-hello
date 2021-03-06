---
title: 「はじめてのペアプロ / モブプロ」を読んだメモ
date: '2019-01-08T19:12:03.284Z'
---

去年の反省の 1 つであるが、一般的なパラレルに開発して上がってきた PR をコードレビューしてマージするという開発スタイルにあらゆる意味で限界を感じていて、ペアプロ、あるいはモブプロを取り入れるべく検討していた。

早速 Discord で頼れる有識者達に相談してみたところ、WEB+DB PRESS の特集を紹介いただき読んでみた。関係者間で要点をシェアするためのメモとして本記事を書いている。実際に実施して適宜加筆していきたい。

- WEB+DB PRESS Vol.102 (2018/1 月号)
  - はじめてのペアプロ / モブプロ

[https://gihyo.jp/magazine/wdpress/archive/2018/vol102:embed:cite]

[:contents]

# ペアプロ

## 効果的なタイミング

- 新メンバーがジョインしたとき
  - キャッチアップする最速の方法
- 新機能を実装するとき
- デバッグや不具合修正を行うとき
  - 複数の観点によってデグレ防止に有効
- 定期開催
  - Daily / Weekly
    - Daily なら 1h, Weekly なら 3h とか
- 技術的負債の返済日

## 進め方

### 1. コードを書く前に方向づけを行う

- 最終目標を決める
- 作業項目をリストにする
  - 開発中も都度更新していく

```md
    - [x] 新規画面の追加
    - [ ] データ取得 API の呼び出しと表示
    - [ ] CSS を書いてデザインを実装
    - [ ] リファクタリング
    - [ ] 動作検証
```

- 最初の目標を決める
  - リスト化して作業を開始
  - 小さい作業項目から着手して流れを作るのがよい

### 2. コードを書きながら会話し、考えを共有する

- ドライバー
  - 考えていることを口に出す
  - 実況のように、よく喋ることが重要
  - 思考をそのまま口にする
- ナビゲーター
  - よく聞き、ドライバーを支える
  - 実況に対してコメント、評価、盛り上げる
  - 同時にコードレビュー
  - 立ち止まって設計の共有
  - 視野を広く持つことが大事

### 3. ロールを交代する

ドライバーの方が消耗が激しいため、ローテーションするのが基本

- 時間で交代する
  - 15 分くらいの交代が目安
- ステップで交代する
  - Pair Programming Ping Pong Pattern
  - 作業項目単位での交代
- 適宜自由に交代する
  - ある程度慣れた人向け

## 注意点・コツ

- ドライバーの正面にキーボードを置く
- 定期的に休憩を取る
  - ロール交代の際に適宜取ると良い
- 開発環境差異の問題
  - 非常に悩ましく、完全な解決方法はない。下記はいずれも対策の一例
    - 各自キーボードを持ち寄る
    - チームメンバーでエディタ、環境を統一してしまう
    - ペアプロ用にデフォルト設定の環境を別途用意する
  - リアルタイム共同編集機能を持つエディタを利用する
    - ペアプロの最終型。これが可能であればベストだがエディタを揃える必要があるか？
    - 同時に編集できなくとも、ツリーをファイルサーバ上に配置したり、dropbox を利用する等でリアルタイムにソースコードを共有して PC をスイッチしやすくするのはどうか？(IMHO)
  - ステップで交代する場合は `push / pull` してドライバーの PC にスイッチするのはどうだろうか？(IMHO)
- メンタル的にペアプロが合わない人もいる
  - 強要してペアプロハラスメントに陥らないこと
  - ただし、単に食わず嫌いの人は多い

# モブプロ

ペアプロでは、ペア以外のチームメンバーへ情報が伝達されにくいという問題がある。例えば、チケットや PR に試行内容とその結果、コードレビューのやり取り等が残らない。**よし、ならば全員同席だ。** ➔ モブプロ

- 3〜5 人が適正
- できる限り大画面を用意する
  - 調べ物用の PC がもう 1 台あると良い
- ナビゲーターそれぞれが課題を調査する

正直なところ、ペアプロほどメリットがスッと頭に入ってこなかったが、とりあえずやってみて考える。
