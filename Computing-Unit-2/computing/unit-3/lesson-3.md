### @explicitHints 1

# レッスン3: 花を植えよう 

## ステップ1
**run**という要素を、``||Player:on chat command||``ブロックの中で次のように変更: **plant_flowers**. 

``||Loops:repeat [4] times||`` コードブロックを ``||Player:on chat command||`` にドラッグし、数値を公園の一辺にあるブロックの数に設定します。この例では次のように設定します: **20**. 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
    	
    }
})
```

## ステップ2
次に ``||Agent:agent set active slot||`` コードブロックのドラッグ先: ``||loops: repeat loop||``.    

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(1)
    }
})
```

## ステップ3
左メニューの新しいツールボックスドロワー、``||Math:MATH||`` ドロワーを開きます。 

このドロワーにあるブロックを使うと、コードの中で数学の計算ができます。

``||Math:pick random [0] to [10]||`` コードブロックを ``||Player:on chat command||`` にドラッグ&ドロップし、数値要素の置き換え先: ``||Agent:agent set active slot||``. 

これによりエージェントは特定のスロットを選ぶのではなく、インベントリの中からランダムにスロットを選ぶようになります。 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(0, 10))
    }
})
```

## ステップ4
1つ目の数値を **1** に、2つ目を **5** に設定します。これはエージェントのインベントリにある5つのスロットに対応しています。 
#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
    }
})
```

## ステップ5
エージェントがランダムに動き回るようにコードしましょう。``||Agent:Agent||`` ドロワーを開き、``||Agent:agent move [forward]||`` コードブロックをコーディングワークスペースにドラッグします。   

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, 1)
    }
})
```

## ステップ6
もう一つ ``||Math:pick random [0] to [10]||`` を追加し、``||Agent:agent move [forward]||`` の数値部分の置き換えとします。``||Math:pick random [0] to [10]||`` の2つ目の数値を次のように変更: **20**. 

このコードを追加すると、エージェントは現在の位置から最大20ブロック先までのランダムな位置に前進するようになります。 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
    }
})
```

## ステップ7
``||Agent:agent place [forward]||`` コードブロックを2つコーディングワークスペースにドラッグし、2つ目を **back** にドロップダウンメニューで変更します。 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
    }
})

```

## ステップ8
もう一つ ``||Agent:agent set active slot||`` コードブロックをコーディングワークスペースにドラッグします。もう一度 ``||Math:MATH||`` ドロワーを開き、もう一つ ``||Math:pick random [0] to [10]||`` を追加します。それを ``||Agent:agent set active slot||`` コードブロックに追加し、数値を1と5に変更します。 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
    }
})
```

## ステップ9
もう一度 ``||Agent:Agent||`` ドロワーを開き、``||Agent:agent move [forward]||`` コードブロックをコーディングワークスペースに選び、**back** にドロップダウンメニューで変更します。 

もう一つ ``||Math:pick another pick random [0] to [10]||`` を選び、``||Agent:agent move [back]||`` コードブロックに追加して、数値を **0** と次のように設定: **20**. 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(BACK, Math.randomRange(0, 20))
    }
})
```

## ステップ10
``||Agent:Agent||`` ドロワーを開き、``||Agent:agent place [forward]||`` コードブロックを2つコーディングワークスペースにドラッグし、2つ目を次のように変更: **back**. 

最後に、``||Agent:agent move [left]||`` コードブロックをコーディングワークスペースにドラッグして、このコードを完成させます。 

#### ~ tutorialhint
``` blocks
player.onChat(" plant_flowers", function () {
    for (let index = 0; index < 20; index++) {
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(FORWARD, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.setSlot(Math.randomRange(1, 5))
        agent.move(BACK, Math.randomRange(0, 20))
        agent.place(FORWARD)
        agent.place(BACK)
        agent.move(LEFT, 1)
    }
})
```

## ステップ11
エージェントを配置してコードを実行しましょう。エージェントを公園の一角に置き、背中がフェンスに接するように、そして公園の本体が左側にくるように配置してください。

コードをテストしましょう。エージェントはランダムな位置まで前進し、ランダムに選んだ花を2本植え、後退して同じことを行い、左に移動してまた最初から繰り返すはずです。これによりランダムな花畑ができあがります。
