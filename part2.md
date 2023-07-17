# Part 2: Loading Assets

Let's load the assets we need for our game. 

### Preload an Image

You do this by putting calls to the Phaser Loader inside of a Scene function called preload. Phaser will automatically look for this function when it starts and load anything defined within it.

Currently the preload function is empty. Change it to:
``` js
function preload ()
{
    this.load.image('sky', 'assets/sky.png');
    this.load.image('ground', 'assets/platform.png');
    this.load.image('star', 'assets/star.png');
    this.load.image('bomb', 'assets/bomb.png');
    this.load.spritesheet('dude', 'assets/dude.png', { frameWidth: 32, frameHeight: 48 });
}
```

This will load 5 assets ( 4 images and a sprite sheet)
- Take note of the first parameter for all the images (ex:`sky`), this is important as it will be what you use to refer to assets throughout your code

### Display an Image

In order to display one of the images we've loaded place the following code inside the `create` function:
```js
function create ()
{
    this.add.image(400, 300, 'sky');

}
```
The values `400` and `300` pixels are the x and y coordinates of the image
- note: images are automatically placed by theit center, our image is 800x600 pixels. If we didnt add the coordinats we would only see the corner of the image
- hint: you can also use `setOrigin` to change this, change the `anchor` property with the param originX and originY
```js
this.add.image(0, 0, 'sky').setOrigin(0, 0)
```

⚠️ Note: if you put the star image first it will be covered by the sky image, due to the order they are rendered
```js
function create ()
{
    this.add.image(400, 300, 'sky');
    this.add.image(400, 300, 'star');
}
```
### At this point your game should look something like this:
![part 2 example image](/assets/part2.png)

## ➡️ Next steps:
Open up `part3.html` and `part3.md` side by side to start coding



