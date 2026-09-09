### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 種を植えよう!

## ステップ1
まず、エージェントとやり取りしてインベントリを開き、種を渡します。次に``||player: on chat||``コマンドを作成し、``||agent: till forward||``と次を追加します: ``||agent: place forward||``. 

```ghost
player.onChat("plantSeed", function () {
    agent.till(FORWARD)
    agent.place(FORWARD)
})
```
