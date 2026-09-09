# レッスン1: 風力発電所をコードする

## ステップ1
風力タービンが集まって風力発電所になります。***wind turbine*** は風車のようなもので、風が当たるとブレードが回転します。現実の世界では、ブレードが回転することでエネルギーが電力に変換されます。風力発電所を作り始める前に、良い設置場所を考えてみましょう。この例では、街の近くの丘を使います。これまでに学んだ方法のいずれかを使ってタービンを1つコードし、それを複製して発電所を作りましょう。  
```template
player.onChat("run", function(){
})
player.teleport(world(19, 79, -413))
```

## ステップ2
腕試しです。最終ユニットに到達したので、主な2つのコーディング方法、``||Agent:AGENT||`` と ``||Builder:BUILDER||`` についてはもう慣れているはずです。どちらかの方法を使って、タービンをどう作るか決めてみましょう。丘の上にワールド内のサンプルがあります。 

## ステップ3
``||Blocks:clone||`` コマンドを ``||Blocks:BLOCKS||`` ツールボックスドロワーから使って、これらをさらに複製してもかまいません。   

```ghost
player.onChat("run", function () {
    blocks.clone(
    pos(0, 0, 0),
    pos(0, 0, 0),
    pos(0, 0, 0),
    CloneMask.Replace,
    CloneMode.Normal
    )
    agent.destroy(FORWARD)
    agent.place(FORWARD)
    agent.setAssist(PLACE_ON_MOVE, false)
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.teleportToPlayer()
    agent.setItem(GRASS, 1, 1)
    for (let index = 0; index < 4; index++) {
        blocks.place(GRASS, world(0, 0, 0))
    }
    while (true) {
    	
    }
    builder.teleportTo(world(-40, 69, -575))
    builder.face(WEST)
    builder.move(FORWARD, 21)
    builder.turn(RIGHT_TURN)
    builder.move(FORWARD, 9)
    builder.tracePath(OAK_FENCE)
    builder.place(GRASS)
    builder.mark()
    builder.fill(GRASS)
})
```