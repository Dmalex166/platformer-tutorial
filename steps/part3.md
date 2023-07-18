# Part 3: World Building

So now you know `this.add.image` is creating a new image game object and adding it to the Scene display list
- You could position these images anywhere on screen, even noutside the bounds of your phaser game or outside the screen
- They will still exist, they just won't be visable
<br>

### Camera system
The Camera system controls your view into the Scene and you can move and zoom the active camera as required.
You can also create new cameras for other views into the Scene.
- It won't be covered in this tutorial but the Phaser 3 camera is significantly more powerful than in v2

## Build Scene
Lets buid  up the scene by adding the background image and some platforms
```js
var platforms;

function create ()
{
    this.add.image(400, 300, 'sky');

    platforms = this.physics.add.staticGroup();

    platforms.create(400, 568, 'ground').setScale(2).refreshBody();

    platforms.create(600, 400, 'ground');
    platforms.create(50, 250, 'ground');
    platforms.create(750, 220, 'ground');
}
```

You'll see `this.physics` , this means we're using the Arcade Physics System
For take effect ww will need to add it to our game config (tell the Phaser game we require it)
```js
var config = {
    type: Phaser.AUTO,
    width: 800,
    height: 600,
    physics: {
        default: 'arcade',
        arcade: {
            gravity: { y: 300 },
            debug: false
        }
    },
    scene: {
        preload: preload,
        create: create,
        update: update
    }
};
```

### At this point your game should look something like this:
![part 3 example image](/assets/part3.png)


## ➡️ Next steps:
Open up [part4.html](/part4.html) and [part4.md](part4.md) side by side to start coding



