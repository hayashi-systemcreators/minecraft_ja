### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 溶岩を泳ぐ

## ステップ1
あなたの課題は、溶岩の湖を``||player:swim||``で渡ることです。``||mobs:applying fire resistance||``を次に適用してみましょう: **nearest player**.

```ghost
player.onTravelled(SWIM_LAVA, function () {
    mobs.applyEffect(FIRE_RESISTANCE, mobs.target(NEAREST_PLAYER), 10, 1)
    mobs.clearEffect(mobs.target(NEAREST_PLAYER))
})
```
