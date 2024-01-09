
These templates generate a book-style result with a nice title page, code listings, glossary, breakout boxes etc and decent formatting and defaults set. See below for all the options. 

They also allow inline tracking of things which need to be checked or fixed before publishing the notes. These should be placed in a \fbr{} environment and will highlighted in bold red within the text and also extracted into a list showing the source filename and the line number. This will be in the file <filename>.FixBeforeRelease. An example is given.


# What the templates provide

A nice title page with Warwick RSE angry penguin

Warwick colour branding as warwickred, green, gold and orange, plus some other colours. 

Syntax coloring and nice display style for code via the lstlistings package. Fortran is forstyle, python is pystyle, C or C++ is cstyle. nostyle applies simple styling without language awareness. 

We also add some custom "languages" from prior stuff, including a loose pseudo code (pseudostyle) (see LanguageDefs for keywords), docs (for Doxygen), make (for Make) and debug (for gdb colourising). 

Glossaries by filling in the glossary_defs file. Once these are done, compile the GlossariesOnly main document to get just a glossary

Break-able boxes for asides, intro or advanced info etc. 

Forced float placement to try and get figures where desired. 

Extraction of text - the FixBeforeRelease for flagging text which needs to be filled in, edited or checked before publishing the notes. 

We also have optional CollationStreams and CollationOutput, which shows a model for extracting inline sections of text into an appendix. We use this for e.g. encoding "golden rules" as "must" and "mustnt" Duplicate this for example for doing a log of additions if something was expanded etc. 

# Using the templates

Checklist of things to get started

* Rename MainDocument.tex to desired name
* Put the title, subtitle, author name(s) and typesetter name into AuthorInfo
* Fix the dedication if required at line 44 (date, workshop associations etc)
* Fix the license info if required at line 48
* If there is an associated repository for code, fill this in at line 60

Checklist as you go

* Use one file per chapter and include these into the main document where marked at line 67. An example ChapterFile is given
* Use \footnote for additions, short asides etc
* For long asides, use the asidebox environment. This gives a (multipage capable) grey box, with a border. Give the box a useful title. This is ideal for advanced or background material as it makes it easy to skip and come back to. 
* Use \lstlisting and \lstinline for all code. Languages are described below and styles for them given
* Use \gls, \glspl for glossary entries. Use a short name if required and also place the definitions in the glossary_defs.tex file. By default, all entries will be included, whether used in the text or not - delete "\glsaddallunused" (line 80 in original MainDocument) to disable. 
* For figures, either embed inline using just \includegraphics or use the figure environment as shown to add captions etc. Figures should be in the Images subdirectory. The float package is used and configured to force immediate placement. 
* There is a simple environment \presnote which defaults to swallow all input. Use this instead of comments to allow including this text in the final output if desired

Checklist to complete before publishing

* Make sure all typesetting errors are fixed
* Make sure FixBeforeRelease file is empty
* (Re)Typeset to get current date on titlepage

