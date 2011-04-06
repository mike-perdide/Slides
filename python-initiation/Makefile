src = template.tex

all: slides

slides: $(src)
	pdflatex template.tex
	pdflatex template.tex

once: $(src)
	pdflatex template.tex

clean:
	rm *.aux *.log *.pdf *.nav *.out *.snm *.toc *.vrb
