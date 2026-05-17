# Copyright (C) 2006 International Business Machines and others.
# All Rights Reserved.
# This file is distributed under the Eclipse Public License.
#
# Author:  Andreas Waechter           IBM    2006-04-13

include BuildTools/Makemain.inc

########################################################################
#            Subdirectories and installation of .pc files              #
########################################################################

SUBDIRS = src src/Osi src/OsiClp src/OsiCommonTest

pkgconfiglib_DATA = clp.pc osi.pc osi-clp.pc osi-unittests.pc

########################################################################
#                           Extra Targets                              #
########################################################################

test: all
	cd test; $(MAKE) test

unitTest: test

clean-local: clean-doxygen-docs
	if test -r test/Makefile; then cd test; $(MAKE) clean; fi

install-exec-local: install-doc

uninstall-local: uninstall-doc uninstall-doxygen-docs

.PHONY: test unitTest
