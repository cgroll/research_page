This repository presents some of my research findings. You can view
the github hosted notes
[here](http://cgroll.github.io/research_page/index.html).

# Structure

Individual research projects reside as git subtrees of the gh-pages
branch of this repository, as pictures and any other parts of the
wegpage must be accessible from within the repository. This would not
be the case for submodules.

Each individual project subtree should be equipped with an individual
Makefile, which allows automatic (re-)generating of all results.
