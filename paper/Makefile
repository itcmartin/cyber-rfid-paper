FSWATCH = /usr/bin/env fswatch
LATEXMK = /usr/bin/env latexmk

TEXFILES = \
	main.tex
IMGFILES =
BIBFILES = bib/main.bib

.PHONY: all clean watch

all: main.pdf

main.pdf: $(TEXFILES) $(IMGFILES) $(BIBFILES)
	$(LATEXMK) -pdf -use-make $<

clean:
	$(LATEXMK) -pdf -bibtex -C

watch: $(TEXFILES) $(IMGFILES) $(BIBFILES)
	$(MAKE)
	$(FSWATCH) -o $^ | xargs -n1 sh -c $(MAKE)
