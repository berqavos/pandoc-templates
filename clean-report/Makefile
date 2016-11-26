PY=python
PANDOC=pandoc

BASEDIR=$(CURDIR)
INPUTDIR=$(BASEDIR)/source
OUTPUTDIR=$(BASEDIR)/output
TEMPLATEDIR=$(INPUTDIR)/templates
STYLEDIR=$(BASEDIR)/style

BIBFILE=$(INPUTDIR)/references.bib

help:
	@echo ''
	@echo 'Makefile for the Markdown report                                       '
	@echo '                                                                       '
	@echo 'Usage:                                                                 '
	@echo '   make pdf                generate a PDF file                         '
	@echo '                                                                       '
	@echo '                                                                       '
	@echo 'get local templates with: pandoc -D latex/html/etc                     '
	@echo 'or generic ones from: https://github.com/jgm/pandoc-templates          '

pdf:
	pandoc "$(INPUTDIR)"/*.md \
        -r markdown+yaml_metadata_block \
        -o "$(OUTPUTDIR)/report.pdf" \
        --template="$(STYLEDIR)/report-template.tex" \
        --highlight-style=pygments \
        --listings \
        -N \
        --latex-engine=pdflatex \
        --verbose
