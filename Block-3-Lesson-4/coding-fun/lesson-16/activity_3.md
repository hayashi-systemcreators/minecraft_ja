### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 町役場を建てよう!

## ステップ1
**stone**を建築材料として使い、**3** ``||variable: variables||``を作成して、**width**、**length**、**height**という名前にします。``||variable: variables||``を正しい数値に設定します。忘れずに、変数を``||player: on chat||``コマンドに追加してください。

```ghost
player.onChat("town_hall", function (length, width, height) {
    for (let index = 0; index < height; index++) {
        for (let index = 0; index < 2; index++) {
            for (let index = 0; index < length; index++) {
                agent.setItem(STONE, 1, 1)
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
            for (let index = 0; index < width; index++) {
                agent.setItem(STONE, 1, 1)
                agent.place(DOWN)
                agent.move(FORWARD, 1)
            }
            agent.turn(RIGHT_TURN)
        }
        agent.move(UP, 1)
    }
})
```
