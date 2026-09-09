### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 子グマを見つけよう!

## ステップ1
どれくらいの距離があるか分からないまま道を掘り進めるようエージェントをプログラムするには、``||loops:while||``と``||agent:agent detect||``コマンドを使います。すべての雪を通り抜けられるように、エージェントは``||agent:destroy forward & up||``する必要があります!完了したら**Play**ボタンを押してコードをコンパイルします。忘れずにMinecraft内でコードを実行しましょう。

#### ~ tutorialhint 
コードのブロックをつなげるとき、その形をよく見てみましょう。次のブロックを使います: ``||agent:agent move forward||``.

```template
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
    	
    }
})
```

```ghost
player.onChat("cub", function () {
    while (agent.detect(AgentDetection.Block, FORWARD)) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        agent.destroy(UP)
    }
})

```
