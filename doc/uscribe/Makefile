# uscribe User Guide (doc/uscribe)
# Built with uscribe from uni/uscribe/

SHELL=/bin/sh
TOPDIR=../..
UNICON_TOP_BUILDDIR ?= $(TOPDIR)
include $(UNICON_TOP_BUILDDIR)/Makedefs

USCRIBE_DIR = $(TOPDIR)/uni/uscribe
USCRIBE ?= $(USCRIBE_DIR)/uscribe
TITLE = uscribe User Guide
NAME = uscribe-userguide
MANIFEST = manual.manifest
OUTDIR = out
THEME ?= basic
THEMES = $(USCRIBE_DIR)/themes
USCRIBE_FLAGS = --manifest=$(MANIFEST) --title="$(TITLE)" \
	--name=$(NAME) --targetDir=$(OUTDIR) \
	--logo=images/uscribe-logo.png

.PHONY: all html latex pdf basic classic dark clean

default: html
all: html

html: $(USCRIBE)
	mkdir -p $(OUTDIR)/images
	-cp -f images/* $(OUTDIR)/images/ 2>/dev/null || true
	$(USCRIBE) $(USCRIBE_FLAGS) \
		--copyright="2026, Jafar Al-Gharaibeh" \
		--theme=$(THEME) --themePath=$(THEMES)

latex: $(USCRIBE)
	mkdir -p $(OUTDIR)/images
	-cp -f images/* $(OUTDIR)/images/ 2>/dev/null || true
	$(USCRIBE) --format=latex $(USCRIBE_FLAGS)

pdf: $(USCRIBE)
	mkdir -p $(OUTDIR)/images
	-cp -f images/* $(OUTDIR)/images/ 2>/dev/null || true
	$(USCRIBE) --format=pdf $(USCRIBE_FLAGS)

basic:
	$(MAKE) html THEME=basic

classic:
	$(MAKE) html THEME=classic

dark:
	$(MAKE) html THEME=dark

$(USCRIBE):
	$(MAKE) -C $(USCRIBE_DIR)

clean:
	rm -rf $(OUTDIR)
