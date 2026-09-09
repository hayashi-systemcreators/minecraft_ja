### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 建築

## ステップ1
``||mobs:Give||``を使って、少なくとも**34 emerald**ブロックを自分に与えましょう。新しい``||variable||``を作成し、**count**という名前にします。``||blocks:on block placed||``ブロックを取得し、**emerald**に設定します。``||change count||``ブロックを``||blocks: on block placed||``の中にドラッグし、``||player: say||``ブロックを追加します。``||count||``を``||player: say||``ブロックの中に追加します。こうすることで、ブロックを設置するたびに、ゲームが設置したブロックの数を数えるようになります。

### ~ tutorialhint 

鉄、金、エメラルド、ダイヤモンドのいずれかを選べます。

```blocks
let count = 0
blocks.onBlockPlaced(EMERALD_BLOCK, function () {
    count += 1
    player.say(count)
})

```

```ghost
blocks.onBlockBroken(STONE, function () {
    count += 1
    player.say(count)
})
let count = 0
mobs.give(
mobs.target(NEAREST_PLAYER),
STONE,
1
)
})
```
