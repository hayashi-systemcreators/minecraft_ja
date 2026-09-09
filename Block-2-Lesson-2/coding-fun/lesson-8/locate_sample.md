### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# サンプルを見つけよう! 

## ステップ1
**While**、エージェントが**inspects the block down**を行い、**not**、**blue ice**を見つけられない間は、エージェントに**destroy**と**move down**を行うようプログラムしましょう。エージェントが**blue ice**を見つけたら、それを**destroy down**して、**collect**し、サンプルを回収する必要があります。

```ghost 
player.onChat("ice", function () {
    while (agent.inspect(AgentInspection.Block, DOWN) != ICE) {
        agent.destroy(DOWN)
        agent.move(DOWN, 1)
    }
    agent.destroy(DOWN)
    agent.collectAll()
    
})
```
