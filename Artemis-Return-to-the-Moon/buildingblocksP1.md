### @flyoutOnly true
### @hideIteration true
### @explicitHints true

# ビルディングブロック

## ステップ1
``||artemis.rover move||``ブロックを使ってローバーを月のレゴリスの山(3か所)まで移動させ、その後``||artemis.collect regolith||``ブロックを使って回収します。

```ghost
    artemis.roverMoveA5()
    artemis.collectBlockA5()
```
```template
    //
```

```package
artemis-ts=github:ReWrite-Media/artemis-ts#v0.0.66
```
