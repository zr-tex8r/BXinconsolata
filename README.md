BXinconsolata Package
=====================

LaTeX: Better support of Inconsolata font

The [inconsolata package] \(by Karl Berry) provides support for use
of [Inconsolata] font. But this package has some properties I do not
like much, particularly when I use it to typeset source code.

  * The digit zero is printed as non-slashed glyph, although the font
    itself has the slashed glyph as default.
  * The characters `\textasciigrave` and `\textquotsingle` are missing
    in the TS1 encoding. They are needed to print source code using
    true ASCII characters with aid of the [upquote package].

The present package provides a set of virtual fonts that resolves the
above-mentioned problems.

[inconsolata package]: http://www.ctan.org/pkg/inconsolata
[Inconsolata]: http://levien.com/type/myfonts/inconsolata.html
[upquote package]: http://www.ctan.org/pkg/upquote

### Installation

  - `*.sty` → $TEXMF/tex/latex/BXinconsolata
  - `*.tfm` → $TEXMF/fonts/tfm/public/BXinconsolata
  - `*.vf`  → $TEXMF/fonts/vf/public/BXinconsolata

The bxinconsolata Package
-------------------------

### Package Loading

You can load this package *in place of* the inconsolata package
(which is loaded inside the package).

    \usepackage[<option>,...]{bxinconsolata}

The set of available options is the same as that of the inconsolata
package.

### Usage

When this package is loaded, the generic monospaced family is switched
to Inconsolata (`fi4` family); this is the same behavior as the
inconsolata package is used, but T1 and TS1 fonts are replaced by the
new ones with improved encodings.

  * The digit zero has a slashed glyph.
  * You can use the upquote package to print verbatim with true ASCII
    characters, as shown below:

        \documentclass{article}
        \usepackage[T1]{fontenc} % must use T1
        \usepackage{upquote}
        \usepackage{bxinconsolata}
        \begin{document}
        
        \begin{verbatim}
        TODAY=`date +'%Y%m%d'`
        \end{verbatim}
        
        \end{document}

Revision History
----------------

  * Version 0.2 <2013/04/20>
      - The first public version.

--------------------
Takayuki YATO (aka. "ZR")  
http://zrbabbler.sp.land.to/
