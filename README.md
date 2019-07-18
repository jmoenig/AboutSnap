# About Snap!

Snap! is our visual programming language. You code by stacking together graphical blocks rather than typing words. Your program is always alive, ready to be tried, tested and changed as your ideas evolve. Snap! supports imperative, functional and object oriented programming paradigms.

https://www.youtube.com/watch?v=b-EWj7xN90U

Hi all, this is a test.

### Who uses Snap!?

Colleges and high schools use Snap! to teach computer science. Students use Snap! to create games, interactive stories, artwork and simulations, to analyze data, drill down on media, control robots and to invent new forms of expressing themselves.



### The Beauty and Joy of Computing

Snap! has been engineered to support UC Berkeley's introductory computer science curriculum named "<a href="https://bjc.berkeley.edu">The Beauty and Joy of Computing</a>" (BJC).



### What Others Say about Snap!

> "Snap! takes the best ideas, then freshly and coherently synthesizes them into a visual programming language that kids can use, but is also satisfying to professional programmers."<br>
> *-Don Hopkins (The Sims)*

> "I had heard good things about SNAP but never tried it out myself. . . it was a GREAT experience.<br>
> *-Susan Klimczak (Boston South End Technology Center)*

## For Students

## For Educators

### Gradual Introduction

Because Snap! doesn't present the definition of a custom block unless the user manually opens it, educators can teach how to use individual custom blocks - especially control structures and functional techniques like map and reduce - in a gradual way. Initially, let users get experienced with the block as though it were any primitive. Once familiar, share the block's definition and foster discussion on how it works. This helps to prompt ideas of creative ways to use the block, as well as of totally new custom blocks one might like to create.

## For Parents

## For Researchers and Developers



## Snap! Concepts

> "Snap! is Scheme disguised as Scratch"<br>
> *-Snap! co-developer Brian Harvey*

On the outside Snap! looks and feels just like Scratch. But inside it provides expressive concepts for abstraction otherwise only found in the most advanced and sophisticated programming languages from AI research. Snap! supports multiple programming paradigms such as imperative, structured programming, functional programming and object-oriented programming. These make Snap! suitable for an intellectually rigorous introduction to computer science at the college and high school level.



### User Defined Procedures and Functions

Snap!'s tagline is "Build Your Own Blocks". Defining custom functions is at the heart of extending any programming language. It gives you the power to add anything you want to the system. Miss a construct that you like in another programming language? Go ahead and build it in Snap!.

![The Snap! block editor, presenting the definition for the custom block "square of size (side)": "repeat (4): move (side) steps, turn (90) degrees". The editor is an in-UI popup with three buttons: "OK", "Apply", "Cancel".](img/square_block.png)

Any kind of block that you see in Snap! you can also define yourself: Procedures (commands), functions (reporters), predicates ("Boolean inputs") and event listeners (hat blocks). Custom blocks can be defined globally ("for every sprite") or as methods of a single actor ("for this sprite only").

![Another block editor, presenting the definition of the custom reporter block "(a) max (b)": "report (if (a \< b) then (a) else (b))".](img/max.png)



### Proper Tail Recursion

Recursion is a powerful idea in computing because it lets you accomplish huge tasks with only little code. Snap! encourages recursion by making it safe to use even for beginners. Technologies such as tail call optimization (TCO) and a dynamic stack ensure that you don't run out of memory in cases of deep recursion levels, and Snap!'s scaffolded scheduler lets you halt infinite recursion when you forget a base case.

![An example definition: "spiral size (length): if (length) \< 1: stop this block; move (length) steps; turn left 50 degrees; spiral size ((length) - 1)".](img/spiral_block.png)

![The result - a recursive inwards spiral - of running the "spiral" custom block with a fairly large value.](img/spiral.png)

Mastering recursion sets apart the computer scientists from the mere coders. With stack overflows out of the way there's nothing to stop you from inventing beautiful fractals or recursing over large data sets.

![A relatively complex example demonstrating the use of recursion to operate across a list: "index of (item) in (data): report (if (is (data) empty?) then (error (join (item) " not found")) else (if (item 1 of (data) = (item)) then (1) else (1 + (index of (item) in (all but first of (data))))))". Snap! automatically wraps the very wide block-expression at useful points so that it is easier to read.](img/index_of.png)



### Lexically Scoped Variables

In addition to global and sprite-local variables Snap! also offers script-local variables, letting you factor code into reusable modules. As in most modern programming languages Snap!'s variables are lexically scoped and support nested functions and closures. Function parameters are mutable and their value can be exposed to the caller. Snap!'s variables are dynamically typed and support heterogeneous lists.

![An example script (group of arranged, connected Snap! blocks) which makes use of the "map (function literal) over (list)" block twice to create a sort-of times table, where each cell contains the product of the row and column numbers.](img/multiplication_table.png)



### Lambda - First-Class Blocks

Procedures as data is another powerful idea in computing. It allows you to go meta on ideas. In addition to blocks Snap! also features "rings" around blocks transforming expressions into anonymous functions that capture their environment of origin. This lets you build your own blocks that accept other blocks and scripts as inputs, such as C-shaped control structures. You can also store blocks in lists or variables, and even make a block that returns a function (another block).

![The definition for the Y-combinator function, "Y (fn): report {ring (call (fn) with inputs (fn) ())}", and a factorial function defined and called using it: "call (Y {ring input names: fact, num - (if (num = 1) (1) else ((num) * (call (fact) with inputs (fact) ((num) - 1))))}) with inputs (5)". The script returns 120.](img/ycomb.png)



### Higher Order Functions

Snap! comes with built-in blocks that let you map, filter, enumerate and reduce data. Rather than looping over arrays these blocks take other function blocks as arguments enabling highly expressive and declarative constructs.

![A script which abbreviates a longer string into "SNAP": "combine with {ring (join () ())} items of (map {ring (letter (1) of ())} over (keep items such that {ring (length of () > 3)} from (split "Software for Novices and Advanced Programmers" by "(space)")))".](img/acronym.png)

Higher order functions are the superpowers of computing. Snap! provides the ingredients you need to define your own uber-functions. While our pedagogy is that using higher order functions should be easy we also believe that there should be no ceiling to what you can express in a programming language.



### Full Closures

Snap!'s lexical scope supports an inner function to access the local variables of an outer function even after the outer function has terminated. This lets you create abstract data structures from reified dispatch procedures.

![A very lengthy example demonstrating the concepts above; it returns a ring (function) which takes the arguments "msg" and "arg", which are treated as a "command" based on which action is taken. This example shows a ring buffer "object" with three different "methods": peek, get, put.](img/ring_buffer.png)

The idea that temporary local data becomes persistent for a surviving inner function lets us demystify object oriented programming.



### User Defined Control Structures

Control structures are typically what you memorize when you learn a new programming language. Snap! lets you build your own C-shaped blocks to make your own control structures. Being able define program control in your own functions lets you discover how to make a new programming language yourself.

![An example control structure block definition: "for (i) = (start) to (end) by (step) (action): set (i) to (start); repeat until (i > end): run (action), change (i) by (step)". Also an example use of this block: "for (i) = (1) to (12) by (3): say (i) for (0.5) secs".](img/for_loop.png)



### First-Class Continuations

Continuations are an advanced construct giving you access to a part of the evaluator state. Capturing a continuation is like keeping your thumb on a certain page of a book as you close it, so later you can reopen it and continue reading where you left off. Snap!'s continuations let you build certain fancy constrol structures in Snap! itself, rather than having to write them in another programming language:

![The definition for a "catch (tag)" custom control structure block, which is then used to break out of a "forever" loop. The definition follows: "catch (tag) (action): run {ring (set (tag) to (); run (action))} with continuation". The example shows a "forever" block placed inside a "catch (tag)" block, using the block "run (tag)" to break out.](img/catch-throw.png)



### Heterogeneous Data

Data structures are what matters most in a programming language. Data is at the heart of modelling a simulation or a digital twin. Data becomes information by adding structure and context. Snap!'s basic data structures, lists, are first-class citizens. You can assemble complex data structures out of atomic data types (numbers, text, Booleans) and combine them with other lists (lists of lists) and objects. Snap!'s lists are untyped allowing for easy heterogeneous collections of data. This lets you express any data structure you desire.

![Two monitors, labeled "data" and "table". They contain identical values, but present it differently: the "data" monitor shows a 2D list containing items such as "('Boolean', true)" and "('sprite', (the sprite itself presented as an image))"; the "table" monitor presents the same data in a table form, showing the label ("Boolean", "predicate", "sound") etc in the first column, and the values themselves (true, the ringified block "touching (edge)?", and a musical note icon representing a sound) in the second.](img/heterogeneous_data.png)



### Media Computation

Remixing pictures and sounds into interactive animations and video games through programming is hugely fun. But with Snap! we go further, letting you drill down to the bare metal of pixel and sample data to examine, manipulate and transform bits of information into new computational artefacts. Snap! not only lets you perform higher-order functions on low-level media components, it even lets you do so live on the video-feed of your webcam or the audio stream of your microphone.

![A fairly complex script which constantly updates the screen with a version of the sprite's costume (image), modified according to the script. The script posterizes the image into three distinct colors according to a threshold based on the mouse position.](img/posterize.png)

 

![An example result of running the script: a photo of Jens (Snap! co-developer) posterized into dark blue, middle green, and light yellow colors.](img/jens_posterized.png)



### Concurrency

Snap!'s virtual machine can run many scripts for many actors (sprites) at the same time in parallel. Individual programs can be triggered by events, and if several scripts react to the same event they all run concurrently. This lets you model agent-based systems in a decentralized modular way rather than cramming everything into a single main "game loop". Snap! also lets you explicitly launch new threads programmatically, so your procecures can take advantage of parallelism to achieve complex behavior in a logical and expressive way.

![A definition for a block which plays a chord - multiple notes all at once: "play chord (notes) for (beats) beats: if (is (notes) empty) then: rest for (beats) beats; else: launch {ring (play note (item 1 of (notes)) for (beats) beats)}, play chord (all but first of (notes)) for (beats) beats".](img/chord.png)



### Object Oriented Programming

Bundling data structures with behavior is a powerful method to model simulations and design user interfaces. Snap!'s sprites are first-class objects. They can be directly referenced, assigned to variables and passed into functions. Sprites can have local fields ("instance variables") and custom blocks ("methods"). Objects  communicate with each other either through public "broadcasts" or through direct polymorphic messages.

Sprites can inherit local state and behavior from another. Rather than through classical inheritance Snap! supports a concrete prototypical, Lieberman-style inheritance mechanism through delegation, similar to JavaScript and SELF.

![An example script demonstrating creating a "clone" of an original sprite, which is assigned to inherit the y-position of the sprite; as the original sprite moves in a circle, the clone continually moves right (while inheriting the y-position). This results in the clone drawing a sine wave. There are two scripts - the first: "when flag clicked: create a clone of myself, forever: move 2 steps, turn 2 degrees"; the second: "when I start as a clone: inherit (y position); pen down; repeat until (touching (edge)): change x by (1); stop (all)".](img/sine-curve.png)

![The result of running the above example: a black sine wave drawn on the stage (project screen), and the sprite and its clone in their final positions.](img/sine_wave.png)

Objects can be composed into aggregations by nesting sprites into part-whole relationships. This lets you easily create virtual puppets and robots.



### Debugging

Snap! supports debugging through a variety of data monitoring widgets, and by allowing visible "slow-mo" and single stepping. Because Snap's programs are always "live" debugging is achieved by inspecting the actual programming as it is running instead of a post-mortem stack trace.

![The menu bar where the execution of a Snap! project is controlled. There is a pressed button with a footsteps icon and a slider beside it (set half-way), signifying the project to execute at a considerably slower speed.](img/controls.png)

![When the "slow-mo" (or single stepping) slider is set, the block which is currently executing is highlighted in a bright cyan-green color. In an example script, the "square of size (i)" block is highlighted. The entire script itself is also glowing, showing that it is actively running.](img/visible_stepping.png)



### Extensions

Write your own JavaScript extensions.

Web APIs, Frequency Distribution Analysis, Infinite Precision Numbers, Text-to-Speech, World Map, JSON, CSV, etc. etc.

![The stage of a program demonstrating a "world map" JavaScript extension, pin-pointing two characters on a 2D map of the Western Hemisphere; one of them (a character named Alonzo) says the real-world distance to the other (a Logo-style turtle sprite): "9262 km to Brian".](img/maps.png)
