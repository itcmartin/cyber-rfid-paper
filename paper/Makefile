FSWATCH = /usr/bin/env fswatch
LATEXMK = /usr/bin/env latexmk

TEXFILES = \
	main.tex \
	tex/abstract.tex \
	tex/conclusion.tex \
	tex/introduction.tex \
	tex/method.tex \
	tex/related-work.tex \
	tex/results.tex
IMGFILES = \
	img/active-directory.png \
	img/loadmaster-geo.png \
	img/loadmaster-ids-ips.png \
        img/loadmaster-pcre-rules.png \
	img/login-flow.png \
	img/raspberry-pi-rfid.png \
	img/whatsup-gold.png
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
