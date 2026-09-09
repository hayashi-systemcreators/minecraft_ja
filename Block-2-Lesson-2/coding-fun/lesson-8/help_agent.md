### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 鉄

## ステップ1
エージェントが**inspects the block down**を行い、そのブロックが**iron ore**でない間は、**move forward**する必要があります。エージェントが**detects a block forward**した場合は、**destroy forward**する必要があります。鉄を見つけたら、それを**collect**するようプログラムしましょう。ブロックを回収するには、まずそれを破壊する必要があることに注意してください。

```ghost
player.onChat("4", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != IRON_ORE) {
        if (agent.detect(AgentDetection.Block, FORWARD)) {
            agent.destroy(FORWARD)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the iron ore!")
    agent.destroy(DOWN)
    agent.collectAll()
})
```
