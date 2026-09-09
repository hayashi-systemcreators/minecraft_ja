### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# 世界を変えよう!

## ステップ1
``||player:on player walk||``イベントを使って、決まった``||positions: world||``座標(具体的には**100, 68, 100**)にブロックを設置します。``||variable||``を作成して**count**という名前にします。``||change count by 1||``ブロックと、``||blocks:place||``ブロックに``||count||``変数を追加してドラッグします。これにより値が1増え、そのブロックIDに対応するブロックが設置されます(1=石、2=草ブロック、3=土、など)。別のイベントブロック、例えば``||player:on player fall||``を使ってブロックをリセットします。そのためには、``||set count||``を**0**にドラッグしてカウントを再開させ、``||blocks: place||``ブロックに``||variable:count||``変数を追加して同じワールド座標を設定します。こうすることで、ワールド内でジャンプするたびに、ブロックがリセットされます。


### ~ tutorialhint 
座標を示すには、忘れずに``||positions: world||``の位置情報を使いましょう。

```blocks
let count = 0
player.onTravelled(WALK, function () {
    count += 1
    blocks.place(count, world(100, 68, 100))
})
```

```ghost
let count = 0
player.onTravelled(WALK, function () {
    count += 1
    blocks.place(count, world(100, 68, 100))
})
player.onTravelled(FALL, function () {
    count = 0
    blocks.place(count, world(100, 68, 100))
})
```
