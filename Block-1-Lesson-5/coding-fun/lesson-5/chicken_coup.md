### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 鶏小屋

## ステップ1
エージェントは**2**層分、**9**ブロックの**iron bars**を設置する必要があります。**4**つの面すべてに**iron bars**が必要です。2段目を作るには、``||agent:agent move up||``を使うのを忘れないでください。

#### ~ tutorialhint
最終的には**3** ``||loops:repeat|``個のコマンドが互いに入れ子になります。エージェントのインベントリに64個を超えるブロックがあることを確認してください!

```ghost
player.onChat("chicken", function () {
    for (let index = 0; index < 2; index++) {
        agent.setItem(IRON_BARS, 1, 1)
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < 9; index++) {
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})

```
