
.PHONY: pdf-illustrations

.DELETE_ON_ERROR: paper.aux

paper.pdf: paper.bbl paper.aux pdf-illustrations #paper.toc
	pdflatex paper
	pdflatex paper

pdf/%.pdf: eps/%.eps
	mkdir pdf || true
	epstopdf "$<" "$@"

pdf-illustrations: pdf/fft-8.pdf pdf/fft-n8-p2.pdf pdf/gemm-n4.pdf pdf/gemm-n4-p8.pdf pdf/2d-block.pdf

paper.bbl: paper.aux paper.bib
	bibtex paper

paper.aux: paper.tex
	pdflatex paper

paper.tar.gz: paper.tex figures/ listings/ paper.bib
	tar cvfz "$@" $^

