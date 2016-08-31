TEX = pandoc
src = template.tex details_fr.yml publi.yml
FLAGS = --latex-engine=xelatex
PDF = ../assets/CV_KevCaz/CV_KevCaz.pdf
ZIP = ../assets/CV_KevCaz.zip

all: publi.yml $(PDF) $(ZIP)


$(ZIP) : $(PDF)
	zip $@ $<


publi.yml: publi.bib
	pandoc-citeproc -y $< $ > $@

$(PDF) : $(src)
	$(TEX)  $(filter-out $<,$^ ) -o $@ --template=$< $(FLAGS)

.PHONY: all
clean :
	rm $(PDF)
