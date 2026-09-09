### @flyoutOnly true
### @hideIteration true
### @explicitHints true

# ビルディングブロック

## ステップ1
パートナーが十分な材料を集めたら、``||artemis.process regolith||``ブロックを使って加工し、``||artemis.cast block||``ブロックを使って成形し、``||artemis.test block-strength||``ブロックを使って強度をテストします。

```ghost
    artemis.meltRegolithA5()
    artemis.castBlocksA5()
    artemis.testBlockStrengthA5()
```
```template
    //
```

```package
artemis-ts=github:ReWrite-Media/artemis-ts#v0.0.66
```
