### @hideIteration false 
### @explicitHints 1

# レッスン2

## ステップ1
エージェントを動かすようにプログラムするには、``||player:on chat||`` コマンドを選び、その名前を **run** から **move** に変更します。次に ``||agent: agent move||`` コマンドを選んで、``||player:on chat||`` コマンドの中にドラッグします。

### ~ tutorialhint
エージェントに移動させたいステップ数を変更するのを忘れずに。 

## ステップ3
最終的なコードでは ``||agent: agent move||`` と ``||agent: agent turn||`` のコマンドを組み合わせましょう。エージェントがオレンジのラインに沿って進むようにしてください。 

## ステップ4
完了したら **Play** ボタンを押してコードをコンパイルします。その後Minecraftのワールドに戻り、**T** を押して、次のように入力: **move**.

## ステップ5
エージェントに木を切り倒させるには、新しい ``||player:on chat||`` コマンドを選びます。次に ``||agent: agent move||``、``||agent: agent destroy||`` のコマンドを追加します。エージェントをどちらの方向に動かしたいか考えてみましょう。 

### ~ tutorialhint
エージェントが動ける方向: **up**、**down**、**forward**、**back**、**left**、**right**. 

## ステップ6
``||agent: agent collect all||`` コマンドをコードに追加するのを忘れずに。エージェントが板材ブロックをすべて回収できるようにしましょう。 

## ステップ7 
それでは、これらのコマンドをいろいろな組み合わせで使う練習をしてみましょう。 

```ghost
player.onChat("run", function () {
    player.say(":)")
    agent.teleportToPlayer()
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.destroy(FORWARD)
    agent.collectAll()
})
```
