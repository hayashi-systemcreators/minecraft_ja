### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1

# エージェントをウミガメの通り道に沿って移動させよう!

## ステップ1
ウミガメの通り道に沿ってエージェントを移動させるには、``||agent: agent move forward||``ブロックを使って門まで進みます。完了したら**Play**ボタンを押してコードをコンパイルします。忘れずにMinecraft内でコードを実行しましょう。

```ghost
player.onChat("tracks", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
for (let index = 0; index < 4; index++) {
    	
 }
```
