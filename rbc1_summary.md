# Cambridge R Bootcamp 2014-01-07

[Bootcamp homepage](http://sje30.github.io/2014-01-07-cam)
[Course material](http://github.com/lgatto/rbc)

Judging from the post-course questionnaire responses, our first R
bootcamp in Cambridge (7/8 January 2014) was a great success.  We had
24 participants (and many on a waiting list) eager to learn how to
program in R and work with essential tools such as git and make.  Our
main prerequisite for participants was that they should already be
familiar with programming in another environment.

# Positive points about the course

We used github to host all of our material, i.e. code, data and notes.
Our notes were primarily markdown documents (sometimes generated from
[R markdown](http://www.rstudio.com/ide/docs/authoring/using_markdown)
source files).  At the start of the course we did not explicitly
explain why we were using github.com to render our notes.  However,
during the course as the participants learnt about R, version control,
markdown, and packaging, it became clearer, and we believe it was a
good decision to use R markdown.

We set the participants an ambitious goal for the bootcamp: to write
their own R package to generate plots from the
[Cambridge weather](http://www.cl.cam.ac.uk/research/dtg/weather/)
dataset.  As these data are fairly easy to understand, the
participants could focus on the computing task, rather than needing
first to understand the data.

Most of the material had been previously taught in other courses (or
bootcamps) meaning that there were relatively few problems with the
material.

# Negative points about the course

We had too much material for two days.  Some exercises were skipped,
and perhaps we could have spent more time on exercises rather than
presenting material.

Participants brought their own laptops to work on. The main (and
unsolved) problems were that we could not get Make/git to work in
Cygwin/Git bash on some machines.  In the future, we will recommend
Unix-based systems to participants and possibly also provide a linux
virtual machine image with pre-installed software.

It was difficult for participants to initially make the connection
between what we were typing and the corresponding notes in the
markdown files on github.  This was partially solved by using a second
data projector to show the notes.

# Will we do it again?

Probably!  Some of the material could be reworked (or omitted) to
allow for better flow.  We will investigate links with other
[R material](https://github.com/swcarpentry/bc/pull/112) in Software
Carpentry.

Two of us (SJE, LG) feel that although we need to teach version
control, Git is too complex for new users.  Starting with something
simple like RCS might be more appropriate, and could naturally flow
from working with the diff/patch shell tools.

# Acknowledgements

Robert Stojnic and Devasena Inupakutika were helpers throughout the
bootcamp.  Thanks to the [Cambridge Computational Biology
Institute](http://www.ccbi.cam.ac.uk) and the [Centre for Mathematical
Sciences](http://www.cms.cam.ac.uk) for hosting the bootcamp.
