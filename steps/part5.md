# Part 5: Ready Player One

No we have platforms!.....but no one to run on them

Create a new variable called `player` and add the following code to the `create` function. You can see this in `part5.html`

```js
player = this.physics.add.sprite(100, 450, 'dude');

player.setBounce(0.2);
player.setCollideWorldBounds(true);

this.anims.create({
    key: 'left',
    frames: this.anims.generateFrameNumbers('dude', { start: 0, end: 3 }),
    frameRate: 10,
    repeat: -1
});

this.anims.create({
    key: 'turn',
    frames: [ { key: 'dude', frame: 4 } ],
    frameRate: 20
});

this.anims.create({
    key: 'right',
    frames: this.anims.generateFrameNumbers('dude', { start: 5, end: 8 }),
    frameRate: 10,
    repeat: -1
});
```

There are two separate things going on here: the creation of a Physics Sprite and the creation of some animations that it can use.

### Physics Sprite
This is the first part of the code to create a sprite
```js
player = this.physics.add.sprite(100, 450, 'dude');

player.setBounce(0.2);
player.setCollideWorldBounds(true);
```
This creates a new sprite called `player`, positioned at 100 x 450 pixels from the bottom of the game. 
- The sprite was created via the Physics Game Object Factory (`this.physics.add`) which means it has a Dynamic Physics body by default.

After creating the sprite it is given a slight bounce value of 0.2. 
- This means when it lands after jumping it will bounce ever so slightly.
The sprite is then set to collide with the world bounds. 
- The bounds, by default, are on the outside of the game dimensions. As we set the game to be 800 x 600 then the player won't be able to run outside of this area. It will stop the player from being able to run off the edges of the screen or jump through the top.

### Animations
If you look back at the `preload` function, you'll see a `dude` was loaded as a sprite sheet, NOT AN IMAGE
- it's a sprite sheet since it contains animation frames
This is what the full sprite sheet looks like:

![sprite sheet examples](assets/dude.png)

There are 9 frames in total
- 4 for running left
- 1 for facing the camera
- 4 for running right

Next we'll define two animations called `left` and `right`
```js
this.anims.create({
    key: 'left',
    frames: this.anims.generateFrameNumbers('dude', { start: 0, end: 3 }),
    frameRate: 10,
    repeat: -1
});
```

The 'left' animation uses frames 0, 1, 2 and 3 and runs at 10 frames per second. The 'repeat -1' value tells the animation to loop.

This is our standard run-cycle and we repeat it for running in the opposite direction, using the key 'right' and a final one for 'turn'.

❗️ Extra Info:
In Phaser 3 the Animation Manager is a global system. Animations created within it are globally available to all Game Objects. They share the base animation data while managing their own timelines. This allows you to define a single animation once and apply it to as many Game Objects as you require. This is different to Phaser 2 where animations belonged specifically to the Game Objects they were created on.

## ➡️ Next steps:
Open up `part6.html` and `part6.md` side by side to start coding



