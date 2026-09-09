### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 竹の境界

## ステップ1
用意されたスタートコードがあります。まずはそれを実行してみましょう。最終目標は、パンダの区画の**4**辺すべてに竹を植えることです。

```template
player.onChat("bamboo", function () {
    agent.setItem(BAMBOO, 64, 1)
    for (let index = 0; index < 16; index++) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
})
```
