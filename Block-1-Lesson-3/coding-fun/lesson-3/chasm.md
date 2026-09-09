### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 大きな裂け目!

## ステップ1
エージェントが氷の裂け目を渡って**build a bridge**できるようプログラムしましょう。まずは``||agent:set block or item||``を使って、エージェントのインベントリに必要な材料があることを確認します。建築材料には**oak**を選び、個数には**64**を選択します。これが**amount of blocks**. ``||loops:while||``を使い、エージェントが下にブロックを検知して**not**いない間、オークの板材を**down**に設置してから**forward**に移動し、橋を作るようプログラムします。    

```template
player.onChat("chasm", function () {
    agent.setItem(PLANKS_OAK, 1, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, DOWN))) {
    	
    }
})
```

```ghost
player.onChat("chasm", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})

```
