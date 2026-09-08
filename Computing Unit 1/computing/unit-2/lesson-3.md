### @explicitHints 1

# レッスン3: 家が並ぶ通りをコードする

## 建設エリア @unplugged
エージェンシーの建物の前にあるこの建設エリアに家を建てます。以下はサンプルの建物です。どんな建物でも構いません!

![Build area image](https://raw.githubusercontent.com/Mojang/EducationContent/master/computing/unit-2/build_area.png)

## ステップ1
自分でデザインした家を手動で建ててみましょう。黄色と黒のウールでマークされた指定の建設エリア内で行ってください。

戻る矢印を押すと、サンプルと建設エリアの場所をもう一度確認できます。

## ステップ2
**run**という要素の名前を、``||Player:on chat command||``ブロックの中で **clone_here** に変更します。次に ``||Blocks:clone from||`` コードブロックを ``||Player:on chat command||``. 

このコードブロックを使うと、Minecraftワールドの指定エリアを複製して別の場所に置くことができます。他のソフトでいうコピー&ペーストのようなものです。あるエリアをコピーして、ワールドの別の場所に貼り付けます。

複製すると、建物の向きはコピー元の建物と同じになります。つまり、コピーした建物が東を向いていれば、複製された建物も東を向きます。

#### ~ tutorialhint
``` blocks
player.onChat("clone_here.", function () {
    blocks.clone(
    pos(0, 0, 0),
    pos(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## ステップ3
最初の2組の座標は、``||Blocks:clone from||`` の座標を1つの角、``||Blocks:to||`` の座標を反対側の角として、その間にあるすべてを画像の箱のように囲む立方体を表します。

3組目の座標、``||Blocks:into||`` は、複製した構造物を貼り付けたい場所の座標を表します。 

実際にやってみましょう!モデルハウスの底の角を見つけてください。提供された画像では、これを黄色のウールでマークしています。 

次に、構造物を囲む見えない箱を作るように、反対側の上の角も決めます。画像でも同じように **Yellow Wool** でマークしています。 

## ステップ4
``||Positions:POSITIONS||`` ツールボックスドロワーを開き、最初の2組の座標を ``||Positions:world||`` の座標に置き換えます。**Yellow Wool** からわかるように、これらの座標はすべて絶対座標です。 

#### ~ tutorialhint
``` blocks
player.onChat("clone_here.", function () {
    blocks.clone(
    world(0, 0, 0),
    world(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## ステップ5
1組目の座標をコードブロックの ``||Blocks:clone from||`` セットに、2組目の座標を ``||Blocks:to||`` セットに変更します。下の画像はサンプルの座標であることに注意してください。 

最後の座標はプレイヤーからの相対座標です。そのためプレイヤー自身が、家を複製したい場所の目印になります。別の家を複製するたびに、プレイヤーを移動させる必要があります。 

#### ~ tutorialhint
``` blocks
player.onChat("clone_here.", function () {
    blocks.clone(
    world(67, 69, -544),
    world(73, 77, -551),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
})
```

## ステップ6
コードをテストしましょう。Minecraftでプレイヤーを空に移動させ、建物がどこに複製されるか注意しながらコードをテストします。 

## ステップ7
家が並ぶ通りを作りましょう。最終的な建物で最初の家を建てたい場所に立ち、次のコマンドを入力: **clone_here** 。すると家が現れるはずです。 

街に通りを作り終えたら、モデルハウスは撤去してかまいません。
