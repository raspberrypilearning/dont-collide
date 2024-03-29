## はじめに

キャラクターが障害物との衝突を避けて走り続けるエンドレス・ランナー・ゲームを作ります。

<p style="border-left: solid; border-width:10px; border-color: #0faeb0; background-color: aliceblue; padding: 10px;"> 
<span style="color: #0faeb0">**エンドレスランナー**</span> は、障害物を避け続け、障害物にぶつかるまで終わらないタイプのゲームです。 できるだけ長く生き続けることでポイントを獲得します。</p>

次のことを行います。
+ 何が起こるかを制御するのにゲームの **条件** を使います
+ 手続き型生成と衝突検出について学びます
+ あなたの興味に合わせてゲームをパーソナライズします

![さまざまなプロジェクト例の画像。](images/showcase_projects.png)

### インスピレーションを得る

作成するゲームの種類と、必要な効果を得るためにコードをどのように使うかについて、いくつかの設計上の決定を行います。

--- no-print ---

--- task ---

これらの例を見てください。 プレイヤーと障害物がどのように作られたかを考えてください。

障害物にぶつかるとどうなりますか？ ゲームが進むにつれて難しくなりますか？

<div style="display: flex; flex-wrap: wrap">
<div style="flex-basis: 175px; flex-grow: 1">  

**ネコのスキー**: [中を見る](https://trinket.io/python/ee04c6d6e1){:target="_blank"}
<div class="trinket">
<iframe src="https://trinket.io/embed/python/ee04c6d6e1?outputOnly=true" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
</div>

**割れちゃダメ**: [中を見る](https://trinket.io/python/31f337454a){:target="_blank"}
<div class="trinket">
<iframe src="https://trinket.io/embed/python/31f337454a?outputOnly=true" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
</div>

**バイキンを避けて**: [中を見る](https://trinket.io/python/740183c0e0){:target="_blank"}
<div class="trinket">
<iframe src="https://trinket.io/embed/python/740183c0e0?outputOnly=true" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
</div>


**きれいなクルマ**: [中を見る](https://trinket.io/python/72bca7fbe3){:target="_blank"}
<div class="trinket">
<iframe src="https://trinket.io/embed/python/72bca7fbe3?outputOnly=true" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
</div>

**小惑星を避けて**: [中を見る](https://trinket.io/python/2c077820d3){:target="_blank"}
<div class="trinket">
<iframe src="https://trinket.io/embed/python/2c077820d3?outputOnly=true" width="100%" height="600" frameborder="0" marginwidth="0" marginheight="0" allowfullscreen></iframe>
</div>

</div>
</div>

--- /task ---

--- /no-print ---

--- print-only ---

作成するゲームの種類と、必要な効果を得るためにコードをどのように使うかについて、いくつかの設計上の決定を行います。

![小惑星を避けてプロジェクトの例](images/example1.png){:width="300px"}
![ネコのスキープロジェクトの例](images/example2.png){:width="300px"}
![バイキンを避けてプロジェクトの例](images/example3.png){:width="300px"}
![割れちゃダメプロジェクトの例](images/example4.png){:width="300px"}
![きれいなクルマプロジェクトの例](images/example5.png){:width="300px"}

--- /print-only ---
