### @flyoutOnly true
### @hideIteration true
### @explicitHints true

# 氷の掘削

## ステップ1
パートナーがローバーを所定の位置に移動させたら、``||artemis.drill down||``ブロックを使って掘削し、その後``||artemis.collect sample||``ブロックを使ってサンプルを採取します。パートナーのコードが終わるのを必ず待ってください。早く始めすぎると掘削が早すぎることになります。

```ghost
    artemis.drillDownA6()
    artemis.collectSampleA6()
```
```template
    //
```

```package
artemis-ts=github:ReWrite-Media/artemis-ts#v0.0.66
```
