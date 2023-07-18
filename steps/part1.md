# Part 1: Learning the File

Lets take a look at your code

Lines 1-13 are just some basic boilerplate HTML, we include the phaser library with:
```js
<script src="//cdn.jsdelivr.net/npm/phaser@3.11.0/dist/phaser.js"></script>
``` 

On line 17 you should see `var config={..};'
- This is where you configure your phaser game
- the `type` property can be either `Phaser.CANVAS`, `Phaser.WEBGL`, or `Phaser.AUTO` 
    - We recommend using Phaser.AUTO since it will automatically use WEBGL anf fall back on CANVAS if your browser doesnt support it
```js
 type: Phaser.AUTO,
```
- in this tutoial we're just going to set the renderer dimensions and the default scene using the `width` and `height` properties set to 800 x 600 pixels

```js
width: 800,
height: 600,
scene: {
    preload: preload,
    create: create,
    update: update
}
```

An instance of a Phaser.Game object is assigned to a local variable called `game` and the configuration object is passed to it. This will start the process of bringing Phaser to life.

```js
var game = new Phaser.Game(config);
```

The `scene` property will be covered in more detail further in this tutorial

## ➡️ Next steps:
Open up `part2.html` and `part2.md` side by side to start coding
