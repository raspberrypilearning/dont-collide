--- question ---
---
legend: 質問2/3
---

このプロジェクトでは、手続き型生成を使いました。コンピューターにゲームなどの世界に部品を作って置かせる方法です。 この方法は時間の大幅な節約になりますが、特に非常に大きなレベルの世界を作る場合は、いくつかの問題が発生する可能性があります。 手続き型生成をテストするときに注意すべき問題はどれですか？

--- choices ---

- (x) これら全部

  --- feedback ---

正解！ これらはすべて、手続き型生成を使うときに起こる可能性があります。 これらの問題をチェックして避けるためにコードを追加するか、うまく行く乱数のタネが見つかるまで別のいろいろ試すことで問題に対処するかが必要です。

  --- /feedback ---

- ( ) プレーヤーが前に進めるルートがないように障害物が生成される。

  --- feedback ---

これだけではありません。 これは、特にゲームが最初にスタートしたとき、手続き的に生成された障害物で発生する可能性があります。


**ヒント：** 障害物がプレーヤーのスタート位置に近づきすぎないようにすることで、この問題を避けることができます。 他の解決策を考えられますか？

  --- /feedback ---

- ( ) プレイヤーの真下に障害物が現れる。

  --- feedback ---

これだけではありません。 これは、ゲームのスタート時、または難易度を上げた結果で新しい障害物が追加されたときに、たまたまプレイヤーの近くの位置であった場合に発生する可能性があります。


**ヒント：** 考えられる解決策は、レベルが上がった後しばらくの間、すべての障害物（または新しく生成された障害物だけでも）とぶつかってもプレーヤーは助かるようにすることです。 障害物がプレーヤーに近すぎる場所に障害物が新しい位置を選んだ場合、どのような問題が発生する可能性がありますか？

  --- /feedback ---

- ( ) 障害物はすべてグループ化され、何もない場所がたくさんできる。

  --- feedback ---

これだけではありません。 乱数発生では、互いに近い数がひとかたまりになることがあるため、この問題が発生する可能性はあります。


**ヒント：** ひとつの解決策は、セミランダム生成に切り替えることです。画面を細かく分け、それらの各部分の内部に乱数を使用して障害物を生成します。 この種の手続き型生成を使用して、ゲームをより面白く、またはより挑戦的にする方法を考えられますか？

  --- /feedback ---

--- /choices ---

--- /question ---