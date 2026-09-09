### @flyoutOnly true
### @hideIteration true
### @explicitHints true

# スペースデブリ

## ステップ1
``||artemis.agent move||``ブロックを使ってエージェントをそれぞれのデブリまで誘導し、``||artemis.collect debris||``ブロックを使って回収します。

```ghost
    artemis.adrvMoveA16()
    artemis.collectDebrisA16()
```
```template
    //
```

```package
artemis-ts=github:ReWrite-Media/artemis-ts#v0.0.66
```
