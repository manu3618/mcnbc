LATEX=pdflatex
BIBTEX=bibtex
BIB=$(wildcard *.bib)
RERUN='(There is undefined reference|Rerun to get (cross-references|the bars) right)'
OBJ:=$(wildcard *.tex *png *aux zombies_files/*png)

.PHONY: all
all: zombie.pdf


zombie.pdf: zombie.tex $(OBJ)
	${LATEX} $<


zombie.tex zombie_files/%.png: zombie.ipynb
	python -m nbconvert --to latex $<


transition.png: transition.tex
	${LATEX} $<


indent: *.tex
	for i in *.tex; do latexindent -w -y="defaultIndent:'    '" $$i ; done


.PHONY: clean
clean:
	rm -frv *.log *.aux *.dvi *.toc *.lot *.lof *.snm *.nav *.out *.tns *.bak? *.blg *.idx *.ilg *.loa *.tdo *.vrb zombies_files/
