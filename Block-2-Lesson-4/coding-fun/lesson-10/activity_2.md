### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 周囲の状況 

## ステップ1
エージェントが**inspecting the block down**して、それが**not** **packed ice**の場合、もしエージェントが**detects the block right**したら、**move forward**する必要があります。そうでなければ**move right**する必要があります。同じループの中で、もしエージェントが**inspects the block down**して、それが**cobblestone** **or** **gravel**のいずれかであれば、次を行う必要があります: **destroy down**と**collect all**. 

```template
player.onChat("ice", function () {
    while (0 == 0) {
        if (true) {
        	
        } else {
        	
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == COBBLESTONE ||agent.inspect(AgentInspection.Block, DOWN) == GRAVEL ) {
        	
        }
    }
})
```
```ghost
player.onChat("2", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != PACKED_ICE) {
        if (agent.detect(AgentDetection.Block, RIGHT)) {
            agent.move(FORWARD, 1)
        } else {
            agent.move(RIGHT, 1)
        }
        if (agent.inspect(AgentInspection.Block, DOWN) == COBBLESTONE || agent.inspect(AgentInspection.Block, DOWN) == GRAVEL) {
            agent.destroy(DOWN)
            agent.collectAll()
        }
    }
})
```
