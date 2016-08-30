#Writing Workflow

I am writing the text in Pandoc Markdown in Scrivener set to use Courier 12 font. Using this formatting in Scrivener makes the interface appear more similar to a plain-text editor. With very basic formatting (bold, italics, headings, and citations) I am able to ensure that in the end I can export plain-text files from Scrivener with Markdown format.

When I export every note as a plain-text file, it allows me to commit the writing to a git repository for archiving and also easy diff’ing if necessary. If I compile the writing, I still export as plain-text, but this is in preparation for one further step: conversion to a more conventional file format (for example, Microsoft Word). 

Conversion to Word is done with pandoc:
```
pandoc -s -S --normalize --bibliography \
~/Dropbox/phd\ research/Bibliography.bib \
--csl ~/.csl/chicago-fullnote-bibliography.csl \
-f markdown -t docx \
-o OUTFILE.docx INFILE.txt
```

I am publishing the outline directly to Github pages with [scriv2web](https://github.com/seandockray/scriv2web)
```
./publish.py -i ../../../scrivener/Trials.scriv -o ../../../scrivener/trials_web  -b ../../../Bibliography.bib -c ~/.csl/chicago-fullnote-bibliography.csl -r origin
```