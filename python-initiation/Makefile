src=$(wildcard *.tex)

all: template.pdf

show: template.pdf
	see template.pdf

template.pdf: $(src)
	pdflatex template.tex -draftmode -halt-on-error -interaction batchmode
	pdflatex template.tex -halt-on-error -interaction batchmode

once: $(src)
	pdflatex template.tex

clean:
	rm -f *.aux *.log *.pdf *.nav *.out *.snm *.toc *.vrb
