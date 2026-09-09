### @flyoutOnly true
### @hideIteration true
### @explicitHints true

# クルーの食事 プレイヤー2

## ステップ1
パートナーがトマトソースを戻し終えたら、あなたの番です!``||artemis.add||``ブロックを使ってクルーが求める材料をすべて加え、その後``||artemis.serve pizza||``ブロックを使って提供します。ピザには次の材料が必要です:
    - トマトソース
    - チーズ
    - ペパロニ

```ghost
    artemis.addIngredientsA9P2()
    artemis.servePizzaA9P2()
```
```template
    //
```

```package
artemis-ts=github:ReWrite-Media/artemis-ts#v0.0.66
```
