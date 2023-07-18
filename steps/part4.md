# Part 4: The Platforms

So we just added a bunch of code to our `create` function and it deserves more explanation

```js
platforms = this.physics.add.staticGroup();
```
This creates a new Static Physics group and assigns it to the local variable `platforms`

There are two types of physics bodies:
- Dynamic: oone that can move around via forces such as velocity or acceleration. It can bounce and collide with other objects and that collision is influenced by the mass of the body and other elements.
- Static: has a position and a size. It isn't touched by gravity, you cannot set velocity on it and when something collides with it, it never moves. Static by name, static by nature.

Perfect for the ground and platforms that we're going to let the player run around on.

### What is a Group?
As their name implies they are ways for you to group together similar objects and control them all as one single unit. You can also check for collision between Groups and other game objects. 

Groups are capable of creating their own Game Objects via handy helper functions like create. A Physics Group will automatically `create` physics enabled children, saving you some leg-work in the process.

With our platform Group made we can now use it to create the platforms:

```js
platforms.create(400, 568, 'ground').setScale(2).refreshBody();
platforms.create(600, 400, 'ground');
platforms.create(50, 250, 'ground');
platforms.create(750, 220, 'ground');
```
During our preload we imported a 'ground' image. It's a simple green rectangle, 400 x 32 pixels in size and will serve for our basic plaform needs:

![part 4 ground image example](../assets/platform.png)

The first line of code above adds a new ground image at 400 x 568 (remember, images are positioned based on their center) 
-  problem is that we need this platform to span the full width of our game, otherwise the player will just drop off the side

To do that we scale it x2 with the function `setScale(2)`. It's now 800 x 64 in size, which is perfect for our needs. The call to `refreshBody()` is required because we have scaled a static physics body, so we have to tell the physics world about the changes we made.

The ground is scaled and in place, so it's time for the other platforms:

```js
platforms.create(600, 400, 'ground');
platforms.create(50, 250, 'ground');
platforms.create(750, 220, 'ground');
```

We don't need to scale these platforms as they are the right size already

3 platforms are placed around the screen, the right distances apart to allow the player to leap up to them.

In the next tutorial we'll add our player!

## ➡️ Next steps:
Open up [part5.html](/part5.html) and [part5.md](part5.md) side by side to start coding



