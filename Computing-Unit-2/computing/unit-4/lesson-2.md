### @explicitHints 1

# レッスン2: 動物園の通路をコードする 

## ステップ1
**run**という要素を、``||Player:on chat command||``ブロックの中で次のように変更: **zoo_path_1**. 

``||Blocks:fill with||`` コードブロックを選び、``||Player:on chat command||`` ブロックの中にドラッグします。 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRASS,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## ステップ2
ドロップダウンメニューを使って、材質を **Grass** から次のように変更: **Gravel**. 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    pos(0, 0, 0),
    pos(0, 0, 0),
    FillOperation.Replace
    )
})
```

## ステップ3
``||Positions:POSITIONS||`` を左メニューから開きます。 

このドロワーには、Minecraftのワールドを ***positions*** や ***coordinates*** といった仕組みで操作できるコードブロックがあります。Minecraftワールドのすべてのブロックは、X、Y、Zの各軸に沿った位置を持っています。 

``||Positions:world [0] [0] [0]||`` のオーバルを2つコーディングワークスペースにドラッグして、``||Positions:[~0] [~0] [~0]||`` のオーバルを ``||Blocks:from||`` と ``||Blocks:to||`` の要素の中で置き換えます。 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(0, 0, 0),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## ステップ4
**Step 3** からの1組目の座標を ``||Blocks:from||`` の ``||Positions:world [0] [0] [0]||`` セットに追加します。 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 69, -575),
    world(0, 0, 0),
    FillOperation.Replace
    )
})
```

## ステップ5
``||Blocks:to||`` の ``||Positions:world [0] [0] [0]||`` セットについても同様に行い、座標は次を使用: **Step 4**. 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 69, -575),
    world(-60, 69, -575),
    FillOperation.Replace
    )
})
```

## ステップ6
中心の座標、つまり **Y** 座標を1つ小さい数値に変更します。この例では次の値です: **68**.  

ちなみに、中央の座標の数値はワールドの一番下 **0** から一番上 **256** までの高さを表しています。この数値を1つ下げる必要があるのは、足元にある **Grass** を **Grey Gravel** に置き換えたいためで、元の座標として選んだブロックはプレイヤーの脚の位置にあたります。そのため、このままコードを実行すると道路が地面より1ブロック高い位置にできてしまいます。そこで代わりに草を置き換えるようにします。 

#### ~ tutorialhint
``` blocks
player.onChat("zoo_path_1", function () {
    blocks.fill(
    GRAVEL,
    world(-40, 68, -575),
    world(-60, 68, -575),
    FillOperation.Replace
    )
})
```
## ステップ7
それではコードをテストしてみましょう。正しくコーディングできていれば、草の代わりに道路が現れるはずです。   

## ステップ8
2本目、3本目、4本目の通路についても同じ手順を繰り返します。使うのは **Green Wool, Orange Wool** と **Red Wool** のマーカーです。以下の例が自分の動物園の計画に合わない場合は、自由に通路のネットワークを設計してかまいません。
