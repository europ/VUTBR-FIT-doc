FILE=doc

# Casual build
.PHONY: make
make: clean
	@pdflatex -draftmode $(FILE)
	@bibtex $(FILE)
	@pdflatex -draftmode $(FILE)
	@pdflatex $(FILE)

# TRAVIS-CI build
.PHONY: travis-build
travis-build: clean-all
	pdflatex -halt-on-error -draftmode $(FILE)
	bibtex $(FILE)
	pdflatex -halt-on-error -draftmode $(FILE)
	pdflatex -halt-on-error $(FILE)

# Print normo page count
.PHONY: normo
normo: normoconst := 1800
normo: characters := $(shell texcount -sum -1 -char $(FILE).tex)
normo: normopages := $(shell echo "scale=2; $(characters)/$(normoconst)" | bc)
normo:
	@echo "File ............. $(FILE).tex"
	@echo "Character sum .... $(characters)"
	@echo "One normo page ... $(normoconst)"
	@echo "Normo page sum ... $(normopages)"
	@echo
	@echo "$(shell tput setaf 1)$(shell tput bold)$(normopages)$(shell tput sgr0)"

# Print statistics
.PHONY: stat
stat:
	@texcount -sum -char -nosub $(FILE).tex
	@texcount -sum -char -nosub quotation.bib

# Remove LaTeX auxiliary files
.PHONY: clean
clean:
	@rm -fv *.aux *.log *.dvi *.ps *.bbl *.blg *.toc *.out *.lof

# Remove all excluding source files
.PHONY: clean-all
clean-all: clean
	@rm -fv *.pdf
