### @explicitHints 1

# レッスン1: 動物園の入り口をコードする

## ステップ1
**run**という要素を、``||Player:on chat command||``ブロックの中で次のように変更: **build_gates**.


``||Agent:agent set active slot||`` コードブロックをコーディングワークスペースにドラッグし、そのまま **1** にしておきます。次に ``||Agent:agent move [forward]||`` ブロックを追加し、ドロップダウンメニューで **up** に変更し、数値はそのまま **1**.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
})
```

## ステップ2
``||Loops:repeat [4] times||`` コードブロックを ``||Player:on chat command||`` にドラッグし、数値を次のように設定: **15** これは大きなゲートになります。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {

    }
})
```

## ステップ3
``||Agent:agent place [forward]||`` コードブロックをコーディングワークスペースにドラッグし、ドロップダウンメニューで次のように設定: **down**.   


``||Agent:agent move [forward]||`` コードブロックをメインのコードに追加し、ドロップダウンメニューで **right** に変更し、数値はそのまま **1**.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
    }
})
```

## ステップ4
もう一つ ``||Agent:agent place [forward]||`` コードブロックを ``||Agent:Agent||`` ドロワーから取得し、次のように設定: **down**.


``||Agent:agent move [forward]||`` コードブロックをコーディングワークスペースにドラッグし、そのまま **forward** と **1**.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```

## ステップ5
もう一つ ``||Agent:agent place [forward]||`` コードブロックを ``||Agent:Agent||`` ドロワーから取得し、次のように設定: **down**.

また ``||Agent:agent move [forward]||`` コードブロックを ``||Agent:Agent||`` ドロワーから取得し、**left** に変更し、数値はそのまま **1**.

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
    }
})
```

## ステップ6
もう一つ ``||Agent:agent place [forward]||`` コードブロックを ``||Agent:Agent||`` ドロワーから取得し、次のように設定: **down**。  
次に、``||Agent:Agent||`` を次のスタート位置まで移動させ、ゲートのこの部分のコードを完成させましょう。

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
    }
})
```

## ステップ7
``||Agent:Agent||`` ドロワーに戻り、``||Agent:agent move [forward]||`` コードブロックをもう2つコーディングワークスペースにドラッグして、``||Agent:agent place [down]||`` ブロックの下に接続します。ドロップダウンメニューで **forward** を **back** に、1つ目のブロックの **forward** を **up** に、2つ目のブロックのものへと変更します。  

#### ~ tutorialhint
``` blocks
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```
## ステップ8
エージェントを **Yellow wool** ブロックのどちらかの上に、ホイッスルを使って配置します。

## ステップ9
コードを実行しましょう。チャット機能で ``||Player:on chat command||`` と入力し、**T** エージェントがゲートの最初の柱を作るのを見てみましょう。

## ステップ10
2本目の柱についても同じことを行います。エージェントをもう一方の **Yellow wool** ブロックにホイッスルで配置してから、もう一度コードを実行します。これで木の柱が2本できているはずです。  

## ステップ11
看板の入り口をコードしましょう。次は上部に看板を追加します。   

新しい ``||Player:on chat command||`` ブロックを取得し、**jump** という要素の名前を次のように変更: **zoo_sign**.

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {

})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## ステップ12
``||Blocks:print [HELLO]||`` コードブロックを選び、新しいon chat commandのコードブロックにドラッグします。


**HELLO** というテキストを次のように変更: **ZOO**.

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    GRASS,
    pos(0, 0, 0),
    WEST
    )
})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## ステップ13
ドロップダウンメニューを使って、ブロックの材質を **Grass** から次のように変更: **Oak Wood**.


``||Positions:world [0] [0] [0]||`` のオーバルをドラッグし、``||Positions:[~0] [~0] [~0]||`` のオーバルを ``||Blocks:print [ZOO]||`` ブロックの中で置き換えます。

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(0, 0, 0),
    WEST
    )
})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## ステップ14
``||Positions:world||`` の位置にある座標を、テキストを開始したい位置の数値に変更します。この例では **-31, 83, -560** です。この数値を使うときは、マイナス記号を忘れずに付けてください。

実際のワールドで正しい位置に合わせるには、作成する文字数や配置場所、向きによって多少の試行錯誤が必要になるかもしれません。
#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(-31, 83, -560),
    WEST
    )
})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## ステップ15
``||Blocks:along||`` の値を、テキストを向けたい方向に合わせて変更します。この例では **North (negative Z)** ですが、あなたのワールドでは異なる場合があります。  

#### ~ tutorialhint
``` blocks
player.onChat("zoo_sign", function () {
    blocks.print(
    "ZOO",
    LOG_OAK,
    world(-31, 83, -560),
    NORTH
    )
})
player.onChat("build_gates", function () {
    agent.setSlot(1)
    agent.move(UP, 1)
    for (let index = 0; index < 15; index++) {
        agent.place(DOWN)
        agent.move(RIGHT, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.place(DOWN)
        agent.move(LEFT, 1)
        agent.place(DOWN)
        agent.move(BACK, 1)
        agent.move(UP, 1)
    }
})
```

## ステップ16
コードを実行しましょう。いよいよコードをテストします。チャットに **zoo_sign** コマンドを入力し、**T** 機能を使ってEnterキーを押します。動物園のゲートの上空に **ZOO** という文字が現れるはずです。
