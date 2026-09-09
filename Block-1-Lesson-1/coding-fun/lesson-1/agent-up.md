### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1

# エージェントを金色の板まで上に移動させよう!

## ステップ1
``||player:on chat||``と``||agent:agent move||``コマンドを使って、エージェントが金色の板に向かって移動するようプログラムしましょう。エージェントを**up**方向に動かすようにプログラムできます。完了したら**Play**ボタンを押してコードをコンパイルします。Minecraftに移動して、ゲーム内でコードを実行しましょう。

```ghost
player.onChat("up", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

```
