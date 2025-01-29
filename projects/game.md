---
layout: project
type: project
image: img/vacay/vacay-square.png
title: "Dodge Em"
date: 2020
published: true
labels:
  - HTML
  - CSS
  - JavaScript
  - GitHub
summary: "A simple JavaScript game that was created in my highschool coding class."
---

<img class="img-fluid" src="../img/dodge_em.png">
Dodge Em is a browser-based game built using HTML, CSS, and JavaScript. It is an arcade-style survival game where the goal is to last as long as possible. The inspiration for this game comes from many of the classic games I enjoyed as a child.

Through this project, I gained hands-on experience in using HTML, CSS, and JavaScript for game development. However, I encountered several challenges along the way. One major issue was working with raw JavaScript without TypeScript, which led to unpredictable behavior. For example, the game exhibited an unusual problem where it would run correctly on some computers but not on others.

Here is some example code to create the objects in the game:
```js
function draw() {
    clear();
    player.show();
    player.update();
    //pillar 1
    pillar.show();
    pillar.update();
    pillar.collide(player);
    //pillar 2
    pillar2.show();
    pillar2.update();
    pillar2.collide(player);
    //pillar 3
    pillar3.show();
    pillar3.update();
    pillar3.collide(player);
    //pillar 4
    pillar4.show();
    pillar4.update();
    pillar4.collide(player);
    //pillar 5
    pillar5.show();
    pillar5.update();
    pillar5.collide(player);
    timer = (millis()/1000).toFixed()
    if (millis() >= 1 + timer){
        timer =  millis()
        document.getElementById('score').innerHTML = (timer/1000).toFixed() + " seconds"
    }
}
```
 
Game: <a href="https://masonl04.github.io/index.html">Dodge Em</a>
