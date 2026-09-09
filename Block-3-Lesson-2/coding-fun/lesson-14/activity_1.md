### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 恐竜をやり過ごそう!

## ステップ1
恐竜を``||player:sneak past||``する必要があります。自分を``||mobs:invisible||``にすることで、それを実現できますか?

### ~ tutorialHint
Minecraftでこっそり進むには、ShiftとWを押してみましょう。

```ghost
player.onTravelled(SNEAK, function () {
    mobs.applyEffect(INVISIBILITY, mobs.target(NEAREST_PLAYER), 3, 1)
})
```
