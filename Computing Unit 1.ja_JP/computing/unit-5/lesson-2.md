### @explicitHints 1

# レッスン2: 風力発電所をアニメーションさせる 

## ステップ1
ブレードの模型を3つコードします。   

風力発電所から離れた場所に、アニメーション用の秘密の模型を作るスペースを見つけましょう。ワールド内のどこでも構いませんが、丘の上から見えない場所にするのが理想です。

まずは特定の回転位置にあるタービンブレードの1つ目の模型を作ります。以下の例では、ブレードを **Yellow Wool** で作っていますが、好きな素材で作ってかまいません。最終的なアニメーションで見せたい向きに合わせて作る必要があるので、このレッスンの最後に表示されたときに見たい向きを考えて建ててください。 

また、``||Blocks:clone||`` ツールを使うと、コピー元の建物の向きは常に保たれます。たとえば東を向いた建物をコピーすれば、複製されたものも常に東を向きます。 

## ステップ2
次に、この隣にもう一つ作りますが、今度は別の回転状態のブレードにします。3つ目、最後のバリエーションとして、さらに別の回転状態のブレードをもう一つ作ります。   

この3つの建築物が、アニメーションの3コマになります。漫画や映画のコマのように、続けて素早く再生することで動いているように見えます。  

1つ目のタービンにある模型ブレードを複製します。次の工程は、模型ブレードが動くようにコードすることです。まずは1つのブレードだけで作業し、その後、残り2つの風力ブレードについても同じ手順を繰り返します。 

## ステップ3
新しい ``||Player:on chat command||`` コードブロックを選び、テキストを次のように変更: **wind_turbine**. 


``||Loops:repeat [4] times||`` コードブロックを ``||Player:on chat command||`` ブロックにドラッグします。テストのため、数値はそのまま **4**. 
#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
    	
    }
})
```

## ステップ4
``||Blocks:BLOCKS||`` ドロワーを開き、``||Blocks:clone from||`` ブロックを ``||Player:on chat command||`` ブロックにドラッグします。 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        pos(0, 0, 0),
        pos(0, 0, 0),
        pos(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ5
**relative** の座標オーバル3つすべてを、``||Positions:world [0] [0] [0]||`` メニューにある ``||Positions:POSITIONS||`` の座標オーバルに置き換えます。  

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ6
``||Blocks:clone from||`` コードブロックを右クリックして、**Duplicate** を選ぶと、薄く表示された複製が作られます。それを最初のコードブロックの下にドラッグします。   

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ7
もう一つ複製を作り、同じように下に配置します。これで ``||Blocks:clone from||`` ブロックが合計3つになります。 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(0, 0, 0),
        world(0, 0, 0),
        world(0, 0, 0),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```

## ステップ8
タービンブレードの模型に戻り、複製に必要な座標をワークブックに記録します。各ブレード全体を囲む見えない立方体を作るため、座標を各建築物の右上と左下に設定します。 

**Blade set 1** – 開始: **55 78 -291** 終了: **61 85 -291**

**Blade set 2** – 開始: **63 78 -291** 終了: **69 85 -291**

**Blade set 3** – 開始: **71 78 -291** 終了: **77 85 -291**

## ステップ9
複製元の座標を入力しましょう。MakeCodeに戻り、1つ目、2つ目、3つ目のブレードの座標を ``||Blocks:clone from||`` コードブロックの ``||Blocks:from||`` と ``||Blocks:to||`` のセクションに慎重に入力します。``||Blocks:into||`` のセットは今のところ空欄のままにしておきます。  

## ステップ10
このユニットの **Lesson 1** で作った風力タービンの構造物に戻ります。  

## ステップ11
タービンの柱の一番上から、好きな材料で20ブロックの塔を建てます。これは最終的な座標を見つけるためのテスト用の柱です。この例では次を使いました: **Yellow Wool**.  

塔の一番上のブロックの座標をワークブックに記録しておきましょう。  

## ステップ12
次にこれを、3つすべての ``||Blocks:clone from||`` コードブロックのinto座標に追加します。 

#### ~ tutorialhint
``` blocks
player.onChat("wind_turbine", function () {
    for (let index = 0; index < 4; index++) {
        blocks.clone(
        world(55, 78, -291),
        world(61, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(63, 78, -291),
        world(69, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
        blocks.clone(
        world(71, 78, -291),
        world(77, 85, -291),
        world(8, 113, -409),
        CloneMask.Replace,
        CloneMode.Normal
        )
    }
})
```
## ステップ13
複製先の座標をテストしましょう。アニメーションを本番用に配置する前に、簡単なテストを行います。ここでは、コマンドを実行したときにブレードがどこに複製されるかを確認します。配置した向きやサイズなどによって、人によって結果が異なる場合があります。  

ブレードの中心を使って、下、そして中心へと進みます。この例では **Orange Wool** でマークしています。この情報をワークブックに記録しましょう。 

下側の水平部分から、ブレードアニメーションの中心が3ブロック右にずれていたことがわかります。これは後で補正します。 

次に高さについても同様に、柱の一番上からブレードアニメーションの中心までを測り、ワークブックに記録します。ここでも **Orange Wool** でマークしていますが、今回は左側です。  

この上側の垂直部分から、中心が4ブロック高すぎたことがわかります。これで両方とも補正できます。 

別の材料を使って、タービンの実際の中心点から測定し、方向と数値を補正します。  

## ステップ14
これでアニメーションの新しい正確な中心座標が見つかりました。この最後のブロックの上に立って座標を確認します。これをワークブックに記録し、コードの ``||Blocks:into||`` の座標セットに追加します。  

## ステップ15
それではコードを実行して、タービンの柱の上に正確に動く風力ブレードがあるか確認しましょう。うまく動かない場合は、必要に応じて調整してください。メモが必要な場合はワークブックのスペースを使ってください。 

## ステップ16
正しく複製できたら、テストがどれだけずれていたかを確認するために追加したテスト用ブロックを取り除きます。この例では **Yellow, Orange, **、**Red Wool** のブロックを取り除くことになります。 

模型のブレードは取り除かないでください!他のタービンに複製するために、そのまま残しておく必要があります。 

ファーム内の他のタービンもアニメーションさせましょう。1つ目が完成したので、他のタービンもアニメーションさせる準備ができました。同じ模型の座標を使い、``||Blocks:into||`` の座標入力を新しいタービンごとに変更するだけです。
