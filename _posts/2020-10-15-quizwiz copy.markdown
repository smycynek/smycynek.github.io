---
layout: post
title:  Quiz Wiz -- A Model for Learning
date:   2020-10-15 01:56:31 -0400
categories: blog
---

I started working on big, 10-million line source-code bases in C++, COM, C++/CLI, and C#
right out of college.  Almost everything I did was a custom class with seven layers of multiple implementation inheritance that did linear algebra and other math or data structures for CAD/CAM applications.

After many, *many* years of that, I needed a change, so a couple of years ago, I took a chance and
got a new job building modern web apps.  The company hired me because I was "scrappy" and "curious", not experienced.  SQL, Python, REST, JavaScript, ORMs -- I had an intern-level of exposure to them when I started. The job certainly took me down a peg or two or three, but it was a great personal growth experience--at first.

#### New Job != Automatic New Growth

I had done Django and React all day for a year or so at the new job, but I found that when you work on code with a team, especially as the project grows, you spend less time learning and developing original code, ideas, and architecture, and more time matching the style, architecture, component choices, and general decision making of the existing codebase.  To a degree, there's nothing wrong with that -- it's part of the job, part of teamwork, and that's life.  However, I was still surprised how quickly this learning slowdown happens, even on a relatively small, new product, especially if you are a beginner.  I was frustrated that my learning and growth slowed so soon after starting my new job, and I needed a way to get back on track so I could keep contributing to the team.  I found that the only way to keep learning was to build small side-projects on my own.

So:

<https://stevenvictor.net/unitcircle/>

<https://stevenvictor.net/area_under_curve/>

<https://stevenvictor.net/mortgage/>

As much as I love these apps, they are still pretty simple, and I sometimes feel a little embarrassed that someone my age is still implementing things at this level of complexity.  I couldn't let my pride get in the way of growth, though.  I was done with COM interop and C++ class factories -- time for something new, starting at the bottom.

#### A Model for Learning

In the middle of all of this, I did a talk at work called "Learn React by Annoying your Spouse."  :)
The idea is to find a very small project you are passionate about, play up the inside-joke appeal
with the project content, and to use your family and non-work friends to get feedback.  If the site is fun and silly and simple, people will be willing to try it out on their various phones and tablets, and you get very honest feedback about usability quickly.  The project should be large enough to be challenging and more than the endless, uninspired parade of "to-do list" tutorials you find online, but still achievable without too much frustration.  Basically,
get outside your comfort zone by 10-20%. <https://www.sciencedaily.com/releases/2019/11/191105113457.htm>

My extended family
liked the mortgage app from above, so I knew I was on to something.  I wanted more feedback, though,
so I needed something fun and engaging.  My wife's family is from India, so I came up with
<https://www.stevenvictor.net/bollywood/>, which eventually morphed into Quiz Wiz, my next
big challenge to try out redux and sagas and return to back-end work.

#### Quiz Wiz

<https://stevenvictor.net/quizwiz/>

Quiz Wiz is a full-stack project:  Django REST Framework, Postgres, deployment to Heroku, React Front End, Bootstrap and CSS, published React NPM component, Webpack, -- all of it.

I ended up building several repos:

* Back-end <https://github.com/smycynek/quizfreak>
* Front-end quiz taking component <https://github.com/smycynek/react-casual-quiz>
* Front-end quiz main site and authoring environment: <https://github.com/smycynek/quizwiz>

I made a few design decisions to keep things simple:

* Make quizzes immutable once published to prevent others from messing with them.
* No login, but allow the users to make quizzes 'unlisted.' (I might have to change this, we'll see.)
Disable PUT, PATCH, and DELETE on the server-side.
* Keep the quiz 'casual', in that the first choice in each question increments a subtotal that will
steer the end result to the first personality type, etc. I might offer a 'scramble choices' feature in the future.
* Don't worry about saving results.
* Implement the 'random quiz' feature on the server -- don't make the client pick one from a list at random.
* No front-end for admin features -- just use the Django admin tool.
* No pagination or JSON-API/HATEOAS for now.
* Better to go live and get feedback and risk embarrassment than never deploy anything.

Obviously, there are bugs and flaws, and I can only work on this in the little free time I have.

So, my model for learning is to do things independently and from scratch (using framework and libraries obviously), and pick small, fun projects people will want to try out quickly.  All of the skills I pick
up get rolled back into my day job.

As Marsellus Wallace said -- "Forget pride, build small Django and React Apps." Don't get me wrong -- I won't quit my day job.
