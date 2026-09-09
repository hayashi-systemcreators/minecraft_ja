### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 探査車を修理しよう 

## ステップ1
このコードスニペットを修正しましょう。目標は、**inspecting**で**air**のブロックを探し、**not**見つからない間、エージェントは**move right**する必要があります。エージェントが**lapis lazuli** **in front**のブロックを見つけたら、**move right**、**turn left**、そして**move right**する必要があります。その後、エージェントは「Found the break!」と発言し、**place a block of redstone forward**.

```template
player.onChat("repair", function () {
    while (agent.inspect(AgentInspection.Block, FORWARD) == AIR) {
        agent.move(RIGHT, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) == LAPIS_LAZULI_BLOCK) {
            agent.move(RIGHT, 1)
            agent.turn(RIGHT_TURN)
            agent.move(LEFT, 1)
        }
    }
    player.say("Found the break!")
    agent.setItem(GRASS, 1, 1)
    agent.place(FORWARD)
})
```
