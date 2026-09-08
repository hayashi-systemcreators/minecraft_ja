### @explicitHints 1

# レッスン1: 道路ネットワークをコードする

## ステップ1
**run**という要素を、``||Player:on chat command||``ブロックの中で **road_1** という名前に変更します。次に ``||Blocks:fill with||`` コードブロックを ``||Player:on chat command||`` ブロックの中にドラッグします。

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRASS,

    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## ステップ2
ドロップダウンメニューを使って、ブロックの種類を次のように変更: **Grass** → **Gray Concrete**.
### ~ tutorialhint

``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## ステップ3
``||Positions:POSITIONS||`` ツールボックスドロワーを開き、world ``||Positions:[0] [0] [0]||`` コードブロックをコーディングワークスペースにドラッグします。
world ``||Positions:[0] [0] [0]||`` ブロックをドラッグして、``||Positions:relative||`` の positions ブロックを ``||Blocks:fill||`` ブロックの中で置き換えます。

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## ステップ4
もう一つ、``||Positions:world [0] [0] [0]||`` の positions コードブロックを ``||Positions:POSITIONS||`` ドロワーからドラッグし、``||Positions:relative||`` の positions ブロックのうち2つ目を ``||Blocks:fill with||`` ブロックの中で置き換えます。

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## ステップ5
そろそろコードをテストする準備が整いましたが、正しく動作させるためにもう一つ大切な作業があります。中央の座標、つまり **Y** 座標を1つ小さい数値に変更します。この例では **68** になります。それではコードをテストしてみましょう。正しくコーディングできていれば、草の代わりに道路が現れるはずです。

### ~ tutorialhint
``` blocks
player.onChat("road_1", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -565),
    world(61, 68, -569),
    FillOperation.Replace
    )
})

```

## ステップ6
2本目の道路についても同じ手順を繰り返します。

### ~ tutorialhint
``` blocks
player.onChat("road_2", function () {
    blocks.fill(
    GRAY_CONCRETE,
    world(-21, 68, -532),
    world(61, 68, -536),
    FillOperation.Replace
    )
})
```

## ステップ7
(発展) 2本の道路ができたら、今作ったコードを使ってさらに道路を作ってみましょう。終わったら、ユニット2レッスン1のNPCのところへ行き、エージェントで道路の目印を作るためのカーペットをもらいましょう。
``` blocks
agent.place()
```
