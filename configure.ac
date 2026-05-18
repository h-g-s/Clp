# Copyright (C) 2006 International Business Machines.
# All Rights Reserved.
# This file is distributed under the Eclipse Public License.
#
# Author:  Andreas Waechter            IBM    2006-04-13

#############################################################################
#                       Names and other basic things                        #
#############################################################################

AC_INIT([Clp],[devel],[https://github.com/coin-or/Clp/issues/new],[coin-or-clp],[https://github.com/coin-or/Clp])

AC_COPYRIGHT([
Copyright 2006 International Business Machines and others.
All Rights Reserved.
This file is part of the open source package Clp which is distributed
under the Eclipse Public License.])

# List one file in the package so that the configure script can test
# whether the package is actually there.
AC_CONFIG_SRCDIR(src/ClpSimplex.cpp)

# Do some initialization work (version numbers, change prefix default, ...)
AC_CONFIG_MACRO_DIRS([BuildTools m4])
AC_COIN_INITIALIZE

#############################################################################
#                         Standard build tool stuff                         #
#############################################################################

# Get the name of the C++ compiler and appropriate compiler options.
AC_COIN_PROG_CXX

# This is a C++ package, set the language accordingly.
AC_LANG_PUSH(C++)

# Initialize libtool
AC_COIN_PROG_LIBTOOL

# set RPATH_FLAGS to the compiler link flags required to hardcode location
# of the shared objects (expanded_libdir is set somewhere in configure before)
# (use in examples Makefile)
AC_COIN_RPATH_FLAGS([$expanded_libdir])

#############################################################################
#                   Math headers                                            #
#############################################################################

# Check for cmath/math.h, cfloat/float.h, cieeefp/ieeefp.h
AC_COIN_CHECK_MATH_HDRS

# Check for intrinsics header for ClpPackedMatrix.cpp
AC_CHECK_HEADERS([immintrin.h intrin.h arm_neon.h fmaintrin.h],[break],[])

#############################################################################
#                              COIN-OR components                           #
#############################################################################

AC_COIN_CHK_PKG(CoinUtils,[ClpLib OsiClpUnitTest OsiLib OsiCommonTestLib])
if test $coin_has_coinutils != yes ; then
  AC_MSG_ERROR([Required package CoinUtils not available.])
fi
AC_COIN_CHK_PKG(Sample,,[coindatasample],[],dataonly)
AC_COIN_CHK_PKG(Netlib,,[coindatanetlib],[],dataonly)

#############################################################################
#                        Third party linear solvers                         #
#############################################################################

# AMD (Approximate Minimum Degree ordering) from SuiteSparse — BSD 3-clause license.
# Used by ClpCholeskyUfl for the barrier (interior-point) LP solver.

# amd.h
AC_COIN_CHK_LIBHDR(AMD,[ClpLib],[-lamd],[-I/usr/include/suitesparse],[],
  [[double Control[AMD_CONTROL];
   amd_defaults(Control);]],
  [#include "amd.h"])

#############################################################################
#                             Other dependencies                            #
#############################################################################

# ClpRacingSolver uses std::thread. On glibc >= 2.34 (Ubuntu 22.04+),
# pthread_create lives in libc and no extra flag is needed.  On older
# systems AC_SEARCH_LIBS will add -lpthread to LIBS (end of link command)
# rather than to CLPLIB_LFLAGS; this avoids changing the link order in a
# way that causes at-exit crashes in static builds.
AC_SEARCH_LIBS([pthread_create],[pthread])

##############################################################################
#                   VPATH links for example input files                      #
##############################################################################

# In case this is a VPATH configuration we need to make sure that the
# input files for the examples are available in the VPATH directory.
AC_COIN_EXAMPLE_FILES([examples/hello.mps examples/input.130])
AC_COIN_EXAMPLE_FILES([examples/g.tiny examples/gparm.tiny])

#############################################################################
#                  Check for doxygen                                        #
#############################################################################

AC_COIN_DOXYGEN([CoinUtils])

##############################################################################
#                   Finishing up by writing all the output                   #
##############################################################################

# Finalize libs and cflags.
AC_COIN_FINALIZE_FLAGS([OsiLib OsiCommonTestLib])
AC_COIN_FINALIZE_FLAGS([ClpLib OsiClpLib OsiClpUnitTest])
AC_COIN_CHK_HERE([OsiLib],[OsiCommonTestLib OsiClpLib OsiClpUnitTest],[osi])
AC_COIN_CHK_HERE([ClpLib],[OsiClpLib OsiClpUnitTest],[clp])

# Here list all the files that configure should create (except for the
# configuration header file)
AC_CONFIG_FILES([Makefile
                 examples/Makefile
                 src/Makefile
                 src/Osi/Makefile
                 src/OsiClp/Makefile
                 src/OsiCommonTest/Makefile
                 test/Makefile
                 clp.pc
                 osi.pc:osi.pc.in
                 osi-clp.pc:src/OsiClp/osi-clp.pc.in
                 osi-unittests.pc:osi-unittests.pc.in])

AC_CONFIG_FILES([doxydoc/doxygen.conf])

# Here put the location and name of the configuration header file
AC_CONFIG_HEADERS([src/config.h src/config_clp.h src/OsiClp/config_osiclp.h])

# Capture git revision for display in solver header
AC_MSG_CHECKING([git revision])
CLP_GIT_HASH=`cd $srcdir && (git describe --always --dirty 2>/dev/null || echo "unknown")`
AC_MSG_RESULT([$CLP_GIT_HASH])
AC_DEFINE_UNQUOTED([CLP_GIT_HASH], ["$CLP_GIT_HASH"], [Git hash at configure time])

# Finally, we let configure write all the output...
AC_COIN_FINALIZE
