### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true
### @explicitHints 1

# その場所をきれいにしよう!

## ステップ1
**14 dandelions**を、隠れ家の**4**辺に沿って植える必要があります。1辺につきエージェントは**14**本のタンポポを植えられます。

#### ~ tutorialhint 
個数を忘れずに設定しましょう。使うのは``||agent:agent set block||``コマンドです。

```ghost
player.onChat("flower", function () {
    for (let index = 0; index < 4; index++) {
        for (let index = 0; index < 14; index++) {
            agent.setItem(YELLOW_FLOWER, 64, 1)
            agent.place(DOWN)
            agent.move(FORWARD, 1)
        }
        agent.turn(RIGHT_TURN)
    }
})

```
