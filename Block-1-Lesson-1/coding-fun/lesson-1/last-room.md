### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1

# エージェントを金色の板まで上に移動させよう!

## ステップ1
エージェントが金色の板に到達するようにプログラムしましょう。あなたは自分の金色の板の上に、エージェントはもう一方の金色の板の上にとどまる必要があります。完了したら**Play**ボタンを押してコードをコンパイルします。Minecraftに移動して、コードを実行しましょう。

```ghost
player.onChat("last", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})
```
