# Part 9: A score to Settle

There are two final touches we're going to add to our game
-  an enemy to avoid that can kill the player
- a score when you collect the stars.

### First a score...
To do this we'll make use of a Text Game Object. Here we create two new variables, one to hold the actual score and the text object itself:
```js
var score = 0;
var scoreText;
```

The `scoreText` is set-up in the `create` function:
```
scoreText = this.add.text(16, 16, 'score: 0', { fontSize: '32px', fill: '#000' });
```

16 x 16 is the coordinate to display the text at. 'score: 0' is the default string to display and the object that follows contains a font size and fill color. By not specifying which font we'll actually use the Phaser default, which is Courier.

Next we need to modify the `collectStar` function so that when the player picks-up a star their score increases and the text is updated to reflect this:

```js
function collectStar (player, star)
{
    star.disableBody(true, true);

    score += 10;
    scoreText.setText('Score: ' + score);
}
```
So 10 points are added for every star and the `scoreText` is updated to show this new total.


![part nine scene example](assets/part9.png)

In the final part we'll add some enemies.
## ➡️ Next steps:
Open up `part10.html` and `part10.md` side by side to start coding



