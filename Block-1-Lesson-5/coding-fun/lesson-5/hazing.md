### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 侵入を防ぐ罠

## ステップ1
エージェントは**tripwire**を設置して、オオカミが入ってこないようにする必要があります。``||agent:agent set block||``を**tripwire**に設定し、個数を**64**にしましょう。``||loops:while||``ブロックを使い、その中に条件を入れます。  

#### ~ tutorialhint
条件の中で**not**を使うのを忘れないようにしましょう。

```blocks
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
    	
    }
})

``` 
```ghost
player.onChat("hazing", function () {
    agent.setItem(TRIPWIRE, 64, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
})
```
