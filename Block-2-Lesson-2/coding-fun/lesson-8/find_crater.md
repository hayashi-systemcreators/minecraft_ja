### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 周囲の状況 

## ステップ1
エージェントが**detects the block down**している間は、前進する必要があります。エージェントが**inspects the block down**を行い、**air**を見つけたら、``||player:say||``コマンドを使って、次のように言います: **Crater found!**. 

```template
player.onChat("crater", function () {
            player.say("Crater found!")
})
```
```ghost
player.onChat("1", function () {
    while (agent.detect(AgentDetection.Block, DOWN)) {
        agent.move(FORWARD, 1)
    }
    if (agent.inspect(AgentInspection.Block, DOWN) == AIR) {
        player.say("Crater found!")
    }
})
```
