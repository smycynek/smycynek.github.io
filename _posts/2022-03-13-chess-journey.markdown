---
layout: post
title:  Chess Journey
date:   2022-02-08 20:00:00 -0400
categories: blog
---

A lot has happened in the last month.  I recently gave a talk at work about finding your passion in side projects to hone skills -- using chess as an example.  Some of the
themes of the talk were around working in areas you weren't comfortable with and cutting yourself some slack when trying to grow.

I needed to take some of my own advice with some new enhancements to chess-puzzles 2D and 3D.  Adding rank and file annotations to the 3D
site was the first challenge.  I could use textures or decals for
letters and numbers, but I'm not set up to do that currently.  I could
have individual meshes for each letter and number, but modeling each of
those and placing them in 3D space along the borders of the board was
tedious.  So, I created a board frame with the letters and numbers carved in.  It's not perfect, but it works all right for now, and
is a lot simpler, so I settled on that.

![Screen shot](/assets/images/chess3d_bw_toggle_border.png)

In the older 2D editor, things were trickier.  A lot of the code made
some assumptions about the layout of the board, and so flipping things
wasn't quite as simple as rotating 180 degrees or iterating in reverse.

In particular, I probably should have had some sort of mapping that allowed me to address squares with a 1D or 2D indexing system independent of rank and file so that it would be clearer if I was addressing square "a1" or the square "64" or [7][7] in the lower-right-corner.

So, I put in some code that flips the ranks and files around a bit, and
the end result looks fine and makes total sense to the user, but I don't like the idea of converting file "a" to file "h" internally.
Still, I thought it was better to just try it out in a branch.

I think I'll continue to add functionality to the 2D and 3D sites
incrementally, and once I feel like I've added enough, I'll either
do a major refactor of both sides or redo them in a new framework, like
three-js or Unity.

![Screen shot](/assets/images/chess_bw_toggle.png)

There's so much more I want to do with WebGL and geometry that goes beyond the chess apps, though, so I may need to do some other projects
and come back to this -- we'll see.