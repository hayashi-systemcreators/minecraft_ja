### @flyoutOnly true
### @hideIteration true
### @explicitHints true

# クルーの食事 プレイヤー1

## ステップ1
まず最初に、トマトソースを戻すのがあなたの仕事です。``||artemis.toggle power||``ブロックを使って戻し装置の電源を入れます。次に、``||artemis.place freeze-dried||``ブロックを使ってトマトソースを戻し装置にセットし、``||artemis.rehydrate with||``ブロックを使って水の量を設定します。どれくらいの水が必要かは、チャートで確認してください。最後に、作業が終わったら装置の電源を切るのを忘れないでください。

```ghost
    artemis.togglePowerA9P1()
    artemis.placeIngredientA9P1()
    artemis.rehydrateA9P1()
```
```template
    //
```

```package
artemis-ts=github:ReWrite-Media/artemis-ts#v0.0.66
```
