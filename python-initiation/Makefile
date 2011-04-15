# Makefile.pdflatex
# Author:	Johannes Ranke <jranke@uni-bremen.de>
# Last Change: 2006 Apr 18
# based on the Makefiles of Tadeusz Pietraszek
# posted on his blog on March 24, 2006
#
# simplified for our slides (majerti 2011)

TEXFILES=$(wildcard *.tex)

RERUN = "(There were undefined references|Rerun to get (cross-references|the bars) right|Table widths have changed. Rerun LaTeX.|Linenumber reference failed)"
RERUNBIB = "No file.*\.bbl|Citation.*undefined"

all: template.pdf

show: template.pdf
	see template.pdf

clean: clean-recursive
	rm -f *.aux *.log *.bbl *.blg *.brf *.cb *.ind *.idx *.ilg  \
          *.inx *.ps *.dvi *.toc *.out *.lot *~ *.lof *.ttt *.fff

distclean:
	rm -f template.pdf

clean-recursive:
	for dir in $(wildcard *); do if [ -d $$dir ] && [ -f $$dir/Makefile ]; then cd $$dir; $(MAKE) clean; cd ..; fi; done

%.pdf: %.tex
	pdflatex $<
	egrep -c $(RERUNBIB) $*.log && (bibtex $*;pdflatex $<); true
	egrep $(RERUN) $*.log && (pdflatex $<) ; true
	egrep $(RERUN) $*.log && (pdflatex $<) ; true

