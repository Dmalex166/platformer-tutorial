# Part 7: Controlling the player with the keyboard

Now that we've got the collider working, we need the player to move. If you're familiar with javascript in yur HTML projects you might think of heading to the documentation and searching about how to add an event listener, but that is not necessary here. Phaser has a built-in Keyboard manager and one of the benefits of using that is this handy little function:
```js
cursors = this.input.keyboard.createCursorKeys();
```

This populates the cursors object with four properties: up, down, left, right, that are all instances of Key objects. Then all we need to do is poll these in our `update` loop:
```js
if (cursors.left.isDown)
{
    player.setVelocityX(-160);

    player.anims.play('left', true);
}
else if (cursors.right.isDown)
{
    player.setVelocityX(160);

    player.anims.play('right', true);
}
else
{
    player.setVelocityX(0);

    player.anims.play('turn');
}

if (cursors.up.isDown && player.body.touching.down)
{
    player.setVelocityY(-330);
}
```
We've just added a lot of code, but it should be very readable.

The first thing it does is check to see if the left key is being held down. 
- If it is we apply a negative horizontal velocity and start the 'left' running animation. 
- If they are holding down 'right' instead we literally do the opposite. 

By clearing the velocity and setting it in this manner, every frame, it creates a 'stop-start' style of movement.

The player sprite will move only when a key is held down and stop immediately they are not. Phaser also allows you to create more complex motions, with momentum and acceleration, but this gives us the effect we need for this game. 
- The final part of the key check sets the animation to 'turn' and zero the horizontal velocity if no key is held down.

### Jump to it
 Now we're going to add the ability to jump.

 First we test.....
 - If the up cursor (our jump button) is down/clicked
 - If our player in on the ground (otherwise our player could jump mid-air)

 If both of these condition are met.....
 - We map apply a vertical velocity of 330px/sec

The player will fall to the ground automatically because of gravity. With the controls in place we now have a game world we can explore. Load up part7.html and have a play.

❗️Hint: Try tweaking the 330 value lower and higher to see it's effect

![part seven scene example](../assets/part7.png)


 
## ➡️ Next steps:
Open up [part8.html](/part8.html) and [part8.md](part8.md)` side by side to start coding



