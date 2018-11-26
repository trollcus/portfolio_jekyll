---
layout: post
title:  "The Last Day at Work"
date:   2016-10-26 14:16:49 +0200
year: 2018
month: 04
day: 13
meta: "Creating game from scratch"
description: "Creating a new game for the course 'Games and Play' at Malmö University"
pageurl: "https://youtu.be/DVEXzfAYacM"
categories: cases cases-featured
category: School
image: "gamesnplay/gamesnplay.jpg"
---
<h2>
<a href="https://youtu.be/DVEXzfAYacM" style="text-decoration:underline;">Final artefact</a>
</h2>
<br>
<h3>Introduction</h3>
Writing this is a couple of months after completing this project. I will try to remember each process the best I can but this text might be updated in the future if I find more documentation.

For our course <a href="https://edu.mau.se/sv/Course/KD410A">Games and Play</a> we were told to create a game. The game had to have some kind of digital element implemented and we were all told to create a concept. Erik, one from our group, introduced the concept of walking within a digital environment with the help of pure sound to the class. I was immediately hooked and wanted to join. In total we were five people on the project and started out our journey.

__Tools used:__ Arduino, Johnny Five, NodeJS server, JS, HTML, CSS

<h3>Concept development and testing</h3>
We started brainstorming around the concept of walking through digital space with sound. We wanted to implement gameplay that was recognizable in order to save time and have some kind of structure ready. We knew that development time could be large so we wanted to ensure that we would make everything on schedule.

<video id="video" controls autoplay muted loop width="100%" height="100%">
  <source src="https://media.giphy.com/media/vRJXwtb6Jjl0gqEjot/giphy.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video><br>
<p class="imgDesc">First Concept</p>

<img src="{{site.baseurl}}/images/gamesnplay/shoes.jpg" alt="Materials" class="img-full"/>
<p class="imgDesc">Pressure sensitive shoes</p>

Instead of using digital rooms and pure sound as it was to confusing while testing we started to try out a whack-a-mole type of gameplay. We put out tape on the floor and started playing sounds to see if you could figure out which square was which while trying to stomp on it.


<video id="video" controls autoplay muted loop width="100%" height="100%">
  <source src="https://media.giphy.com/media/1xVfKO6O7Hjd0S1ath/giphy.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video><br>

We tried out multiple different amount of squares (9x9, 4x4 etc) in combination of trying to figure out and remembering which sound belonged to which square. These sounds were determined by a Gamemaster who supervised each game.

<img src="{{site.baseurl}}/images/gamesnplay/gamemaster.jpg" alt="Gamemaster controlling sounds" class="img-full"/>
<p class="imgDesc">Gamemaster controlling sounds</p>

We started to have some kind of breakthrough while at the same time it was hard to remember which sound was which. However we ran out of time and it was time to present what we had at the time and get some consulting of how we should proceed.
Our mentors liked our progress but felt that we needed a more solid gameplay experience. The term Gamify was used frequently. We started doing even more research based on our ideas and tried to transform the ideas into something that was more like we had from the beginning. We wanted the game to be immersive and something that could be set up in a museum environment.

<h3>Material</h3>
From the beginning there was pressure sensors in the shoes. This was transformed into stepping plates. The plates would be controlled via Arduino with wires connected to them. The plates would have conductive tape on each side. When stepped on the circuit would be closed which then tells the Arduino that it was active - basically a very big button. Simple mechanics that actually worked wonders. However we needed it to feel right. It had to have THE feeling that made you feel satisfied and immersed when stepping on it.
<video id="video" controls autoplay muted loop width="100%" height="100%">
  <source src="https://media.giphy.com/media/WxTOcUaZlEgeKO4jlx/giphy.mp4" type="video/mp4">
  Your browser does not support the video tag.
</video><br>
<img src="{{site.baseurl}}/images/gamesnplay/material.jpg" alt="Materials" class="img-full"/>
<p class="imgDesc">Trying out array of materials</p>

Our plates were developed over a span of two weeks of just iterating the different prototypes. Testing with users combined with the software development (More on that later) they were transformed from one day to another.

<h4>Breakthrough</h4>
The plates were quite sensitive and could break anytime. Often because of the cables got loose from the plates. One day when doing testing, one of the plates broke down and Elias started putting together the cables by hand instead in order to continue testing the game and this was a revelation. It introduced a new interaction in order to close the circuit. It looked like he was trying to run around and fix things and it drew parallels to fixing something old that was breaking down. We tried to put the tester in an immersive environment with the help of different sounds (More on feedback and sound later) and we landed in the concept of using an old and broken down factory.

<h3>Software</h3>
During this project I was the one who took charge of software development. We started using native Arduino code but we knew that we wanted to extend this to a digital screen as well. This meant creating a bridge between the Arduino and a Node server. Luckily there is some great libraries for this. We started using <a href="http://johnny-five.io/">Johnny five</a> which bridged our gap between the two.
The main problems we had during development were:
- The plates feedback frequency were so high and glitchy which ended up breaking of our Arduinos. Our fix was when we got a hold of a stronger Arduino.
- The same as above on the software side though. It flooded the websockets with information. After a lot of problem solving we managed to throttle the data while still getting an even stream of data which was manageable.
- Game logic. There were A LOT(A LOT) of moving parts with different timers. Managing state of the game was a b#&ch using native Javascript. We nailed it down in the end though.

This resulted in many thousand lines of code. The repo can be found <a href="https://github.com/trollcus/gamesnplay_project/tree/new-dev" style="text-decoration:underline;">Here.</a> Keep in mind that I have not had the time to clean up the code. It is a bit rough right now but readable.

<h3>Game concept.</h3>
The best explanation and final result is best showed in this <a href="https://youtu.be/DVEXzfAYacM" style="text-decoration:underline;">video.</a> However, in the next section I will finish of by talking about feedback, sounds and final thoughts as well.

<h4>Feedback and sounds</h4>
When the game started looking like the final product we struggled with feedback from the game itself. The feedback in this context means sounds resulting in the user feeling that they are making progress. When researching the subject we happened to come across <a href="https://youtu.be/Fy0aCDmgnxg">Juicy feedback</a>. Juicy feedback helped us adding satifactory sounds to the game when increasing tempo, scoring points and other game sounds.

While using Juicy feedback sounds for those kinds of interaction we also needed sounds for each of the machines and for the boss. Erik managed to pull of his angry voice in order to act as the boss. The rest of the sounds were created by us which can be heard in the gameplay video.
