### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 牛

## ステップ1
スタートコードを見て、まず実行してみましょう。このコードを使うと、ブロック数を数えなくてもエージェントを動かすことができます。エージェントがたどるべき経路を確認し、正しく曲がるようにコーディングを完成させましょう。エージェントが到達できるか確認してください: **gold plate**.  

```template
player.onChat("sheep", function () {
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.move(FORWARD, 1)
    }
    agent.turn(LEFT_TURN)
})

```
