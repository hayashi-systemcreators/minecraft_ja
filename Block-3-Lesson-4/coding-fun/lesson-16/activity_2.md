### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 最初の家を建てよう!

## ステップ1
用意されたサンプルコードを使って、ブロックを1列設置します。次に、エージェントは同じ手順を**4 times**繰り返し、その後``||agent: move up||``して、さらに**repeat**します。``||variable: height||``を取得し、``||loops: repeat||``ブロックに追加します。このコードで、家を**1**軒建てられます。

### ~ tutorialHint
コマンドを入力する際、ゲーム内チャットで数値を入力するのを忘れないでください。例えば次のように: **house 2 5**. 

```template    
 player.onChat("house", function (height, size) {
    for (let index = 0; index < size; index++) {
        agent.setItem(STONE, 1, 1)
        agent.place(DOWN)
        agent.move(FORWARD, 1)
    }
    agent.turn(RIGHT_TURN)
})
```

```ghost
player.onChat("build-simple", function (size, height) {
    for (let index = 0; index < height; index++) {
        for (let index = 0; index < 4; index++) {
            for (let index = 0; index < size; index++) {
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
