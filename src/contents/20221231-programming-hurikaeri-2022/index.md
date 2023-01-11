---
path: /programming-hurikaeri-2022
created: "2022-12-31"
title: 2022年に勉強した技術
visual: "./visual.png"
tags: [振り返り, 雑記]
userId: sadnessOjisan
isFavorite: false
isProtect: true
---

皆がやってるのを見てると自分もやりたくなってきました。
こうことを表明することが次のキャリアにつながるのだと思っています！

## 学んだ技術

### React & Next

自分は react v16.8, Next v9 以降の知識があまりないです。
なぜなら無くても困らなかったからです。
が、フロントエンドエンジニアを名乗る以上流石に勉強しないとなと言うことで勉強しました。

React は新機能を周りを reactwg の discussion を眺めていました。

FYI: https://github.com/reactwg/react-18/discussions

この辺りの情報は docs の beta にまとめられているらしいので年始にでも読もうと思います。

FYI: https://beta.reactjs.org/

Next に関してはドキュメントを一通り読み直していました。
Next は v6 くらいから prd で使っていてかなり貯金がある技術なのですが、すこしキャッチアップをサボると知らないことが増えすぎていて大変でした。
やはりリリースされた後のリリースノート読み会とかにはちゃんと参加しないとなと思いました。

またいま React の内部実装を一緒に読んでくれる人が見つかったのでその準備をしています。来年は内部実装を読もうと思います。preact を読んだ時の話は

- [preact の仕組みを理解する軽量版教育用 preact を作ってる話](https://speakerdeck.com/sadnessojisan/preactfalseshi-zu-miwoli-jie-suruqing-liang-ban-jiao-yu-yong-preactwozuo-tuteruhua)
- [preact コードリーディング](https://blog.ojisan.io/preact-reading/)

にあります。preact と違って schedular が複雑という前情報があってそのアイデアを学びたいです。後述しますが最近 schedular という概念そのものの勉強をしていて（特に非同期ランタイム文脈）、その勉強をしてから React を見つめ直すと結構面白そうだったのでモチベーションがあります。

### Scala

[t-wada さんの研修資料](https://speakerdeck.com/rtechkouhou/enziniatositekofalsexian-sheng-kifalsekorutameni?slide=25)を見てから毎年新しい言語を趣味で覚えるようにしているのですが、今年は Scala をしました。たまたま書く機会がいまあるというのと、今年弊社に入ってきた新卒の子が Scala のプロみたいな人で熱心な布教を受け、「教えてくれるのなら、、、まぁ、、、」と初めてみました。結果、めちゃくちゃ好みの言語だと思いました。

去年は Rust を勉強していました。それは安全装置と機能がたくさんついている言語が欲しかったからです。ただそれと同時に所有権周りが難しくて「GC があればいいのに」と思いながら書いていました。それは Rustacean に怒られる発言かもしれませんが自分は本気で思っています。自分にとっては Rust は Web サーバーを書くためで、結局 FW が無邪気に clone を要求したりするのを見ると「GC あり言語でええやん」となりました。サーバーに関しては純粋な比較をするとコンテナとの相性とかで Rust を使いたい理由はまだまだあるのでしょうが、「JVM も十分素晴らしいじゃないの」と思っているので、パフォーマンスをさらに限界まで高めたいと言う気持ちになったことがなく、あまり Rust のそういう面が自分に刺さっていないと言うのがあります。あとは Wasm も触りますが、普段はオモチャしか作らないし、本番ではエッジでしか動かさないので GC あり言語でもいいかなぁというのが最近の感覚です。

そして Rust に GC を足したものを考えると自分は Scala がこれに当てはまりました。パターンマッチも Result も if 式もあって自分が Web プログラミングしたいときに欲しいものが揃っていました。特に Result は cats エコシステムが強力で Rust では表現できなかったことが色々できて良かったです。

その辺りの勉強は

- [Monad は継続、Applicative は並列](https://blog.ojisan.io/monad-applicative/)
- [Free モナドは何が嬉しいか](http://blog.ojisan.io/how-to-use-free-monad/)

に書きました。

実は Scala が自分が一番求めていた言語だったのかもしれないと思って最近は勉強するようにしています。ただ sbt 周りが難しくて苦戦しています。

### Python + Django

仕事でいわゆる API 仕様書を改善したい部分があったので、職場で採用していた Python + Django を覚えました。

白状するともともと Python や Django に対しては僕は非常に悪い印象しかありません。この手のサーバーは API 仕様書がないか、間違っているという契約を反故にされる経験しかなかったからです。実際のところ言語自体に静的な型がないため、型とバリデータと Spec を一致させるのが難しいと思います。フロントエンドエンジニアとしてサーバーに求めるのは [API 仕様書をバリデーターと型と同期させて作る](https://blog.ojisan.io/swagger-validator-ts/) の世界です。

が、（古い）Python には 静的な型がないものの クラスとインスタンスがあるので Django では Model を使うことで API Spec を吐けることがわかりました。
このような仕組みをどう既存システムに落とし込むかと言う勉強を今年はしました。
たとえば [持続可能なスプラトゥーン３反省システム](https://blog.ojisan.io/splatoon3-hansei-site2/) などはちゃんと Spec もはけていますし、そこから API クライアントを自動生成して Astro に繋ぎこむみたいなことができてい普通に使えています。
重量級 FW は Admin や ORM や Migration が付いてくるというのも良く、短期間でこのサービスを作ることができました。
あとなんだかんだで Python にはなんでも揃っていると言うのが良かったです。

### 非同期ランタイム

非同期ランタイムは去年から [並行プログラミング入門 ―Rust、C、アセンブリによる実装からのアプローチ](https://www.amazon.co.jp/dp/4873119596)を読むなどをし、[サーバー入門、非同期処理入門、epoll 入門](https://blog.ojisan.io/how-to-epoll/) を書いたりしていました。

このときはあまり根から理解できていたわけではないのですが、今年また読み直すと理解が深まったので、理解できるところまで理解しようと思い勉強しました。これには Scala を勉強したことで cats-effect 方面から理解のブレイクスルーがあったという出来事もあります。

- [ライブラリを使わない非同期処理（前編）](https://blog.ojisan.io/think-rust-async-part1/)
- [ライブラリを使わない非同期処理（後編）](https://blog.ojisan.io/think-rust-async-part2/)

これまでは自分は JS エンジニアということもあり、シングルスレッドでの非同期処理についてでしか理解していませんでしたが、今年理解が深まったのはマルチスレッドでの非同期処理と OS に対する感覚です。コンピューターにはなんらかのリソースがあって、それを複数の主体が奪い合うという感覚が得られました。マルチスレッドでの非同期処理では概念的には CPU コアの数だけワーカー立ててその中でシングルスレッドの非同期ランタイムを動かせば良いというのが理解できました。

さらに tokio のコードリーディングを通してスレッド間でタスクを奪える work steal の概念も学びました。これは自分は世紀の発見に思えましたが、その筋の人たちでは王道の初歩的なテクニックらしいです。work steal は cats effect も採用していて、ここでも Scala の勉強が役に立ちました。

FYI: <https://typelevel.org/blog/2021/02/21/fibers-fast-mkay.html>

非同期ランタイムの勉強は去年までに比べるとかなり今年は進みました。しかしまだ理解できていないものがあります。それがグリーンスレッドとアクターモデルです。グリーンスレッドはコンテキストスイッチ実装のためのアセンブリがほとんど書けないので後回しにしていました。暇な時に <https://godbolt.org/> に Rust のコード入れて比較して遊ぶとかはやっていましたがあまり身についていないです。が、もう逃げられないと思っているので気合をいれて向き合おうと思います。この辺りは「Go は独自の ABI がなんちゃらでパフォーマンスが良い」みたいな話があると思うのですが、この辺りを人に説明できるようになるのがまずは目標です。

アクターモデルに関しては自作グリーンスレッドができたらその上に作るというのを目的にしています。アクターモデルはちゃんと理解できていませんが、幸いなことに今 Scala で Akka を書く機会があるので、メンタルモデルくらいは身についていて欲しいなと期待しています。

### VCL

今の職場はおそらく日本で一番長い VCL がある会社です。（知らんけど）
これまでは特に大きな仕事を任されたりしていなかったので、VCL 周りを理解しなくて済んでいたのですが、今年はサービスの開発を現コードベースを使わずにまるまる任されると言うミッションが与えられて、VCL 含め社内の基盤と向き合う必要がありました。
そのため VCL の設定を自分で書くこととなりました。
ある程度は雛形があるのですが、一発でうまく行くはずもなく結局は雛形の仕組みを理解したりする必要がありました。
暇な時に fastly の docs を読んでいました。
VCL だけでなく HTTP の解説からあるのでとても勉強になります。

FYI: <https://docs.fastly.com/>

これらを読んだおかげで HTTP Caching 自体の知識が増えたことはもちろん、VCL の仕組み自体も知れました。ただ先輩方に比べるとまだまだなので、いまの職場で働く以上はこの勉強は継続しなきゃという感じです。
ただ同僚や新卒の子が無敵すぎて、「俺がやらなきゃヤバい」という危機感が生まれなくてあまり他の項目に比べるとやる気が出ないです。（やれ）

あと VCL ではないですが Fastly エコシステムには自分で契約したこともあって詳しくなており、

- [Fastly に自ドメインを設定する](https://blog.ojisan.io/fastly-domain-config/)
- [ご報告ブログの裏側をお見せします](https://blog.ojisan.io/gohoukoku-backyard-tour/)

などを書いています。C@E を使えるのは Rust を勉強していて良かったと思いました。

## 来年は何を勉強する？

自分の将来をどうするかとも密接に関わるのでまだ決めれていないのですが、選択肢としては、今年の積み残し +

- TypeScript
- システムアーキテクト
- 開発マネジメント
- テクニカルライティング
- 英語

のどれかです。

来年はエンジニアをやめることが視野に入っています。伸び代の上限値が見えてきたので。もうワシはダメぽよ。