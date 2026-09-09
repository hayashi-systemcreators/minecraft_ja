### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 初めての素材検出

## ステップ1
エージェントは**destroy**し、その後**collect**する必要があります。対象は**gold**ブロックです。

```template
player.onChat("material", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(LEFT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == GOLD_BLOCK) {
            
        }
    }
})
```

```ghost
player.onChat("1", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(LEFT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == GOLD_BLOCK) {
            agent.destroy(FORWARD)
            agent.collectAll()
        }
    }
})
```
