### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 3D空間

## ステップ1
この課題を解決するには、エージェントが**gold**ブロックまで行って回収するようプログラムする必要があります。まずは地上階でこれを行い、次に**move 3 levels up**して、同じ手順を繰り返してください。  

```template
player.onChat("3D", function () {
    for (let index = 0; index < 2; index++) {
        
})
``` 
```ghost
player.onChat("3D", function () {
    for (let index = 0; index < 2; index++) {
        while (agent.inspect(AgentInspection.Block, FORWARD) != GOLD_BLOCK) {
            if (!(agent.detect(AgentDetection.Block, FORWARD))) {
                agent.move(FORWARD, 1)
            } else {
                agent.turn(LEFT_TURN)
            }
        }
        agent.destroy(FORWARD)
        agent.collectAll()
        agent.move(UP, 3)
    }
})
```
