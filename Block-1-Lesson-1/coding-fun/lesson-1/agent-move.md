### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @flyoutOnly 1
### @explicitHints 1

# エージェントを金色の板まで移動させよう!

## ステップ1
``||player:on chat||``コマンドを選択し、名前を**run**から**1**に変更します。``||agent: agent move forward||``ブロックを選択し、``||player:on chat||``コマンドの中にドラッグします。移動する歩数を表す**number**の値を**3**に変更し、エージェントが金色の板に到達できるようにします。完了したら**Play**ボタンを押してコードをコンパイルしたら、Minecraftに戻って**t**キーを押し、次のように入力します: **1**.

#### ~ tutorialhint 
``||agent: agent move||``ブロック内の数値を変えることで、エージェントの移動歩数を変更できます。また、``||agent: agent turn||``ブロックを使うと、エージェントを左右に曲げることができます。

```ghost
player.onChat("1", function () {
    agent.move(FORWARD, 1)
    agent.turn(LEFT_TURN)
})

```
