### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# マグマに到達しよう

## ステップ1
エージェントが**move forward**するようプログラムしましょう。エージェントが**inspects**するブロックが**down**で、それが**not magma**である間は、次を行う必要があります: **move down**. 

```ghost
player.onChat("magma", function () {
    agent.move(FORWARD, 1)
    while (agent.inspect(AgentInspection.Block, DOWN) != MAGMA_BLOCK) {
        agent.move(DOWN, 1)
    }
})
```
