### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# ポータルに電力を!

## ステップ1
**gold plates**の上に立っている間に雷を落とす必要があります。まず、``||gameplay: weather||``を雨に設定するため、``||loops: on start||``を使います。次に、正確なタイミングで雷を落とすため、``||logic: if||``、``||blocks: test for||``、``||mobs: spawn a lightning bolt||``を``||player: on walk||``の中に配置します。

### ~ tutorialHint
金色の板は、あなたの足元の**0, -1, 0**座標にあります。

```ghost
player.onTravelled(WALK, function () {
    if (blocks.testForBlock(GOLD_BLOCK, pos(0, -1, 0))) {
        mobs.spawn(LIGHTNING_BOLT, pos(0, 0, 0))
    }
})
gameplay.setWeather(RAIN)
```
