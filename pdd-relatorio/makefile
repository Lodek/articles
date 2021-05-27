dir := $(shell pwd)
uid := $(shell id -u)
gid := $(shell id -g)
target := doc


run:
	docker run --rm -v ${dir}:/target -u ${uid}:${gid} latex make compile

compile: 
	pdflatex ${target}.tex
	/usr/bin/vendor_perl/biber ${target}
	pdflatex ${target}

.PHONY: clean compile run

clean:
	rm *.log *.bcf *.aux *.bbl *.blg *.run.xml *.toc *.out
