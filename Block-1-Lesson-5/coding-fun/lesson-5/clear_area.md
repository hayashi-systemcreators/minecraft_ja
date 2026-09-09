### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 下草を片付けよう!

## ステップ1
エージェントは下草を**8**ブロック、**forward**方向に進みながら壊す必要があります。壊すべき下草の列は**16**列あります。エージェントは``||agent:destroy forward||``と``||agent:move forward||`` **8**回繰り返す必要があります。
#### ~ tutorialhint 
```blocks
player.onChat("foliage", function () {
    for (let index = 0; index < 8; index++) {
        for (let index = 0; index < 8; index++) {
        	
        }
    }
})

```

```ghost
player.onChat("foliage", function () {
    for (let index = 0; index < 8; index++) {
        agent.destroy(FORWARD)
        agent.move(FORWARD, 1)
        for (let index = 0; index < 2; index++) {
            agent.move(FORWARD, 1)
            agent.turn(RIGHT_TURN)
        }
    }
})
```
