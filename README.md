#Pyhoc
###The magic disappearing prompt

Under the [GPL v3](http://www.gnu.org/licenses/gpl-3.0.html)

If you're anything like me, your terminal gets filled with

    /projects/this/project/ $ command
    /projects/this/project/ $ command
    /projects/this/project/ $ command
    /projects/this/project/ $ command
    /projects/this/project/ $ command
    /projects/this/project/ $ command
    /projects/this/project/ $ command

It sort of makes using a small terminal or multiple panes hard to do because
your prompt might end up taking most of the screen space just writing things
you already know. I know where I am terminal! I've been here two hours! Also, I
think I know my name, and the computer I'm logged on to.

Wanting to preserve the beauty of a clean terminal, free of superfluous output,
I made a magic prompt, built in Python, so when you do

    me@my_computer /projects/this/project $ command

your next prompt is

    $

And should you change directory:

    $ cd foo
    /projects/this/project/foo $

Then when you get to work:

    /projects/this/project/foo $ command
    $

Pyhoc will display the information you tell it to when there's something new to
say.

To install, place `pyhoc` in `~/bin/`. Then have your shell's rc file run it in
its PS1 variable.

    PS1='$(pyhoc "%l%d")%#'

zsh users remember to turn on prompt_subst.


Formatting options:

`%l` will return the traditional `user@computer `, with a trailing space so
anything after it does not get truncated to it.

`%u` will return your user name, with a trailing space so anything after it
does not get truncated to it.

`%c` will return your computer's name, with a trailing space so anything after
it does not get truncated to it.

`%d` will return your current working directory, with a trailing space so
anything after it does not get truncated to it.
