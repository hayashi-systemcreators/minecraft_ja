### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 町役場を建てよう!

## ステップ1
**plantSeed**という関数を用意しました。これは前のアクティビティで使ったコードそのものです。次に、``||player: on chat||``コマンドをワークスペースにドラッグし、**run**という名前にします。``||loops: repeat||``ループを追加し、**Advanced**セクションをクリックしてから**Functions**をクリックして、``||function:call plantSeed||``関数をループの中にドラッグします。エージェントが**plantSeed**関数を何回繰り返す必要があるか数えましょう。

### ~ tutorialHint
関数は**Advanced**セクションにあります。私たちが関数について残しておいたようなメモを、書いたコードについて残しておくのも良い習慣です。

```template
/**
 * A function allows you to easily reuse code.
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    agent.place(DOWN)
}
```

```ghost
player.onChat("plantSection", function () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
})
```
