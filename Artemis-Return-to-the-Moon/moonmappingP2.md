### @flyoutOnly true
### @hideIteration true
### @explicitHints true

# 月面マッピング

## ステップ1
パートナーが訪れるべき3つの地点をマークすると、画面に緑色のXが3つ表示されます。``||artemis.VIPER move||``ブロックを使ってそれぞれの地点まで移動し、``||artemis.take picture||``ブロックを使ってそれぞれの地点で写真を撮影します。

```ghost
    artemis.takePictureA8P2()
    artemis.viperMoveA8P2()
```
```template
    //
```

```package
artemis-ts=github:ReWrite-Media/artemis-ts#v0.0.66
```
