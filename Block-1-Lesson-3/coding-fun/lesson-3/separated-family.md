### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 離ればなれの家族!

## ステップ1
氷の裂け目に橋を架けるようエージェントをプログラムしましょう。エージェントのインベントリに**64**個の**oak planks**があることを確認してください。

#### ~ tutorialhint 
忘れずに**not**を、**while**ループの中で使ってください。エージェントがどこにブロックを置きたいか考えましょう。

```ghost
player.onChat("family", function () {
    agent.setItem(PLANKS_OAK, 64, 1)
    agent.move(FORWARD, 1)
    while (!(agent.detect(AgentDetection.Block, FORWARD))) {
        agent.place(DOWN)
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
    }
})

```
