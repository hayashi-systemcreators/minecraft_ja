### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 深い石 

## ステップ1
このコードスニペットを修正しましょう。エージェントの目標は、地表を掘り進んで**gold**ブロックが**left**側にあるところまで到達することです。下に進む途中、エージェントは前方に**stone**があるかどうかを検知して回収します。

```template
player.onChat("dig", function () {
    while (agent.inspect(AgentInspection.Block, LEFT) == AIR) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
            if (agent.inspect(AgentInspection.Block, FORWARD) != GRASS) {
                player.say("Found the stone!")
                agent.destroy(FORWARD)
                agent.collectAll()
        }
    }
})
```
