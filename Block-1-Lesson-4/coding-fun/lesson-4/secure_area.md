### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# エリアを守ろう

## ステップ1
エージェントに**oak fence**を作らせるようプログラムしましょう。エージェントは**oak fence**ブロックを右側に設置し、障害物を壊しながら前進する必要があります。フェンスの長さは**17 blocks**にしましょう。

#### ~ tutorialhint
エージェントが右側にブロックを設置し、左側のブロックを壊すようにしましょう。

```blocks
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
            }
})
```
```ghost
player.onChat("fence", function () {
    agent.setItem(OAK_FENCE, 64, 1)
    for (let index = 0; index < 17; index++) {
        agent.place(RIGHT)
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
    }
})
```
