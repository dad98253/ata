## Process this file with automake to produce Makefile.in

include ataOBJS.inc
include ataINCS.inc

ACLOCAL_AMFLAGS = -I m4 --install

#build ata
bin_PROGRAMS = $(top_builddir)/bin/ata
__top_builddir__bin_ata_SOURCES = $(ATAMAIN) $(ATASOURCES)

AM_FFLAGS = -fno-align-commons -std=legacy

if LINUX
@GENERATE_CHANGELOG_RULES@
  dist-hook: dist-ChangeLog
endif 


distclean-local:
	@rm config.status configure config.log
	@rm Makefile
	@rm -r autom4te.cache/
	@rm aclocal.m4
	@rm Makefile.in


#add header files
noinst_HEADERS = $(ATAINCLUDES)

help:
	-@echo "make                    --> build ata"
	-@echo "make clean              --> delete what was built"
	-@echo "make distclean          --> delete auto tools products"
	-@echo "make dist               --> build distribution package"


