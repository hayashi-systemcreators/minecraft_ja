### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 周囲の状況 

## ステップ1
エージェントが**inspecting the block down**して、それが**packed ice**であり、**if**エージェントが**detects the block right**した場合は、**move forward**する必要があります。そうでなければ次を行います: **move right**. 

```ghost
player.onChat("1", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) == PACKED_ICE) {
        if (agent.detect(AgentDetection.Block, RIGHT)) {
            agent.move(FORWARD, 1)
        } else {
            agent.move(RIGHT, 1)
        }
    }
})
```
