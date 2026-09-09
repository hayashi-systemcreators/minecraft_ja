### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 探査車を追跡しよう 

## ステップ1
このコードスニペットを修正しましょう。目標は、**inspecting forward**で**quartz**のブロックを探し、**not**見つからない間、エージェントは**move forward**する必要があります。もし**detects**したものが**gold**ブロックで**down**にある場合は、**turn right**する必要があります。もし**block of iron down**を検知した場合は、**turn left**する必要があります。最後にエージェントは「Found the rover!」と発言する必要があります。

```template
player.onChat("rover", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) != BLOCK_OF_QUARTZ) {
            if (agent.inspect(AgentInspection.Block, UP) == GOLD_BLOCK) {
            agent.turn(LEFT_TURN)
        }
            if (agent.inspect(AgentInspection.Block, RIGHT) == IRON_BLOCK) {
            agent.turn(RIGHT_TURN)
        }
        agent.move(FORWARD, 1)
    }
    player.say("Found the rover!")
})
```
