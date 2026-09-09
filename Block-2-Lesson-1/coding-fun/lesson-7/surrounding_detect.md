### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 周囲の状況 

## ステップ1
エージェントが**inspecting the block down**を行い、それが**stone**である間は、**move forward**してください。前方にブロックを検知**not**しなければ**move forward**し、そうでなければ次を行います: **turn left**. 

```template
player.onChat("inspect", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == STONE) {
        
    }
})
```

```ghost
player.onChat("inspect", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == STONE) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
        }
    }
})
```
