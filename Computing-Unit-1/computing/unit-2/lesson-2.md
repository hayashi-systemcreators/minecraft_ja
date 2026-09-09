### @explicitHints 1

# レッスン2: 建物をコードする

## ステップ1
まずは壁を作ることから始めましょう。**run**という要素を、``||Player:on chat command||``ブロックの中で **build_a_structure** という名前に変更します。次に ``||Agent:agent set active slot||`` コードブロックをコーディングワークスペースにドラッグ&ドロップし、``||Player:on chat command||`` コードブロックに追加します。 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
})
```

## ステップ2
``||Agent:agent [place on move]||`` コードブロックを ``||Player:on chat command||`` のコードセットにドラッグします。ドロップダウンメニューを使って、**false** 要素を次のように変更: **true**. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
})
```

## ステップ3
それでは、エージェントに何をどうやって作るか指示を与えましょう。左側のメニューにある ``||Loops:LOOPS||`` ツールボックスドロワーを開きます。``||Loops:repeat [4] times||`` コードブロックをドラッグして、``||Player:on chat command||`` のセットの次のステップとして追加します。 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
    	
    }
})
```

## ステップ4
``||Agent:AGENT||`` ツールボックスドロワーに戻り、``||Agent:agent move [forward]||`` をドラッグします。今回は ``||Loops:repeat [4] times||`` のコードセットの中に配置します。 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 1)
    }
})
```

## ステップ5
``||Agent:agent move [forward]||`` コードブロックの数値を **5** に変更します。``||Agent:agent turn [left]||`` をドラッグし、今回は ``||Loops:repeat [4] times||`` のコードセットの中に配置します。方向は、何をどこに作るかによって自由に変更できます。この例では次のままにします: **left**. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
})
```

## ステップ6
コードをテストしてみましょう。壁が4つできて、エージェントは開始位置付近に戻ります。 

## ステップ7
``||Agent:AGENT||`` ツールボックスドロワーに戻り、``||Agent:agent move [forward]||`` をもう一つ追加し、**up** に変更します。ただし今回は ``||Agent:repeat [4] times||`` コードブロックの外側、その後ろに新しい別のアクションとして配置します。これによりエージェントが1ブロック上に移動し、その下のブロックを埋めます。

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
})
```

## ステップ8
``||Agent:agent [place on move]||`` をもう一つ追加し、これは **false** のままにしておきます。今回はエージェントが移動中にブロックを設置しないようにするためです。 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
    agent.setAssist(PLACE_ON_MOVE, false)
})
```

## ステップ9
``||Agent:agent move [forward]||`` をもう一つ追加し、**right** に変更します。これによりエージェントが開始位置に戻り、壁の2段目を作る準備が整います。 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        agent.move(FORWARD, 5)
        agent.turn(LEFT_TURN)
    }
    agent.move(UP, 1)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(RIGHT, 1)
})
```

## ステップ10
この工程を壁の4段分繰り返す必要があります。そのためにはもう一つループが必要です。
``||Loops:LOOPS||`` ドロワーに戻り、もう一つ ``||Loops:repeat [4] times||`` をコーディングワークスペースに持ってきます。今回は壁を作る手順を繰り返すためです。 

## ステップ11
``||Agent:AGENT||`` ツールボックスドロワーに戻り、``||Agent:agent [place on move]||`` をもう一つ追加し、**true** に設定します。コードをテストしてみましょう。 

## ステップ12
``||Agent:AGENT||`` ツールボックスドロワーに戻り、``||Agent:agent set active slot||`` をもう一つ追加し、**2** に設定します。別のループを使って、エージェントを5ブロック前進させてから左に移動させます。次に5ブロック後退させて、再び左に移動させます。これを3回繰り返して屋根を作ります。使う材料: **Stone Slabs**.

### ~ tutorialhint

``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
})
```

## ステップ13
いよいよ窓とドアを作りましょう。もう一つ ``||Agent:agent [place on move]||`` を追加し、**false** のままにします。次に、もう一つ ``||Agent:agent move [forward]||`` を追加し、**down** を **3** に設定します。これによりエージェントは3マス下に移動し、屋根のタイルが置かれないよう窓を設置する高さまで下がります。 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
})
```

## ステップ14
``||Agent:agent move [forward]||`` をもう一つ追加し、設定: ``||Agent:forward||``、**1**.

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
})
```

## ステップ15
``||Agent:set active slot||`` をもう一つ追加し、**3** に設定します。これによりエージェントのインベントリの3番目のスロットが選択され、次に使う建材が **Glass Panes** になります。 

さらに ``||Agent:agent destroy [forward]||`` ブロックを追加します。最後のブロックの下に置き、値を **right** に変更します。これによりエージェントが右隣のブロックを壊し、壁に窓用の穴を開けます。 

## ステップ16
新しいコードブロック ``||Agent:agent place [forward]||`` を選び、ドロップダウンメニューで **right** に変更します。これによりエージェントが **Glass Pane** を、壁を壊した後にできた隙間に設置するようになります。 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
})
```

## ステップ17
``||Agent:agent move [forward]||`` コードブロックをもう一つ追加します。設定はそのまま **forward** にし、番号を次のように変更: **2**.

## ステップ18
ドアを設置するので、壁の2ブロック分の高さを壊す必要があります。まずは ``||Agent:agent destroy [forward]||`` コードブロックを置き、設定: **right**. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
})
```

## ステップ19

``||Agent:agent move [forward]||`` コードブロックをもう一つ追加し、**down** に変更します。これによりエージェントがドアを設置したい位置にちょうど移動します。そのため、正しいインベントリスロットを選んでからドアを設置する必要があります。 

### ~ tutorialhint
``` blocks 
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
})
```

## ステップ20
``||Agent:agent destroy [forward]||`` コードブロックをもう一つ追加し、設定: **right**.

``||Agent:AGENT||`` ドロワーに戻り、もう一つ ``||Agent:select active slot||`` コードブロックを追加し、設定: **4** に。これによりエージェントの4番目のインベントリスロットが選択されます。使うのは: **Acacia Door**. 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
    agent.destroy(RIGHT)
    agent.setSlot(4)
})
```

## ステップ21
``||Agent:AGENT||`` ツールボックスドロワーに戻り、もう一つ ``||Agent:agent place [forward]||`` コードブロックを追加し、**right** に変更します。これによりドアが設置され、建物が完成します。コードをテストしてみましょう! 

### ~ tutorialhint
``` blocks
player.onChat("build_a_structure.", function () {
    agent.setSlot(1)
    agent.setAssist(PLACE_ON_MOVE, true)
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.move(FORWARD, 5)
            agent.turn(LEFT_TURN)
        }
        agent.move(UP, 1)
        agent.setAssist(PLACE_ON_MOVE, false)
        agent.move(RIGHT, 1)
        agent.setAssist(PLACE_ON_MOVE, true)
    }
    agent.setSlot(2)
    for (let index = 0; index < 3; index++) {
        agent.move(FORWARD, 5)
        agent.move(LEFT, 1)
        agent.move(BACK, 5)
        agent.move(LEFT, 1)
    }
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.move(DOWN, 3)
    agent.move(FORWARD, 1)
    agent.setSlot(3)
    agent.destroy(RIGHT)
    agent.place(RIGHT)
    agent.move(FORWARD, 2)
    agent.destroy(RIGHT)
    agent.move(DOWN, 1)
    agent.destroy(RIGHT)
    agent.setSlot(4)
    agent.place(RIGHT)
})
```