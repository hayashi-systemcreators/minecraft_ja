### @hideIteration true 
### @explicitHints true

# レッスン3

## ステップ1
これまでに学んだことを活かして、水の上に橋をかけるコードをエージェントに書けますか?   
隙間の幅は3ブロックです。   
完了したら **Play** ボタンを押してコードをコンパイルします。その後Minecraftのワールドに戻り、**T** を押して、次のように入力: **build_a_bridge**.

### ~ tutorialhint
ブロックを設置するときは **down** を忘れずに指定してください!   
また、エージェントのインベントリに **building material** が入っていることを確認してください。ブロックの位置: **slot 1**.

```ghost
player.onChat("run", function () {
    player.say(":)")
    agent.teleportToPlayer()
    agent.turn(LEFT_TURN)
    agent.move(FORWARD, 1)
    agent.place(FORWARD)
})
```