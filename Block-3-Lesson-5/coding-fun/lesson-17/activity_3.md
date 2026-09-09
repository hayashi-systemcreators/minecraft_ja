### @codeStart players set @s makecode 0
### @codeStop players set @s makecode 1

### @hideIteration true 
### @explicitHints 1

# ビーツを植えよう!

## ステップ1

2つの関数、**plantSeed**と**plantSection**を用意しています。新しい``||player: on chat||``コマンドを作成し、その中に``||functions: call plantSection||``を追加してください。``||logic: if||``文を追加し、``||agent: agent inspects block down||``かどうかを確認します。
下のブロックが``||blocks: lapis lazuli||``の場合、エージェントは次を行う必要があります: ``||agent: turn right||``、``||agent: move forward||``、``||agent: turn right||``.  
``||logic: Else||``。エージェントが``||agent: inspects the block down||``して、それが``||blocks: a block of quartz||``の場合は、次を行う必要があります: ``||agent: turn left||``、``||agent: move forward||``、``||agent: turn left||``。
最後に``||functions: call plantSection||``.

#### ~ tutorialhint
``` blocks
player.onChat("run", function () {
    plantSection()
})
```

```template
/**
 * We are calling a function inside a function
 */
function plantSection () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
}
 /**
 * The code was modified to not place seeds if there's no block under the Agent.
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    if (agent.detect(AgentDetection.Block, DOWN)) {
        agent.place(DOWN)
    }
}

/**
* You need to check if the Agent is stepping on a lapis block turn right, if quartz turn left.
*/
```
## ステップ2
``||logic:if||``文を``||player:on chat||``コマンドに追加します。**true**の``||logic:if|``ブロックの中に``||logic:" " = " "||``ブロックを追加します。``||agent:agent inspects block down||``が**equal (=)**で``||blocks:lapis lazuli||``であれば、エージェントは次を行う必要があります: ``||agent: turn right||``、``||agent:move forward||``、``||agent:turn right||``. 

#### ~ tutorialhint
``` blocks
player.onChat("run", function () {
    plantSection()
    if (agent.inspect(AgentInspection.Block, DOWN) == LAPIS_LAZULI_BLOCK) {
        agent.turn(RIGHT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    }

})
```

```template
/**
 * We are calling a function inside a function
 */
function plantSection () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
}
 /**
 * The code was modified to not place seeds if there's no block under the Agent.
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    if (agent.detect(AgentDetection.Block, DOWN)) {
        agent.place(DOWN)
    }
}

/**
* You need to check if the Agent is stepping on a lapis block turn right, if quartz turn left.
*/
```

## ステップ3
**+**記号を``||logic:if||``ブロックの上で2回クリックします。** - **をクリックして、**else**ブロックを削除します。``||logic:" " = " "||``ブロックを、**blank**になっている``||logic:else if||``ブロックのスペースに追加します。``||agent:agent inspects block down||``が**equal (=)**で``||blocks:a block of quartz||``であれば、エージェントは次を行う必要があります: ``||agent:turn left||``、``||agent:move forward||``、``||agent:turn left||``.  

#### ~ tutorialhint
``` blocks
player.onChat("run", function () {
    plantSection()
    if (agent.inspect(AgentInspection.Block, DOWN) == LAPIS_LAZULI_BLOCK) {
        agent.turn(RIGHT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    } else if (agent.inspect(AgentInspection.Block, DOWN) == BLOCK_OF_QUARTZ) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
    }

})
```

```template
/**
 * We are calling a function inside a function
 */
function plantSection () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
}
 /**
 * The code was modified to not place seeds if there's no block under the Agent.
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    if (agent.detect(AgentDetection.Block, DOWN)) {
        agent.place(DOWN)
    }
}

/**
* You need to check if the Agent is stepping on a lapis block turn right, if quartz turn left.
*/
```

## ステップ4
最後に、もう一つ``||functions: call plantSection||``を``||player:on chat||``コマンドの中に、``||logic:if||``文の外側に追加します。  

#### ~ tutorialhint
``` blocks
player.onChat("run", function () {
    plantSection()
    if (agent.inspect(AgentInspection.Block, DOWN) == LAPIS_LAZULI_BLOCK) {
        agent.turn(RIGHT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    } else if (agent.inspect(AgentInspection.Block, DOWN) == BLOCK_OF_QUARTZ) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(LEFT_TURN)
    }
    plantSection()
})
```

```template
/**
 * We are calling a function inside a function
 */
function plantSection () {
    for (let index = 0; index < 11; index++) {
        plantSeed()
    }
    agent.move(FORWARD, 1)
}
 /**
 * The code was modified to not place seeds if there's no block under the Agent.
 */
function plantSeed () {
    agent.till(FORWARD)
    agent.move(FORWARD, 1)
    if (agent.detect(AgentDetection.Block, DOWN)) {
        agent.place(DOWN)
    }
}

/**
* You need to check what block your Agent is on. If on a lapis block turn right, else if quartz turn left.
*/

/**
* You can click on the + button of an If block to add an Else
*/

```

```ghost
player.onChat("turn", function () {
    plantSection()
    if (agent.inspect(AgentInspection.Block, DOWN) == LAPIS_LAZULI_BLOCK) {
        agent.turn(RIGHT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    } else if (agent.inspect(AgentInspection.Block, DOWN) == BLOCK_OF_QUARTZ) {
        agent.turn(LEFT_TURN)
        agent.move(FORWARD, 1)
        agent.turn(RIGHT_TURN)
    }
    plantSection()
})
```
