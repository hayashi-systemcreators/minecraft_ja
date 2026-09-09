### @explicitHints 1

# レッスン1: 公園のフェンスをコードする

## ステップ1
**run**という要素を、``||Player:on chat command||``ブロックの中で次のように変更: **park_fence**. 

``||Agent:agent set active slot||`` コードブロックをコーディングワークスペースにドラッグ&ドロップし、``||Player:on chat command||`` コードブロックに追加します。

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
})
```
## ステップ2
``||Loops:repeat [4] times||`` を ``||Player:on chat command||`` のセットにドラッグし、次のように変更: **25**.

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
    	
    }
})
```

## ステップ3
``||Agent:agent move [forward]||`` コードブロックをコーディングワークスペースにドラッグし、``||Player:on chat command||`` コードブロックの中、``||Loops:repeat [25] times||`` ループの内側に追加し、次のように変更: **1**. 

``||Agent:agent place [forward]||`` コードブロックをコーディングワークスペースにドラッグし、``||Player:on chat command||`` コードブロックの中、``||Loops:repeats [25] times||`` ループの内側、``||Agent.agent move[forward]||`` コードブロックの下に追加し、**forward** を次のように変更: **back**.

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
        agent.move(FORWARD, 1)
        agent.place(BACK)
    }
})
```

## ステップ4
``||Agent:agent turn [left]||`` コードブロックを ``||PLayer:on chat command||`` コードブロックの後ろに追加します。エージェントが回転させたい方向に設定してください。この例では次のとおりです: **left**. 

### ~ tutorialhint
``` blocks
player.onChat("park_fence", function () {
    agent.setSlot(1)
    for (let index = 0; index < 25; index++) {
        agent.move(FORWARD, 1)
        agent.place(BACK)
    }
    agent.turn(LEFT_TURN)
})
```

## ステップ5
コードをテストしましょう。エージェントを開始ブロックの上に置き、**T** キーを押してチャットボックスを開き、次のように入力: **park_fence**. 

このコードは一度に1辺しか作れません。実行する前に、各辺を作り終えるのに十分なブロックがエージェントにあるか確認しましょう!足りない場合はユニット3レッスン1のNPCにブロックをもらいに行きましょう。
