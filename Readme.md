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

# Considerations

### Proprietary data

- must reside in private repository
- if data is downloaded, download script should be included together
  with access time of the data and software version next to the data
  itself
- analysis of raw data and filtering code must reside in public
  repository in order to include pictures in webpage repository

### Subtrees vs symbolic links

- subtrees will keep separate copy of all pictures and hence bloat the
  repository 
- with symbolic links subfolder project pictures would not be
  accessible by homepage
- subtrees reference some given state of graphics?! 

### Jupyter notebooks vs .jl files

- Jupyter notebooks for first data analysis
- scripts should basically only export graphics that shall be kept for
  the analysis

