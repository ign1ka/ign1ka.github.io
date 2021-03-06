# Game Development Portfolio

## Project List:
- [1. Post Reality](#1-post-reality)
- [2. Dejarik](#2-dejarik)
- [3. Sabacc](#3-sabacc)

## In-Progress Projects:
- [1. Senior Thesis](#1-senior-thesis)

## Projects

### 1. Post Reality

Post Reality, a subsidiary of The Glimpse Group, is an augmented reality-centric company based in New York City, NY. Post Reality's flagship app, also named Post Reality, allows users to create and share presentations in augmented reality. Through the app, users can view these experiences using a number of methods. During the summer of 2021, I worked at Post Reality as a Software Development/Quality Assurance Intern. Over the course of my internship, our team rebuilt the Post Reality app from scratch in Unity 3D and successfully released it on both the Apple App Store and the Google Play Store.

While working this internship, I was involved with the Post Realty app’s development from conception to release. The following video portrays the particular feature I developed: easel object placement in augmented reality. Though the Post Reality team has iterated on the easel model and tap to place indicator since my internship ended, my original implementation resembles this current version in most regards. Furthermore, I was also responsible for developing easel movement and rotation features, which remain unchanged from my implementation and can be seen in action in the video.

{% include youtubePlayer.html id="dusOd25-WxQ" %}


Due to the nature of my internship at Post Reality, all the development work I did for the app is proprietary and I am therefore unable to display the code associated with the above video.

### 2. Dejarik

Dejarik, based on the hologram chess game of the same name played on the Millenium Falcon in Star Wars Episode IV: A New Hope, is a 2D, two-player board game made for MacOS, iPadOS, and iOS devices. I developed this game in Unity 3D with C# over my winter break following the Fall 2021 semester. There are four classes of pieces, each with different possible move and attack patterns. Since I am unable to publish this app to the Apple App Store due to copyright concerns, I have included a video below to display the game's functionality. 

{% include youtubePlayer.html id="F0eu2eKCP3c" %}


An interesting problem I ran into while developing this game stemmed from the design of its board. Since the board is circular, I was unable to use the standard (X, Y) coordinate system used by other digital chess games. To combat this issue, I created a coordinate system for the board based on 2 “orbits” (designating the inner and outer circles) and 12 “rays” (designating the 12 spaces within each orbit). I defined each orbit using the radii of its outer and inner borders and each ray using the angles its left and right borders made with the positive horizontal axis.

Though this was an effective coordinate system, it resulted in another complication that needed resolution. Again due to the circular nature of the board, the spaces (1, 1) and (2, 1) are adjacent to the spaces (1, 12) and (2, 12). Therefore, unlike similar 2D Unity chess games, I was unable to simply increment or decrement a given piece’s position to move it. For example, incrementing (1, 12) would result in the piece moving to (1, 13) (a space which doesn’t exist) instead of (1, 1). To solve this problem, I implemented a NormalizeCoordinates() function that takes an (orbit, ray) coordinate pair and, if the ray value is larger than 12 or less than 0, returns the correct coordinate pair. In this way, NormalizeCoordinates(1, 14) returns (1, 2). This can be seen in the above video when pieces move across the leftward-facing horizontal. With these structures in place, I was able to move on to implementing the primary game loop.

The game makes use of three seperate C# scripts: Game.cs, MovePlate.cs, and Piece.cs. These scripts can be viewed here: [Dejarik Code Samples](https://github.com/trippahive/Dejarik2D-Code-Samples)

### 3. Sabacc

This game, based on the card game of the same name shown in Solo: A Star Wars Story, is a text-based equivalent to the in-universe game. I developed the game using Python. Somewhat analogous to the real world game of blackjack, my version of the game follows the rules outlined in the version of the game available at Disney’s Star Wars: Galaxy’s edge. The game simulates one three-turn round of Sabacc, allowing the player to compete with between one and seven NPCs. The video below displays the functionality of the game.

{% include youtubePlayer.html id="pczRfDRx3jk" %}

The game makes use of two seperate Python scripts: CorrelianSpike.py and Play_CorrelianSpike.py. These scripts can be viewed here: [Sabacc Code Samples](https://github.com/trippahive/PythonSabacc)

I am currently in the process of using the logic in this game to develop a 3D protoype version in Unity. I hope to use the experience of doing so to further build upon my Unity skills and gain familiarity with using Blender to create and apply textures to 3D models.

## In-Progress Projects

### 1. Senior Thesis
### _Orbital Visualization in VR_

The Physics & Astronomy department at Pomona College requires students to submit a senior thesis before graduation. My senior thesis project involves visualizing Near-Earth Object (NEO) orbits in virtual reality.

NEOs are defined as any small Solar System body whose orbit brings it into proximity with Earth. The Pomona Physics & Astronomy department is working on a joint project with NASA’s Jet Propulsion Laboratory (JPL) to observe, image, and track both previously discovered and currently unknown NEOs. Using a remote observatory, Pomona student observers record data on these NEOs, which is then sent to NASA for review and cataloging. 

For my senior thesis, I am developing a Unity project to visualize these orbits relative to a model Solar System in VR. So far I have implemented a simple orbital mechanic that allows GameObjects to orbit around a defined point, taking into account values for eccentricity and semi-major axis. The video below displays this script running in the Unity Editor, rotating a small sphere around another larger sphere.

{% include youtubePlayer.html id="Gr1WD_JesUg" %}


The associated script, Orbit.cs, can be viewed here: [Thesis Scripts](https://github.com/trippahive/Senior-Thesis)

I am further developing this project by implementing Newton’s laws of gravitation, allowing instantiated GameObjects to dynamically orbit without following a pre-defined path. This will also take velocity into account. From here, I plan to implement VR functionality, including zoom, translation, and rotation controls.
