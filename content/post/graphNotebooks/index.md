+++
title = "Fixing Computational Notebooks"
date = 2018-11-16T23:36:15-06:00
draft = false

# Tags and categories
# For example, use `tags = []` for no tags, or the form `tags = ["A Tag", "Another Tag"]` for one or more tags.
tags = []
categories = []

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder. 
[image]
  # Caption (optional)
  caption = "Test"

  # Focal point (optional)
  # Options: Smart, Center, TopLeft, Top, TopRight, Left, Right, BottomLeft, Bottom, BottomRight
  focal_point = "Right"
+++

Recently, I have been working on an extension for VSCode: [VSNotebooks](https://github.com/pavanagrawal123/VSNotebooks). It's basically a way to run code in a Jupyter Kernel from VSCode. I've had had a ton of fun writing this extension, but one thing I realized while working on this extension is: **I don't like notebooks.** 

I could sum up why I don't like notebooks in this post, but I feel like the best reasons I found were in this [*awesome* talk by Joel Grus.](https://www.youtube.com/watch?v=7jiPeIFXb6U)

Whenever I'm working on a cool new project, my usual workflow is to startup a Jupyter notebook and start working there for experimentation and coding. (I understand some people love REPLs for this style of work, but I am not a huge fan of REPls.) What ends up happening is I always lose my flow of execution because:

* I've completely messed up the flow of cells and run things out of order
* I've started editing code in cells but not re-running them
* I make cells that reference a variable in the same cell that mutates itself or mutates based on another changing variables, which causes tons of problems.

Now, I totally understand that most (*if not all*) are really just user issues, but in my opinion finding a way to fix these issues will speed up my workflow infinitely.

## How can we solve this?

Of course, this issue seemed really easy to solve at first: "Why don't I just keep a history of all code execution in my kernel?" This is *a* solution, but not a great one. If this solution were adopted, an end user would need to sift through tons of extra content to figure out the flow of their notebook. The whole point of this endeavor was to make notebooks *easier* and *faster*, so I quickly dropped this solution. 