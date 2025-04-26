# Static analysis tools
The goal of this post is to help me process and put down in words my thoughts
on the use of static analysis and other development tools (linters, LSPs, type
checkers, etc).

I have found that I am currently making poor use of such tools in my
development practice. Interestingly, rather than under-using them, I think I
might be over-using them. I have started to feel like the constant feedback is
creating noise in my workflow and interrupting my train of thought, focusing
more on making the warnings go away rather than on design and problem-solving.

# Seperation of concerns
My main idea, inspired by this article on [Google's experience building their
own static analysis tools](https://cacm.acm.org/research/lessons-from-building-static-analysis-tools-at-google/)),
is to integrate feedback into my workflow at the precise moment where it will
bring the most benefit and generate the least amount of disruption.

## Cognitive overload and short-term memory
It is often said that [we can hold about 5 objects in our short-term memory,
give or take 2](https://en.wikipedia.org/wiki/The_Magical_Number_Seven%2C_Plus_or_Minus_Two).
Whether this comes from sound research or not, I think most of us can agree
that the number of concepts or tasks we can focus on at once is quite limited.
It thus makes sense to seek to hide superfluous information from our view when
it is not needed for the task at hand.

## Stages
I have three stages in mind:
- In-editor analysis
- Compile-time analysis
- Commit-time analysis

## In-editor analysis
This is where we receive the fastest feedback, but are also the most susceptible
to disruption and noise. I think it is useful to envision the different scenarios
that find us working in our editor, and the state of mind we are in.

When in our editor, we are usually either writing or reading code, and are
usually engaged in _exploration_, _creation_, or _problem-solving_.

### Exploration
#### Creative Exploration
Often, we just want to bang out some code and see what happens. Maybe we have
an idea in our head we want to explore, using the editor as one would a
whiteboard. We might have a quick hypothesis we want to test. Or we could be
exploring the features of our language, writing a couple of words and seeing
what our editor's auto-completion and documentation features present to us.
When in this mode, we are feeding our creativity, getting an idea of what is
possible and what we want to do.

In this mode, we want our tools to be as helpful and unobstructive as possible.
We don't care about bugs or correctness or formatting; not at this point. Our
tools should be there to help us discover functionality and stay out of the way
so we can test our ideas as quickly as possible. It might even be useful to
be able to run our compiler with all checks and warnings disabled so we can
focus on writing down a small piece of code and seeing what it does.

Useful:
- Auto-completion
- In-editor documentation
- Code suggestion
- A "Run" button or function so we can try our code without leaving the editor.
- An in-editor debugger so we can go through our program and look at our data
without leaving the editor.
- Warnings to let us know our code will not compile and/or run (with the caveat
that those can turn into noise while we're in the middle of writing an incomplete
segment of code).
- Warnings about features our coding guidelines prohibit (functions that are
inherently unsafe like _gets()_ for instance).

#### Learning Exploration
At other times, we are reading someone else's code and trying to understand it.
In

# References
- [](https://cacm.acm.org/research/lessons-from-building-static-analysis-tools-at-google/)
