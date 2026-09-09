### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration false 
### @explicitHints 1

# もっと高いところへ!

## ステップ1
エージェントに**oak**ブロックで高さ**10**の塔を建てさせましょう。まずは**64**個の**oak plank**を``||agent:set block or item||``コマンドでエージェントに持たせます。次に**forward**、**left**、**right**の順にオークの板材を設置するよう、``||agent:agent place||``ブロックを使ってプログラムしましょう。ブロックを設置したあとは**move up**する必要があります。  

#### ~ tutorialhint 
``||loops:repeat||``ブロックを使い、数値を次のように変更します: **10**. 

## ステップ2
エージェントを塔から**down**させ、**ladder**を高さ**10**ブロックで作りましょう。上るために梯子が必要です!

#### ~ tutorialhint 
エージェントのインベントリに**64**個の**ladder**を選んでおくのを忘れないようにしましょう。これは``||agent: agent set block||``を使ってエージェントが梯子を設置できるようにするためです。

```ghost
player.onChat("tower", function () {
    agent.move(FORWARD, 1)
    agent.setItem(LADDER, 64, 1)
    for (let index = 0; index < 10; index++) {
        agent.place(FORWARD)
        agent.move(UP, 1)
    }
    agent.move(DOWN, 10)
})

```
