FILE=doc

# Casual build
.PHONY: make
make: clean
	pdflatex -draftmode $(FILE)
	bibtex $(FILE)
	pdflatex -draftmode $(FILE)
	pdflatex $(FILE)

# TRAVIS-CI build
.PHONY: travis-build
travis-build: clean-all
	pdflatex -halt-on-error -draftmode $(FILE)
	bibtex $(FILE)
	pdflatex -halt-on-error -draftmode $(FILE)
	pdflatex -halt-on-error $(FILE)

# Remove LaTeX auxiliary files
.PHONY: clean
clean:
	@rm -fv *.aux *.log *.dvi *.ps *.bbl *.blg *.toc *.out *.lof

# Remove all excluding source files
.PHONY: clean-all
clean-all: clean
	@rm -fv *.pdf
