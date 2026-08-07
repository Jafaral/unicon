# uniphinx User Guide (doc/uniphinx)
# Built with uniphinx from uni/uniphinx/

SHELL=/bin/sh
TOPDIR=../..
UNICON_TOP_BUILDDIR ?= $(TOPDIR)
include $(UNICON_TOP_BUILDDIR)/Makedefs

UNIPHINX_DIR = $(TOPDIR)/uni/uniphinx
UNIPHINX ?= $(UNIPHINX_DIR)/uniphinx
TITLE = uniphinx User Guide
MANIFEST = manual.manifest
OUTDIR = out
THEME ?= basic
THEMES = $(UNIPHINX_DIR)/themes

.PHONY: all html latex pdf basic classic dark clean

default: html
all: html

html: $(UNIPHINX)
	mkdir -p $(OUTDIR)/images
	-cp -f images/* $(OUTDIR)/images/ 2>/dev/null || true
	$(UNIPHINX) --manifest=$(MANIFEST) --title="$(TITLE)" \
		--copyright="2026, Jafar Al-Gharaibeh" \
		--logo=images/uniphinx-logo.png \
		--targetDir=$(OUTDIR) --theme=$(THEME) --themePath=$(THEMES)

latex: $(UNIPHINX)
	mkdir -p $(OUTDIR)/images
	-cp -f images/* $(OUTDIR)/images/ 2>/dev/null || true
	$(UNIPHINX) --format=latex --manifest=$(MANIFEST) --title="$(TITLE)" \
		--targetDir=$(OUTDIR)

pdf: $(UNIPHINX)
	mkdir -p $(OUTDIR)/images
	-cp -f images/* $(OUTDIR)/images/ 2>/dev/null || true
	$(UNIPHINX) --format=pdf --manifest=$(MANIFEST) --title="$(TITLE)" \
		--targetDir=$(OUTDIR)

basic:
	$(MAKE) html THEME=basic

classic:
	$(MAKE) html THEME=classic

dark:
	$(MAKE) html THEME=dark

$(UNIPHINX):
	$(MAKE) -C $(UNIPHINX_DIR)

clean:
	rm -rf $(OUTDIR)
