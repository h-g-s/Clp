# Copyright (C) 2006 International Business Machines and others.
# All Rights Reserved.
# This file is distributed under the Eclipse Public License.
#
# Author:  Andreas Waechter           IBM    2006-04-13

include $(top_srcdir)/BuildTools/Makemain.inc

########################################################################
#                               libClp                                 #
########################################################################

# Let the code know we're building the Clp libraries.

# Name of the library compiled in this directory.  We want it to be installed
# in the 'lib' directory
lib_LTLIBRARIES = libClp.la 

# List all source files for this library, including headers
libClp_la_SOURCES = \
	ClpConfig.h \
	ClpCholeskyBase.cpp ClpCholeskyBase.hpp \
	ClpCholeskyDense.cpp ClpCholeskyDense.hpp \
	ClpConstraint.cpp ClpConstraint.hpp \
	ClpConstraintLinear.cpp ClpConstraintLinear.hpp \
	ClpConstraintQuadratic.cpp ClpConstraintQuadratic.hpp \
	Clp_C_Interface.cpp Clp_C_Interface.h \
	ClpDualRowDantzig.cpp ClpDualRowDantzig.hpp \
	ClpDualRowPivot.cpp ClpDualRowPivot.hpp \
	ClpDualRowSteepest.cpp ClpDualRowSteepest.hpp \
	ClpDummyMatrix.cpp ClpDummyMatrix.hpp \
	ClpDynamicExampleMatrix.cpp ClpDynamicExampleMatrix.hpp \
	ClpDynamicMatrix.cpp ClpDynamicMatrix.hpp \
	ClpEventHandler.cpp ClpEventHandler.hpp \
	ClpFactorization.cpp ClpFactorization.hpp \
	ClpGubDynamicMatrix.cpp ClpGubDynamicMatrix.hpp \
	ClpGubMatrix.cpp ClpGubMatrix.hpp \
	ClpHelperFunctions.cpp ClpHelperFunctions.hpp \
	ClpInterior.cpp ClpInterior.hpp \
	ClpLinearObjective.cpp ClpLinearObjective.hpp \
	ClpMatrixBase.cpp ClpMatrixBase.hpp \
	ClpMessage.cpp ClpMessage.hpp \
	ClpModel.cpp ClpModel.hpp \
	ClpNetworkBasis.cpp ClpNetworkBasis.hpp \
	ClpNetworkMatrix.cpp ClpNetworkMatrix.hpp \
	ClpNonLinearCost.cpp ClpNonLinearCost.hpp \
	ClpNode.cpp ClpNode.hpp \
	ClpObjective.cpp ClpObjective.hpp \
	ClpOutput.cpp ClpOutput.hpp \
	ClpPackedMatrix.cpp ClpPackedMatrix.hpp \
	ClpParamUtils.cpp ClpParamUtils.hpp \
	ClpParam.cpp ClpParam.hpp \
	CbcOrClpParam.cpp CbcOrClpParam.hpp \
	ClpParameters.cpp ClpParameters.hpp \
	ClpModelParameters.hpp \
	ClpPlusMinusOneMatrix.cpp ClpPlusMinusOneMatrix.hpp \
	ClpPredictorCorrector.cpp ClpPredictorCorrector.hpp \
	ClpPdco.cpp ClpPdco.hpp \
	ClpPdcoBase.cpp ClpPdcoBase.hpp \
	ClpLsqr.cpp ClpLsqr.hpp \
	ClpPresolve.cpp ClpPresolve.hpp \
	ClpRacingSolver.cpp ClpRacingSolver.hpp \
	ClpPrimalColumnDantzig.cpp ClpPrimalColumnDantzig.hpp \
	ClpPrimalColumnPivot.cpp ClpPrimalColumnPivot.hpp \
	ClpPrimalColumnSteepest.cpp ClpPrimalColumnSteepest.hpp \
	ClpQuadraticObjective.cpp ClpQuadraticObjective.hpp \
	ClpSimplex.cpp ClpSimplex.hpp \
	ClpSimplexDual.cpp ClpSimplexDual.hpp \
	ClpSimplexNonlinear.cpp ClpSimplexNonlinear.hpp \
	ClpSimplexOther.cpp ClpSimplexOther.hpp \
	ClpSimplexPrimal.cpp ClpSimplexPrimal.hpp \
	ClpSolve.cpp ClpSolve.hpp \
	Idiot.cpp Idiot.hpp \
	IdiSolve.cpp \
	ClpPESimplex.cpp ClpPESimplex.hpp \
	ClpPEPrimalColumnDantzig.cpp ClpPEPrimalColumnDantzig.hpp \
 	ClpPEPrimalColumnSteepest.cpp ClpPEPrimalColumnSteepest.hpp \
 	ClpPEDualRowDantzig.cpp ClpPEDualRowDantzig.hpp \
 	ClpPEDualRowSteepest.cpp ClpPEDualRowSteepest.hpp \
	ClpSolver.cpp \
	MyEventHandler.cpp MyEventHandler.hpp \
	MyMessageHandler.cpp MyMessageHandler.hpp \
	unitTest.cpp


# AMD (BSD 3-clause) for barrier Cholesky ordering
if COIN_HAS_AMD
libClp_la_SOURCES += ClpCholeskyUfl.cpp ClpCholeskyUfl.hpp
endif

# List all additionally required libraries
libClp_la_LIBADD = $(CLPLIB_LFLAGS)

########################################################################
#                            clp program                               #
########################################################################

# Name of the executable compiled in this directory.  We want it to be
# installed in the 'bin' directory
bin_PROGRAMS = clp

# List all source files for this executable, including headers
clp_SOURCES = ClpMain.cpp 

# List all additionally required libraries
clp_LDADD = libClp.la $(CLPLIB_LFLAGS)

########################################################################
#                            Additional flags                          #
########################################################################

AM_CPPFLAGS = $(CLPLIB_CFLAGS)

# Use additional libtool flags
AM_LDFLAGS = $(LT_LDFLAGS)

########################################################################
#                Headers that need to be installed                     #
########################################################################

# Here list all the header files that are required by a user of the library,
# and that therefore should be installed in 'include/coin-or'
includecoindir = $(pkgincludedir)
includecoin_HEADERS = \
	Clp_C_Interface.h \
	ClpCholeskyBase.hpp \
	ClpCholeskyDense.hpp \
	ClpConstraint.hpp \
	ClpConstraintLinear.hpp \
	ClpConstraintQuadratic.hpp \
	ClpDualRowDantzig.hpp \
	ClpDualRowPivot.hpp \
	ClpDualRowSteepest.hpp \
	ClpDummyMatrix.hpp \
	ClpDynamicExampleMatrix.hpp \
	ClpDynamicMatrix.hpp \
	ClpEventHandler.hpp \
	ClpAbortHandler.hpp \
	ClpFactorization.hpp \
	ClpGubDynamicMatrix.hpp \
	ClpGubMatrix.hpp \
	ClpInterior.hpp \
	ClpLinearObjective.hpp \
	ClpMatrixBase.hpp \
	ClpMessage.hpp \
	ClpModel.hpp \
	ClpModelParameters.hpp \
	ClpNetworkMatrix.hpp \
	ClpNonLinearCost.hpp \
	ClpNode.hpp \
	ClpObjective.hpp \
	ClpOutput.hpp \
	ClpPackedMatrix.hpp \
	ClpParamUtils.hpp \
	ClpPdcoBase.hpp \
	ClpPlusMinusOneMatrix.hpp \
	ClpParameters.hpp \
	ClpPresolve.hpp \
	ClpRacingSolver.hpp \
	ClpPrimalColumnDantzig.hpp \
	ClpPrimalColumnPivot.hpp \
	ClpPrimalColumnSteepest.hpp \
	ClpQuadraticObjective.hpp \
	ClpSimplex.hpp \
	ClpSimplexNonlinear.hpp \
	ClpSimplexOther.hpp \
	ClpSimplexDual.hpp \
	ClpSimplexPrimal.hpp \
	ClpSolve.hpp \
	ClpParam.hpp \
	ClpParameters.hpp \
	Idiot.hpp \
	ClpPESimplex.hpp \
	ClpPEPrimalColumnDantzig.hpp \
	ClpPEPrimalColumnSteepest.hpp \
	ClpPEDualRowDantzig.hpp \
	ClpPEDualRowSteepest.hpp \
	CbcOrClpParam.hpp \
	CbcOrClpParam.cpp 


# AMD barrier Cholesky header
if COIN_HAS_AMD
includecoin_HEADERS += ClpCholeskyUfl.hpp
endif

# needed by Cbc
includecoin_HEADERS += ClpParam.cpp


#######################################################################
# Create the Config.h file that has all public defines and install it #
#######################################################################

install-exec-local:
	$(install_sh_DATA) config_clp.h $(DESTDIR)$(includecoindir)/ClpConfig.h

uninstall-local:
	rm -f $(DESTDIR)$(includecoindir)/ClpConfig.h
