# Makefile
# GNU makefile for single and parallel test programs using MMSP
# Questions/comments to gruberja@gmail.com (Jason Gruber)

# includes
incdir = ../include

# compilers/flags
compiler = g++
flags = -O3 -I $(incdir)
pcompiler = mpic++
pflags = -O3 -I $(incdir) -include mpi.h 

# dependencies
core = $(incdir)/MMSP.hpp \
       $(incdir)/MMSP.utility.hpp \
       $(incdir)/MMSP.grid.hpp \
       $(incdir)/MMSP.scalar.hpp \
       $(incdir)/MMSP.vector.hpp \
       $(incdir)/MMSP.sparse.hpp 

# the program
test: test.cpp $(core)
	$(compiler) $(flags) $< -o $@

parallel: test.cpp $(core)
	$(pcompiler) $(pflags) $< -o $@

clean:
	rm -f test parallel
