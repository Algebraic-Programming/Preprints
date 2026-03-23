
paper.pdf: paper.bbl paper.aux paper.toc
	pdflatex paper

paper.bbl: paper.aux paper.bib
	bibtex paper

paper.aux: paper.tex
	pdflatex paper

paper.tar.gz: paper.tex figures/ listings/ paper.bib
	tar cvfz "$@" $^

