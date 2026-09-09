### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 竹の隠れ家

## ステップ1
砂地の各辺に竹を**3**ブロック分植えるようエージェントをプログラムしましょう。アクティビティを完了できるように、``||agent: agent turn||``コマンドも忘れずに追加してください。

#### ~ tutorialhint
2つの**repeat**ループが必要で、一方をもう一方の中に入れ子にします。
 
```ghost
player.onChat("bamboo", function () {
    for (let index = 0; index < 3; index++) {
        agent.setItem(BAMBOO, 64, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
})
```
