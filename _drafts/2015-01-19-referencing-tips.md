---
layout: post
title: Referencing tips
categories: []
tags: []
published: True

---




## Notes on referencing a document

Important to specify the type correctly.
Note that there are often fewer types in a CSL file than that which you need.

e.g. the Vancouver CSL file

Includes

Matched as 'any'

- article-journal
- article-magazine
- article-newspaper
- bill
- legislation

Matched to its own type
- report
- patent
- speech

NOTE: 2015-01-19 - [ ] in the end I couldn't get this to work and went back to doing it manually with Bookends



## An example command (template)

    pandoc -o paper-spotearly.docx \
        --smart \
        --normalize \
        --reference-docx=pandoc-reference.docx  \
        --bibliography=paper-spotearly.xml \
        --csl=the-lancet.csl \
        paper-spotearly.md


## Pandoc and `pandoc-citeproc`

Don't download the CSL files directly from github (I don't know why but they fail.) Instead, use the [Zotero](https://zotero.org/styles) reference finder.

## Useful links

https://zotero.org/styles
http://citationstyles.org/

