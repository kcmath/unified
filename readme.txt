-----------------------------------------------------------------------
|                               g V O F                               |
|                                                                     |
|      A package of FORTRAN subroutines to implement advanced         |
|            unsplit geometric volume of fluid methods                |
|                                                                     |
|           Copyright (C) 2021 J. Lopez and J. Hernandez              |
|                                                                     |
|                                                                     |
-----------------------------------------------------------------------

-----------------------------------------------------------------------

gVOF is a collection of FORTRAN subroutines for volume of fluid
initialization, fluid advection and reconstruction of interfaces
on arbitrary grids, either structured or unstructured with convex or
non-convex cells. Routines for the aid of interface visualization are
also included.

This library is free software: you can redistribute it and/or modify
it under the terms of the GNU Lesser General Public License as
published by the Free Software Foundation, either version 3 of the
License, or (at your option) any later version.
                                                                     
This library is distributed in the hope that it will be useful, but
WITHOUT ANY WARRANTY; without even the implied warranty of
MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE. See the GNU
Lesser General Public License for more details.
                                                                     
You should have received a copy of the GNU Lesser General Public
License along with this library. If not, see
<http://www.gnu.org/licenses/>.

A reference about gVOF is the following:

J. Lopez and J. Hernandez, gVOF: An open-source package for unsplit
geometric volume of fluid methods on arbitrary grids, submitted to
Computer Physics Communications.

For more information contact joaquin.lopez@upct.es 

-----------------------------------------------------------------------
                               g V O F
-----------------------------------------------------------------------

In this directory you will find the following files: 

gvof.f       ---> source code of routines used to implement different 
             advanced unsplit geometric VOF methods with PLIC 
             reconstruction
	     
usergvof.f   ---> source code of user-defined routines and functions to
             be used inthe test programs

cgvof.h      ---> declaration of the main routines included in gvof.f
             to be used in C programs

cusergvof.h  ---> declaration of user-defined routines and functions
             included in usergvof.f to be used in C programs

testrec.f    ---> FORTRAN test program for interface reconstruction

testrec.c    ---> C test program for interface reconstruction

testvof.f    ---> FORTRAN test program for interfacial dynamics problems

testvof.c    ---> C test program for interfacial dynamics problems

gvofvardef   ---> text file with input data for the test programs

Makefile.#   ---> script examples in different platforms for the set
             of tasks to construct the gvof library and make executable
	     files for test programs in C and FORTRAN

user-manual-gvof.pdf ---> user manual in pdf format

readme       ---> this file with information about the contents of the
             supplied software package

COPYING      ---> copy of the GNU General Public License, Version 3

grids        ---> directory with sample non-uniform grids for test
             programs

c---------------------------------------------------------------------c
c---------------------------------------------------------------------c
c                              i s o a p                              c
c                                                                     c
c              A FORTRAN code for iso-surface extraction              c
c                       on arbitrary polyhedra                        c
c                                                                     c
c                     (Version 1, november 2020)                      c
c                                                                     c
c                                                                     c
c           Copyright (C) 2020 J. Lopez* and J. Hernandez**           c
c                                                                     c
c                                                                     c
c  *Dpto. Ingenieria Mecanica, Materiales y Fabricacion, UPCT. 30202, c
c   Cartagena, Spain.                                                 c
c **Dpto. Mecanica, UNED. 28040, Madrid, Spain.                       c
c                                                                     c
c   For more information, please contact: joaquin.lopez@upct.es       c
c---------------------------------------------------------------------c
c This code is free software: you can redistribute it and/or modify   c
c it under the terms of the GNU Lesser General Public License as      c
c published by the Free Software Foundation, either version 3 of the  c
c License, or (at your option) any later version.                     c
c                                                                     c
c This code is distributed in the hope that it will be useful, but    c
c WITHOUT ANY WARRANTY; without even the implied warranty of          c
c MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the       c
c GNU Lesser General Public License for more details.                 c
c                                                                     c
c You should have received a copy of the GNU Lesser General Public    c
c License along with this code.  If not, see                          c
c <http://www.gnu.org/licenses/>.                                     c
c---------------------------------------------------------------------c

Reference about isoap is the following:

[1] J. Lopez, J. Hernandez, P. Gomez, R. Zamora, C. Zanzi, F. Faura, A
new isosurface extraction method for VOF interface reconstruction on 
arbitrary grids, submitted to Computer Methods for Applied Mechanics 
and Engineering.

For more information contact joaquin.lopez@upct.es 

-----------------------------------------------------------------------
                             i s o a p
-----------------------------------------------------------------------

In this directory you will find the following files: 

isoap.f         ---> source code of the main routine used to extract
                     an isosurface from an arbitrary polyhedron and of the
		     routines used to depict the geometry of polyhedra
		     and extracted isosurfaces.

userisoap.f     ---> source code of user-defined routines and functions
                     to extract isosurfaces on grids.

cisoap.h        ---> declaration of the routines included in the isoap.f
                     file to be used in C programs.

cuserisoap.h    ---> declaration of the user-defined routines and functions
                     included in the userisoap.f file to be used in C
		     programs.

test.f          ---> FORTRAN test program for isosurface extraction on
                     single polyhedra.
		     
test.c          ---> C test program for isosurface extraction on single
                     polyhedra.
		     
testgrid.f      ---> FORTRAN test program for isosurface extraction on grids.

testgrid.c      ---> C test program for isosurface extraction on grids.

isoapvardef     ---> text file with input data for the test programs used
                     to extract isosurfaces on single polyhedra.
		     
isoapvardefgrid ---> text file with input data for the test programs used to
                     extract isosurfaces on grids.

phi             ---> text file sample with scalar values assigned to the
                     polyhedron vertices (several examples are included in
		     the ./data/ directory).
		     
phigrid         ---> text file sample with scalar values assigned to the
                     grid nodes (several examples are included in the
		     ./data/grids/ directory).
		     
Makefile.linux,
Makefile.mac    ---> script examples in different platforms for the set of
                     tasks to construct the isoap library and make
		     executable files for test programs in C and FORTRAN.
		     
user-manual-isoap.pdf -> this user manual in pdf format.

readme          ---> information about the contents of the supplied
                     software package.
		     
COPYING         ---> copy of the GNU General Public License, Version 3.

data directory  ---> data and grids with examples for the test programs.

#---------------------------------------------------------------------#
#---------------------------------------------------------------------#
#                              Makefile                               #
#---------------------------------------------------------------------#
#            Copyright (C) 2020 J. Lopez and J. Hernandez             #
#---------------------------------------------------------------------#
#      Makefile uses to construct the isoap library                   #
#      (libisoap.a) and compile the test programs in C and FORTRAN.   #
#      Type:                                                          #
#      1) 'make dim -f Makefile.linux' to generate the dim#.h files   #
#      2) 'make fortran -f Makefile.linux' for the single polyhedron  #
#         test program in FORTRAN                                     #
#      3) 'make c -f Makefile.linux' for the single polyhedron test   #
#         program in C                                                #
#      4) 'make fortran_grid -f Makefile.linux' for the grid test     #
#         program in FORTRAN                                          #
#      5) 'make c_grid -f Makefile.linux' for the grid test program   #
#         in C                                                        #
#      6) 'make all -f Makefile.linux' for the dim#.h files and all   #
#         the test programs in FORTRAN and C                          #
#      7) 'make clean -f Makefile.linux' to recompile the isoap       #
#         library in the same directory                               #
#---------------------------------------------------------------------#
# This file is part of isoap.                                         #
#                                                                     #
# isoap is free software: you can redistribute it and/or modify       #
# it under the terms of the GNU Lesser General Public License as      #
# published by the Free Software Foundation, either version 3 of the  #
# License, or (at your option) any later version.                     #
#                                                                     #
# isoap is distributed in the hope that it will be useful, but        #
# WITHOUT ANY WARRANTY; without even the implied warranty of          #
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the       #
# GNU Lesser General Public License for more details.                 #
#                                                                     #
# You should have received a copy of the GNU Lesser General Public    #
# License along with isoap. If not, see                               #
# <http://www.gnu.org/licenses/>.                                     #
#---------------------------------------------------------------------# 
#Chose your compilers:
#---------------------
# 1 for GNU compilers
# 2 for Intel compilers
# 3 for PGI compilers
#---------------------
COMPILER=1

# Parameters used for array allocation:
#--------------------------------------
NS=200
NV=240
NF=30
NP=50

ifeq "$(COMPILER)" "1"
CC=gcc
F77=gfortran
LIBS=-lm -lgfortran
OPT=-mcmodel=medium -fopenmp
endif

ifeq "$(COMPILER)" "2"
CC=icc
F77=ifort
LIBS=-lifcore
OPT=-shared-intel -fp-model source -qopenmp
endif

ifeq "$(COMPILER)" "3"
CC=pgcc
F77=pgfortran
LIBS=-pgf90libs
OPT=-mcmodel=medium -mp -Mpreprocess
endif

OPT1=-O2 -o
OPT2=-O2 -c

dim:
	@echo "      INTEGER, PARAMETER :: NS=$(NS),NV=$(NV)" > dimpol.h
	@echo "#define ns $(NS)\n#define nv $(NV)" > dimpolc.h
	@echo "      INTEGER, PARAMETER :: NF=$(NF),NP=$(NP)" > dimgrid.h
	@echo "#define nf $(NF)\n#define np $(NP)" > dimgridc.h

libisoap.a: isoap.o
	ar rv libisoap.a isoap.o

fortran: test.f userisoap.o libisoap.a
	$(F77) $(OPT) $(OPT1) test_f test.f userisoap.o libisoap.a

fortran_grid: testgrid.f userisoap.o libisoap.a
	$(F77) $(OPT) $(OPT1) testgrid_f testgrid.f userisoap.o libisoap.a

c: test.c userisoap.o libisoap.a
	$(CC) $(OPT) $(OPT1) test_c test.c userisoap.o libisoap.a $(LIBS)

c_grid: testgrid.c userisoap.o libisoap.a
	$(CC) $(OPT) $(OPT1) testgrid_c testgrid.c userisoap.o libisoap.a $(LIBS)

all: dim fortran fortran_grid c c_grid

isoap.o: isoap.f
	$(F77) $(OPT) $(OPT2) isoap.f

userisoap.o: userisoap.f
	$(F77) $(OPT) $(OPT2) userisoap.f

clean:
	rm -f *.o

#---------------------------------------------------------------------#
#---------------------------------------------------------------------#
#                              Makefile                               #
#---------------------------------------------------------------------#
#            Copyright (C) 2021 J. Lopez and J. Hernandez             #
#---------------------------------------------------------------------#
#      Makefile uses to construct the gVOF library (libgvof.a)        #
#      and compile the test programs in C and FORTRAN.                #
#      1) Install VOFTools (v5) and isoap libraries (specify below    #
#         the installation directories chosen by the user)            #
#      2) If required, change the values of the parameters used for   #
#         array dimensioning and type 'make dim -f Makefile.linux' to #
#         get the new dim#.h files                                    # 
#      Type:                                                          #
#      3) 'make testrec_c -f Makefile.linux' for the interface        #
#         reconst. test program (testrec_c) in C                      #
#      4) 'make testvof_c -f Makefile.linux' for the interfacial      #
#         dynamics test program (testvof_c) in C                      #
#      5) 'make testrec_f -f Makefile.linux' for the interface        #
#         reconst. test program (testrec_f) in FORTRAN                #
#      6) 'make testvof_f -f Makefile.linux' for the interfacial      #
#         dynamics test program (testvof_f) in FORTRAN                #
#      7) 'make all -f Makefile.linux' for the dim#.h files and all   #
#         the test programs in FORTRAN and C                          #
#      8) 'make clean -f Makefile.linux' to recompile the gVOF        #
#         library in the same directory                               #
#---------------------------------------------------------------------#
# This file is part of gVOF.                                          #
#                                                                     #
# gVOF is free software: you can redistribute it and/or modify        #
# it under the terms of the GNU Lesser General Public License as      #
# published by the Free Software Foundation, either version 3 of the  #
# License, or (at your option) any later version.                     #
#                                                                     #
# gVOF is distributed in the hope that it will be useful, but         #
# WITHOUT ANY WARRANTY; without even the implied warranty of          #
# MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the       #
# GNU Lesser General Public License for more details.                 #
#                                                                     #
# You should have received a copy of the GNU Lesser General Public    #
# License along with gVOF. If not, see <http://www.gnu.org/licenses/>.#
#---------------------------------------------------------------------#
# Parameters used for array allocation:
#--------------------------------------
NS=140
NV=200
NF=140
NP=100
NN=200
# To increase the stack and execute the code with n threads, type
#      ulimit -s unlimited
#      export OMP_NUM_THREADS=n
# being n the desired number of threads used during the code execution.
# By default, voftools-5.tgz and isoap.tgz packages are considered 
# to be downloaded and decompressed in the same directory as gvof.tgz.
# Change below if necessary.
# VOFTools directory:
VOFTOOLS_DIR=../
copy_voftools:
	cp -f $(VOFTOOLS_DIR)/voftools-5/voftools.f ./
	cp -f $(VOFTOOLS_DIR)/voftools-5/cvoftools.h ./
# isoap directory:
ISOAP_DIR=../
copy_isoap:
	cp -f $(ISOAP_DIR)/isoap/isoap.f ./
	cp -f $(ISOAP_DIR)/isoap/userisoap.f ./
	cp -f $(ISOAP_DIR)/isoap/cuserisoap.h ./
#Chose your compilers:
#---------------------
# 1 for GNU compilers
# 2 for Intel compilers
# 3 for PGI compilers
#---------------------
COMPILER=1

ifeq "$(COMPILER)" "1"
CC=gcc
F77=gfortran
LIBS=-lm -lgfortran
OPTF=-O3 -mcmodel=medium -fopenmp
OPTC=-O3 -mcmodel=medium -fopenmp
endif

ifeq "$(COMPILER)" "2"
CC=icc
F77=ifort
LIBS=-lifcore
OPTF=-O3 -mcmodel medium -shared-intel -fp-model source -qopenmp
OPTC=-O3 -mcmodel medium -shared-intel -fp-model source -qopenmp
endif

ifeq "$(COMPILER)" "3"
CC=pgcc
F77=pgfortran
LIBS=-pgf90libs
OPTF=-O3 -mcmodel=medium -mp -Mpreprocess
OPTC=-O3 -mcmodel=medium -mp -Mpreprocess
endif

dim:
	@echo "      PARAMETER (NS=$(NS),NV=$(NV))" > dim.h
	@echo "      INTEGER, PARAMETER :: NS=$(NS),NV=$(NV)" > dimpol.h
	@echo "#define ns $(NS)\n#define nv $(NV)" > dimc.h
	@echo "#define ns $(NS)\n#define nv $(NV)" > dimpolc.h
	@echo "      INTEGER, PARAMETER :: NF=$(NF),NP=$(NP),NN=$(NN)" > dimgrid.h
	@echo "#define nf $(NF)\n#define np $(NP)\n#define nn $(NN)" > dimgridc.h

libvoftools.a: voftools.o
	ar rv libvoftools.a voftools.o

libisoap.a: isoap.o
	ar rv libisoap.a isoap.o

libgvof.a: gvof.o
	ar rv libgvof.a gvof.o

testvof_f: testvof.f usergvof.o userisoap.o libgvof.a libvoftools.a libisoap.a
	$(F77) $(OPTF) testvof.f usergvof.o userisoap.o libgvof.a libvoftools.a libisoap.a -o testvof_f

testvof_c: testvof.c usergvof.o userisoap.o libgvof.a libvoftools.a libisoap.a
	$(CC) $(OPTC) testvof.c usergvof.o userisoap.o libgvof.a libvoftools.a libisoap.a $(LIBS) -o testvof_c

testrec_f: testrec.f usergvof.o userisoap.o libgvof.a libvoftools.a libisoap.a
	$(F77) $(OPTF) testrec.f usergvof.o userisoap.o libgvof.a libvoftools.a libisoap.a -o testrec_f

testrec_c: testrec.c usergvof.o userisoap.o libgvof.a libvoftools.a libisoap.a
	$(CC) $(OPTC) testrec.c usergvof.o userisoap.o libgvof.a libvoftools.a libisoap.a $(LIBS) -o testrec_c

all: dim testvof_f testvof_c testrec_f testrec_c

usergvof.o: usergvof.f
	$(F77) $(OPTF) -c usergvof.f

gvof.o: gvof.f
	$(F77) $(OPTF) -c gvof.f

voftools.o: voftools.f
	$(F77) $(OPTF) -c voftools.f

isoap.o: isoap.f
	$(F77) $(OPTF) -c isoap.f

userisoap.o: userisoap.f
	$(F77) $(OPTF) -c userisoap.f

clean:
	rm -f *.o
	rm -f *.mod
