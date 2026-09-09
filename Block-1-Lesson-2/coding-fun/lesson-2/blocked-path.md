### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1

# エージェントをウミガメの通り道に沿って移動させ、障害物を壊そう!

## ステップ1
エージェントを使って、道を塞いでいる**destroy the tree trunk**には、``||agent: agent destroy||``と``||agent:agent collect all||``ブロックを使います。``||loops:repeat||``ブロックを使うと、コードがより効率的になります。完了したら**Play**ボタンを押してコードをコンパイルします。忘れずにMinecraft内でコードを実行しましょう。

```ghost
player.onChat("path", function () {
    for (let index = 0; index < 4; index++) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.destroy(FORWARD)
        agent.collectAll()
    }
})
```
