### @explicitHints 1

# レッスン2: 水の設備をコードする

## ステップ1
**run**という要素を、``||Player:on chat command||``ブロックの中で次のように変更: **park_fountain**.

噴水の枠を掘りましょう。次の工程は噴水の枠(境界)を作ることです。まず地面を掘り、その後ブロックを次の材料に置き換えます: **Cobblestone**.

## ステップ2
``||Loops:repeat [4] times||`` コードブロックを ``||Player:on chat command||`` のセットにドラッグし、数値はそのまま **4**.  

これによりエージェントは次の一連のアクションを4回繰り返します。複数のループを使うので、この最初のループを **outer** ループと呼びます。  

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {

    }
})
```

## ステップ3
もう一つ ``||Loops:repeat [4] times||`` コードブロックを ``||Player:on chat command||`` のセットにドラッグします。最初のループの内側に配置してください。

``||Agent:agent destroy [forward]||`` コードブロックをコーディングワークスペースに追加し、ドロップダウンメニューを使って次のように設定: **down**.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
            agent.destroy(DOWN)
        }
    }
})
```

## ステップ4
``||Agent:agent move [forward]||`` コードブロックをコーディングワークスペースにドラッグし、前のステップで追加したブロックの後ろの ``||Loops:repeat [4] times||`` に配置します。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
          agent.destroy(DOWN)
          agent.move(FORWARD, 1)
        }
    }
})
```

## ステップ5
``||Agent:agent turn [left]||`` コードブロックを、1つ目(外側)の **outer** ``||Loops:repeat [4] times||`` ループの内側に追加します。ただし2つ目(内側)は対象外: ``||Loops:repeat [4] times||``.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 4; index++) {
          agent.destroy(DOWN)
          agent.move(FORWARD, 1)
        }
        agent.turn(LEFT_TURN)
    }
})
```

## ステップ6
コードをテストしてみましょう。エージェントが5×5の枠を掘るのが確認できます。

コブルストーンで埋める。それでは、この新しくできた穴をコブルストーンで埋めて、噴水の枠を作りましょう。

## ステップ7
``||Agent:agent set active slot||`` コードブロックを、``||Loops:repeat [4] times||`` の内側、``||Player:on chat command||`` ブロックの下に配置します。エージェントはこれを繰り返す必要はなく、これは新しいアクションの一部です。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
      for (let index = 0; index < 4; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.turn(LEFT_TURN)
    }
    agent.setSlot(1)
})
```

## ステップ8
手順を繰り返しますが、新しいセットは ``||Agent:agent set active slot||`` の後ろに配置し、``||Agent:agent destroy [down]||`` だけを次のように置き換えます: ``||Agent:agent place [down]||``.  

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
})
```

## ステップ9
もう一度コードをテストしましょう。今回はエージェントが地面を掘った後、**Cobblestone** に置き換えることに注目してください。これが噴水の枠になります。

噴水の内側を掘る。次に、水が公園にあふれないように、噴水の内側の地面を取り除くコードをエージェントに書きます。

## ステップ10
``||Agent:agent move [forward]||`` コードブロックをドラッグし、**left** に変更して、現在のコードの最後に配置します。

もう一つ ``||Agent:agent move [forward]||`` コードブロックを取得し、**forward** のままにして、現在のコードの最後に配置します。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
    for (let index = 0; index < 4; index++) {
      for (let index = 0; index < 4; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.turn(LEFT_TURN)
    }
    agent.setSlot(1)
    for (let index = 0; index < 4; index++) {
      for (let index = 0; index < 4; index++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.turn(LEFT_TURN)
    }
    agent.move(LEFT, 1)
    agent.move(FORWARD, 1)
})
```

## ステップ11
``||Loops:repeat [4] times||`` コードブロックを ``||Player:on chat command||`` コードの最後にドラッグし、数値を次のように設定: **3**.

噴水の枠の中央には3×3ブロックの草があり、エージェントがこれを取り除く必要があります。そのため3つのアクションを与えて、それを3回繰り返します。ここでも最初のループを外側のループ、2つ目を内側のループと呼びます。  

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {

  }
})
```

## ステップ12
もう一つ ``||Loops:repeat [4] times||`` コードブロックを取得し、最初のループの内側に配置して、次のように設定: **3**.  

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {

      }
  }
})
```

## ステップ13
次に、エージェントに ``||Agent:agent destroy||`` をさせ、**down** をドロップダウンメニューで設定します。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
      }
  }
})
```

## ステップ14
エージェントに ``||Agent:agent move [forward]||`` をさせます。数値はそのまま **1**.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 5; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
  }
})
```

## ステップ15
エージェントを元の位置に戻しましょう。エージェントに ``||Agent:agent move [forward]||`` をさせ、**back** に設定し、数値を次のように変更: **3**.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
  }
})
```

## ステップ16
エージェントに ``||Agent:agent move [forward]||`` をさせ、**left** に設定します。
これによりエージェントは、次に取り除く3ブロックの列の先頭に移動し、外側のループによってこれが3回繰り返されます。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
})
```

## ステップ17
コードをテストして、エージェントが噴水の枠の内側を掘るのを見てみましょう。

## ステップ18
水の設備をコードしましょう。``||Agent:agent move [forward]||`` コードブロックをメインのコードにドラッグします。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
})
```

## ステップ19
``||Agent:agent move [forward]||`` コードブロックを取得し、**forward** を **right** にドロップダウンメニューで変更し、数値を **2** に変更します。これによりエージェントが噴水の中央に移動します。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
})
```

## ステップ20
``||Loops:repeat [4] times||`` コードブロックを取得し、数値を次のように変更: **5**.

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {

  }
})
```

## ステップ21
``||Agent:AGENT||`` ドロワーに戻り、``||Agent:agent place [down]||`` コードブロックを取得して、``||Loops:repeat [5] times||`` ブロックの内側にコードを追加します。
これによりエージェントは、5つのうち最初の **Cobblestone** ブロックを噴水の底に設置します。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
  }
})
```

## ステップ22
``||Agent:agent move [forward]||`` コードブロックを取得してコードに追加し、**up** にドロップダウンメニューで変更します。
これによりエージェントは噴水の一番上に移動し、水を追加する準備が整います。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 5; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
    agent.move(UP, 1)
  }
})
```

## ステップ23
``||Agent:agent set active slot||`` コードブロックを取得してコードに追加し、**2** に変更します。これはエージェントのインベントリのうち、**Bucket of Water** が入っているスロットです。次に ``||agent:agent place||`` **down** ブロックを追加します。

#### ~ tutorialhint
``` blocks
player.onChat("park_fountain", function () {
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.destroy(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.setSlot(1)
  for (let index = 0; index < 4; index++) {
    for (let index = 0; index < 4; index++) {
      agent.place(DOWN)
      agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
  }
  agent.move(LEFT, 1)
  agent.move(FORWARD, 1)
  for (let index = 0; index < 3; index++) {
      for (let index = 0; index < 3; index++) {
        agent.destroy(DOWN)
        agent.move(FORWARD, 1)
      }
      agent.move(BACK, 3)
      agent.move(LEFT, 1)
  }
  agent.move(FORWARD, 1)
  agent.move(RIGHT, 2)
  for (let index = 0; index < 5; index++) {
    agent.place(DOWN)
    agent.move(UP, 1)
  }
  agent.setSlot(2)
  agent.place(DOWN)
})
```

## ステップ24
噴水を公園のどこかに設置する前に、コードを確認してテストしましょう。
