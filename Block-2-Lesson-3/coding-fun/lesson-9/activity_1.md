### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 石を見つけよう 

## ステップ1
このコードスニペットを修正しましょう。エージェントが行うべきことは次のとおりです: **move**して**left 4 times**、**destroy down**、**move down**を行います。エージェントが前方に**stone**ブロックを検知したら、「Found the stone!」と発言し、**destroy forward**と**collect all**を行います。石が**not detected**の場合、エージェントは「No stone here!」と発言する必要があります。下に移動するたびに、エージェントは**move 1 block up**して地表に戻る必要があります。このアクティビティは**4**回繰り返す必要があります。

```template
player.onChat("stone", function () {
    for (let index = 0; index < 3; index++) {
        agent.move(RIGHT, 4)
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
        if (agent.inspect(AgentInspection.Block, FORWARD) != STONE) {
            player.say("Found the stone!")
            agent.destroy(FORWARD)
            agent.collectAll()
        } else {
            player.say("No stone here!")
        }
        agent.move(UP, 1)
    }
})
```
