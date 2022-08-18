This is where comments are going for code unrelated.
```
function animate(){
    ctx.clearRect(0, 0, CANVAS_WIDTH, CANVAS_HEIGHT);
    let position = math.floor(gameFrame/staggerFrames) % 6; // 6 is because the idle animation has 6 frames
    frameX = spriteWidth * position;
    // ctx.fillRect(50,50,100,100); This fills a square
    // ctx.drawImage(image, sx, sy, sw, sh, dx, dy, dw, dh); S = source and D = destination
    ctx.drawImage(playerImage, frameX, frameY * spriteHeight, spriteWidth, spriteHeight, 0, 0, spriteWidth, spriteHeight);

    // this is the simpler way of changing the frames however this will require more code between different positions.
    // if (gameFrame % staggerFrames == 0){
    //     if (frameX < 6) frameX++;
    //     else frameX = 0;
    // }
    

    gameFrame++;
    requestAnimationFrame(animate);
};
```