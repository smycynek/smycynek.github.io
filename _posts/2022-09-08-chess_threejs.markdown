---
layout: post
title:  Chess Puzzles in ThreeJS
date:   2022-09-08 7:30:00 -0400
categories: blog
---
I wanted to get back into some side projects,
so I decided to take another look at my older project "Chess Puzzles 3D."

![Screen shot](/assets/images/chess3d_bw_toggle_border.png)

I was both proud and disappointed in this project.
I wrote the GL code from scratch, including the
shading code, and that was great, but it was a lot of work just to get something that looks like it was from 1996.

I wasn't sure what to do and felt stalled, as I didn't know if I could make the site much better.

One day, though, I was reading about how someone described WebGL as a rasterization library.
Not a graphics library, but a *rasterization library.*

WebGL does Bresenham's line algorithm,
a triangle fill algorithm, and has all sorts of utilities for efficiently loading arrays of data and applying transforms to them in parallel.
It doesn't even do Phong or Gourad shading out of the box -- you need to supply that.  Want matrix utilities to actually create those transforms?  Gotta go find them or implement them.  I'm oversimplifying things a bit -- OpenGL and WebGL are amazing innovations, but it's good to realize what small stepping stones they are relative to the bigger picture.

When you think about it like that, WebGL is a lot like using C rather than assembly, and C is pretty low-level by today's standards.  No one
expects you to write a game to compete with
"The Last of Us, Part 1" in C with no libraries in your spare time.

So, I decided it was time to try out a game engine and work with some power tools.

![Screen shot](/assets/images/chess_puzzles_threeJs.png)

Here's a site I'm a lot happier with.
Shading, animation, mobile support for pinch-zoom/tilt  -- it's a much better experience.

(https://stevenvictor.net/chess3d/?question=What%20move%20by%20white%20shows%20three%20tactics%20at%20once%3F&answer=Os6:%20%20Qvfpbirerq%20nggnpx,%20sbex,%20naq%20qbhoyr%20purpx&data=wKh1,bNf1,wPh2,wPg2,wRh3,wNb3,bBc3,wBh4,bBa4,bPb4,wPc5,bRb5,bPb6,bPa7,bPf7,bKh8&editMode=true)

I used the same "chess3d" url path, so older links now go to the new site.

My next task is to try out mouse and touch support for actually dragging and dropping pieces in 3D.
