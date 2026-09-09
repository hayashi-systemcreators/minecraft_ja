### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 資源を採掘しよう!

## ステップ1
エージェントは**gold ore**と**iron ore**のブロックを採掘する必要があります。いくつかの``||player:on chat||``コマンドを作成して、エージェントをさまざまな方向に動かすようプログラムしてみましょう。例えば**forward**、**back**、**right**などです。エージェントをどれだけ動かすか指定する代わりに、変数を使うことができます。ゲーム内チャットでコマンドを入力するときは、**forward**と**a number**を入力します。例えば**forward 5**のように入力すれば、エージェントに**move 5 steps forward**させることができます。こうすることで、コードを変更せずに、その場でエージェントが動くべき歩数を変えられます。

### ~ tutorialHint
エージェントが鉱物を採掘するようプログラムするには、忘れずに``||agent: destroy||``と``||agent: collect||``ブロックを追加しましょう。

```template
player.onChat("forward", function (num1) {
    agent.move(FORWARD, num1)
})
```
```ghost
player.onChat("right", function (num1) {
    agent.turn(RIGHT_TURN)
    agent.move(FORWARD, num1)
})
player.onChat("back", function (num1) {
    agent.turn(RIGHT_TURN)
    agent.turn(RIGHT_TURN)
    agent.move(FORWARD, num1)
})
player.onChat("left", function (num1) {
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, num1)
})
player.onChat("collect", function () {
    agent.destroy(DOWN)
    agent.collectAll()
})
```
