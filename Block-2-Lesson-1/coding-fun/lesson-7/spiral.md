### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# スパイラル

## ステップ1
エージェントが**inspecting the block forward**を行い、それが**not**、つまり**gold block**でない間は、エージェントは**move forward**する必要があります。前方にブロックを検知**not**しない場合、エージェントも前進する必要があり、検知した場合は**turn left**する必要があります。エージェントが**gold block**に到達したら、それを**destroy**し、**collect**する必要があります。

```ghost
player.onChat("3", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
        if (!(agent.detect(AgentDetection.Block, FORWARD))) {
            agent.move(FORWARD, 1)
        } else {
            agent.turn(LEFT_TURN)
        }
    }
    agent.destroy(FORWARD)
    agent.collectAll()
})
```
