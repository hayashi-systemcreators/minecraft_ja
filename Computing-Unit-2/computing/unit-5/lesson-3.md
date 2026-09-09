### @explicitHints 1
# レッスン3: 照明システムをコードする  

## ステップ1
風の合図をコードしましょう。まず最初に行うのは、タービンのブレードが常に回っているわけではないという錯覚を作ることです。現実世界でも、いつも十分な風があるとは限りませんよね。   

スターターコードを使い、``||loops:repeat||`` 要素の値を **4** から次のように変更: **10**. 

```template
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ2
発電のコードを作りましょう。``||Blocks:place [block] at||`` コードブロックをドラッグし、コードの最初の部分、``||Loops:repeat [10] times||`` ブロックの上に差し込みます。

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(GRASS, pos(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ3
ドロップダウンメニューを使って、**Grass Block** 要素を **Block of Redstone** に変更します。覚えておいてください、**Block of Redstone** は以前インベントリで確認した入力用ブロックです。  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, pos(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ4
**relative** の座標オーバルを、``||Positions:world [0] [0] [0]||`` ツールボックスドロワーにある ``||Positions:POSITIONS||`` の座標オーバルに置き換えます。  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(0, 0, 0))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ5
ゲームに戻り、**Redstone** 用に掘った溝の最初のブロックの上に立ちます。このブロックの座標をワークブックに記録してください。この例では **8 81 -412** ですが、あなたのワールドでは異なる座標になります。  

## ステップ6
MakeCodeで、この新しい座標を ``||Blocks:place [Block of Redstone]||`` のセットに入力します。  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ7
完成した ``||Blocks:place [Block of Redstone]||`` コードブロックを右クリックし、次を選択: **Duplicate**.  

この複製をメインのコードの一番下にドラッグし、3つ目の ``||Blocks:clone from||`` コードブロックの後ろ、ただし外側となるのは ``||Loops:LOOP||``.  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
})
```

## ステップ8
ドロップダウンメニューを使って、**Block of Redstone** 要素を **air** に変更します。ここまでの完成したコード。ここまでのコードは、自分の座標を使ってこのようになっているはずです

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
})
```

## ステップ9
コードをテストしましょう。うまくいけば、**Redstone Lamp** が、**wind_turbine** コマンドを実行するたびに点灯します。  

## ステップ10
``||Loops:forever||`` コードブロックを取得します。  

このコードブロックはループを作り、それを永遠に実行し続けます。天候の状態や、今回のように風など、グローバルな定数を扱うのに便利です。 

## ステップ11
これをコーディングワークスペースにドラッグし、``||Blocks:place [Block of Redstone]||`` コードブロックの上でマウスの左ボタンを押したままにします。左ボタンを押したままマウスを動かすと、このコードブロックとその下に接続されたすべてのブロックがドラッグされ、新しい ``||Loops:forever||`` ブロックの中に接続されます。  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
})
loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 10; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    )
})
```   

## ステップ12
``||Loops:repeat [10] times||`` の数値を次のように変更: **20**. 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    
})
loops.forever(function () {
    blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
    for (let index = 0; index < 20; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    )
})
```  

## ステップ13
風の変化を再現しましょう。最後に、無風の期間を表す要素を追加する必要があります。ここまでは、タービンが休みなく回転し、電力もすぐにオンオフを繰り返しています。コードの適切な場所に一時停止を入れることで、その効果が得られます。 

## ステップ14
``||Loops:LOOPS||`` メニューに戻り、``||Loops:pause (ms)||`` コードブロックを選びます。これをコードにドラッグし、最後の ``||Blocks:place [Air]||`` ブロックの直後に配置します。次に数値を次のように変更: **5000**.  

目安として、1000msはゲーム内時間の1秒にあたります。そのため5000msに設定すると、アニメーションに5秒の一時停止が入ります。これにより5秒間、風力が失われた状態を再現します。 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
   
})
loops.forever(function () {
    for (let index = 0; index < 20; index++) {
        blocks.place(REDSTONE_BLOCK, world(8, 81, -412))
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
    blocks.place(AIR, world(8, 81, -412))
    loops.pause(5000)
})
```
## ステップ15
コードを実行しましょう。コードをテストします。ブレードは20回転した後、5秒間停止し、これを無限に繰り返すはずです。**Redstone Lamp** は、ブレードが回転しているときだけ点灯するはずです。うまくいかない場合は、コードを見直して必要な調整を行ってください。その後、他のタービンについても同じ手順を繰り返しましょう。
