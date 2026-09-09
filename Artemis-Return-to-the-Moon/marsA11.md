### @flyoutOnly true
### @hideIteration true
### @explicitHints true

# 火星偵察

## ステップ1
``||artemis.rover move||``ブロックを使ってエージェントを緑色のXまで移動させ、その後``||artemis.take picture||``ブロックを使って写真を撮影します

```ghost
    artemis.roverMoveA11()
    artemis.takePictureA11()
```
```template
    //
```

```package
artemis-ts=github:ReWrite-Media/artemis-ts#v0.0.66
```
