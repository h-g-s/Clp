include $(top_srcdir)/BuildTools/Makemain.inc

########################################################################
#                               libOsi                                 #
########################################################################

lib_LTLIBRARIES = libOsi.la

libOsi_la_SOURCES = \
	OsiConfig.h \
	OsiAuxInfo.cpp OsiAuxInfo.hpp \
	OsiBranchingObject.cpp OsiBranchingObject.hpp \
	OsiChooseVariable.cpp OsiChooseVariable.hpp \
	OsiColCut.cpp OsiColCut.hpp \
	OsiCollections.hpp \
	OsiCut.cpp OsiCut.hpp \
	OsiCuts.cpp OsiCuts.hpp \
	OsiColumnType.hpp \
	OsiNames.cpp \
	OsiPresolve.cpp OsiPresolve.hpp \
	OsiRowCut.cpp OsiRowCut.hpp \
	OsiRowCutDebugger.cpp OsiRowCutDebugger.hpp \
	OsiSolverBranch.cpp OsiSolverBranch.hpp \
	OsiSolverInterface.cpp OsiSolverInterface.hpp \
	OsiSolverParameters.hpp \
	OsiFeatures.cpp OsiFeatures.hpp

libOsi_la_LIBADD = $(OSILIB_LFLAGS)

AM_LDFLAGS = $(LT_LDFLAGS)

AM_CPPFLAGS = $(OSILIB_CFLAGS)

########################################################################
#                Headers that need to be installed                     #
########################################################################

includecoindir = $(pkgincludedir)
includecoin_HEADERS = \
	OsiConfig.h \
	OsiAuxInfo.hpp \
	OsiBranchingObject.hpp \
	OsiChooseVariable.hpp \
	OsiColCut.hpp \
	OsiCollections.hpp \
	OsiColumnType.hpp \
	OsiCut.hpp \
	OsiCuts.hpp \
	OsiPresolve.hpp \
	OsiRowCut.hpp \
	OsiRowCutDebugger.hpp \
	OsiSolverBranch.hpp \
	OsiSolverInterface.hpp \
	OsiSolverParameters.hpp \
	OsiFeatures.hpp
