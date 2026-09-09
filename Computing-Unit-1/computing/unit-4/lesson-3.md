### @explicitHints 1

# レッスン3: 動物の飼育エリアをコードする 

## ステップ1
まずBUILDERにスタート地点を指定します。MakeCodeで、**run**という要素を、``||Player:on chat command||``ブロックの中で次のように変更: **ocelot_wall**. 

``||Advanced:ADVANCED||`` ドロワーを画面左から開き、次に ``||Builder:BUILDER||`` ドロワーを画面左から開きます。``||Builder:BUILDER||`` ドロワーを使うと、Minecraftのポジション機能にアクセスして操作できます。``||Builder:BUILDER||`` は目に見えない ``||Agent:Agent||``. 

まずは最初の座標を設定しましょう。``||Builder:builder teleport to [~0] [~0] [~0]||`` ブロックを ``||Player:on chat command||`` ブロックにドラッグします。 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(pos(0, 0, 0))
})
```

## ステップ2
``||Positions:world [0] [0] [0]||`` のオーバルをコーディングワークスペースにドラッグし、すでにある **relative** の座標オーバルと置き換えます。 

次に、``||Positions:world [0] [0] [0]||`` の座標を、壁を作り始めたい位置に設定します。今回は開始位置を **Gold Block** で、座標 **-40, 69, -575** の位置にマークしました。開始位置(最初の目印)の座標をワークブックに記録しておきましょう。 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
})
```

## ステップ3
BUILDERに方向を伝えましょう。次に、どの方向に作るかを指定する必要があります。Minecraftのワールドには南北・東西、そして上下のグリッドがあることを思い出してください。一番簡単な方法はコンパスを使うことです。 

インベントリにコンパスがあります。

動き回ると、**compass** も一緒に動きます。これを使って北(赤い針が指す方向)、東、南、西を確認できます。**compass** が示している方向は西です。今回はこの方向に ``||Builder:BUILDER||`` を動かしたいと思います。 

## ステップ4
``||Builder:BUILDER||`` ドロワーに戻り、``||Builder:builder face [West (negative X)||`` コードブロックを探します。これをメインのコードに追加し、ドロップダウンメニューで作りたい方向を正しく設定します。 

注意: プレイヤーが向いている方向が東・北・南の場合は、このコードブロックをそれに合わせて変更してください。おさらいすると、**compass** を使って、動かしたい ``||Builder:BUILDER||`` の方向を確認し、それをこのコードブロックに入力します。 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
})
```

## ステップ5
``||Builder:BUILDER||`` メニューに戻り、``||Builder:builder move [forward]||`` ブロックをメインのコードにドラッグします。 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 1)
})
```

## ステップ6
``||Builder:builder move [forward]||`` の数値を、作りたいブロックの数に変更します。この例では **21** ですが、あなたの飼育エリアでは異なる数値になるかもしれません。 

次に ``||Builder:builder turn [left]||`` コードブロックをメインのコードにドラッグします。 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(LEFT_TURN)
})
```

## ステップ7
``||Builder:BUILDER||`` を次に向かせたい方向に変更します。この例では右にします。 

もう一つ ``||Builder:builder move [forward]||`` コードブロックを追加し、数値をこの新しい方向に作りたいブロックの総数に変更します。この例では次のように設定します: **9**. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
})
```

## ステップ8
BUILDERに使う材料を伝えましょう。最後に ``||Builder:BUILDER||`` に建材を与えます。``||Builder:BUILDER||`` ドロワーに戻り、``||Builder:builder trace a path from mark with||`` コードブロックをメインのコードにドラッグします。 

これによりBUILDERは移動した経路に沿って、指定した材料の跡を残すようになります。 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(GRASS)
})
```

## ステップ9
ドロップダウンメニューを使って、材料の要素を外壁に使いたい材料に変更します。この例では次を使用します: **Stone Bricks**. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(STONE_BRICKS)
})
```

## ステップ10
壁を作るためにコードを実行しましょう。コードをテストします。 ``||Builder:BUILDER||`` は、位置 **-40, 69, -575** からスタートし、西に **21** ブロック移動して **left** に曲がり、**9** ブロック移動しながら **Stone Bricks** を設置していくはずです。これによりオセロットの飼育エリアの周りに小さな外壁ができます。この作業は ``||Agent:Agent||`` や ``||Blocks:BLOCKS||`` を使った以前のレッスンに比べて、とても速く終わることに気づくでしょう。少し事前に計画しておけば、数秒で巨大な構造物を作ることができます。 

## ステップ11
フェンスなどのディテールを追加しましょう。この壁だけではオセロットを閉じ込められないので、上にフェンスを追加して逃げられないようにします。 

## ステップ12
上記のコーディングを繰り返すか、既存のコードを調整してこれを行います。位置を1ブロック高くし、材料を **Oak Fence** に変更するだけです。以下は例です: 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot_wall", function () {
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
})
```

## ステップ13
それでは、オセロットの飼育エリアにいくつか要素を追加しましょう。 

飼育エリアにオセロットをコードする。あとはオセロットを新しい飼育エリアに登場させるだけです。 

## ステップ14
新しい ``||Player:on chat command||`` ブロックをコーディングウィンドウに追加し、次の名前をつけます: **ocelot**. 

## ステップ15
``||Mobs:spawn [animal] at||`` コードブロックを ``||Mobs:MOBS||`` メニューから、新しい ``||Player:on chat command||`` コードにドラッグします。 

ドロップダウンメニューを使って、**animal** 要素を次のように変更: **ocelot**. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot", function () {
    mobs.spawn(OCELOT, pos(0, 0, 0))
})
```

## ステップ16
``||Positions:POSITIONS||`` ドロワーに行き、``||Positions:world [0] [0] [0]||`` を取得して、**relative** の座標オーバルと置き換えます。次に、数値を飼育エリア内の位置に変更します。この例では次のように設定します: **-50, 69, -580**. 

#### ~ tutorialhint
``` blocks
player.onChat("ocelot", function () {
    mobs.spawn(OCELOT, world(-50, 69, -580))
})
```

## ステップ17
オセロットをスポーンさせましょう。コードを実行します。完了すると、**ocelot** が現れるはずです! 

## ステップ18
他の飼育エリアや動物を追加してみましょう。たとえば **wolf** や **polar bear** などを追加できます。それぞれの生息環境を考えながら、飼育エリアを装飾してみましょう。
