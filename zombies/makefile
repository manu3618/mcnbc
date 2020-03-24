LATEX=pdflatex
BIBTEX=bibtex
BIB=$(wildcard *.bib)
RERUN='(There is undefined reference|Rerun to get (cross-references|the bars) right)'
OBJ=$(wildcard *aux zombies_files/*png) transition.png transition.pdf zombie.tex

.PHONY: all
all: zombie.pdf


zombie.pdf: zombie.tex transition.png
	${LATEX} $<


zombie.tex: zombie.ipynb
	python -m nbconvert --to latex $<


transition.pdf: transition.tex
	${LATEX} $<


transition.png: transition.pdf
	pdftoppm $< > $@


indent: *.tex
	for i in *.tex; do latexindent -w -y="defaultIndent:'    '" $$i ; done


.PHONY: clean
clean:
	rm -frv *.log *.aux *.dvi *.toc *.lot *.lof *.snm *.nav *.out *.tns *.bak? *.blg *.idx *.ilg *.loa *.tdo *.vrb ${OBJ}


mrproper: clean
	rm zombie.pdf
