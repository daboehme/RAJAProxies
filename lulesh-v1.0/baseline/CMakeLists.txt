###############################################################################
#
# Copyright (c) 2017, Lawrence Livermore National Security, LLC.
#
# Produced at the Lawrence Livermore National Laboratory
#
# All rights reserved.
#
# This file is part of the RAJA Proxy App Suite
#
###############################################################################

blt_add_executable(
  NAME lulesh-v1.0-baseline-seq.exe
  SOURCES lulesh.cpp
  DEPENDS_ON RAJA)

target_compile_options(
  lulesh-v1.0-baseline-seq.exe
  PRIVATE
  -Wno-unknown-pragmas)

if(ENABLE_OPENMP)
  blt_add_executable(
    NAME lulesh-v1.0-baseline-omp.exe
    SOURCES lulesh.cpp
    DEPENDS_ON RAJA openmp)
endif()

