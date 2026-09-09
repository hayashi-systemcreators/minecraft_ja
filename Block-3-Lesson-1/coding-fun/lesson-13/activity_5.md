### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 雨を降らせよう!

## ステップ1
Minecraftで踊りながら雨を降らせましょう!それを実現するには、いくつかのイベントハンドラーを使う必要があります。1. 変数を作成します。例えば: **walk**、**jump**、または**break**。2. イベントハンドラーを選択します。例えば``||player: on player fall||``、``||player: on player walk||``。3. 対応する各イベントブロックの中で、新しい``||variables||``を``||logic: true||``に設定します。4. ``||loop: forever||``ブロックを使い、その中に``||logic: if statement||``をドラッグします。すべての条件を``||logic:true||``に設定し、``||gameplay: weather||``ブロックを**rain**に設定して追加します。


### ~ tutorialHint
```blocks
let walk = false
player.onTravelled(WALK, function () {
    walk = true
})
loops.forever(function () {
    if (walk == true && "" == "") {
    	
    }
})

```

```ghost
let climb = false
let walk = false
let _break = false
player.onTravelled(CLIMB, function () {
    climb = true
})
player.onTravelled(WALK, function () {
    walk = true
})
blocks.onBlockBroken(STONE, function () {
    _break = true
})
loops.forever(function () {
    if (walk == true && climb == (true && _break == true)) {
        gameplay.setWeather(RAIN)
    }
})
```
