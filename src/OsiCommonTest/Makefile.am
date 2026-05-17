include $(top_srcdir)/BuildTools/Makemain.inc

########################################################################
#                    Common Test library for Osi                       #
########################################################################

lib_LTLIBRARIES = libOsiCommonTest.la

libOsiCommonTest_la_SOURCES = \
	OsiUnitTests.hpp \
	OsiUnitTestsConfig.h \
	OsiColCutTest.cpp \
	OsiCutsTest.cpp \
	OsiRowCutDebuggerTest.cpp \
	OsiRowCutTest.cpp \
	OsiSimplexAPITest.cpp \
	OsiNetlibTest.cpp \
	OsiUnitTestUtils.cpp \
	OsiSolverInterfaceTest.cpp

libOsiCommonTest_la_LIBADD = $(OSICOMMONTESTLIB_LFLAGS) ../Osi/libOsi.la

AM_LDFLAGS = $(LT_LDFLAGS)

AM_CPPFLAGS = -I$(srcdir)/../Osi $(OSICOMMONTESTLIB_CFLAGS)

########################################################################
#                Headers that need to be installed                     #
########################################################################

includecoindir = $(pkgincludedir)
includecoin_HEADERS = OsiUnitTests.hpp OsiUnitTestsConfig.h
