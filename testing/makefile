IDIR =../include
CC=g++
CFLAGS=-I$(IDIR) -std=c++11 -O3 -Wall -Wextra -pedantic

ODIR=obj
LDIR =../lib
LIBS=-lm -lblas -llapack -larpack

_DEPS = Figure.h Spline.h keycpp.h vector_k.h Matrix.h kiss_fft.h gnuplot_i.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = test_ode45.o test_eigs.o test_eig.o test_sprintf.o test_fft.o test_mat.o test_vec.o test.o
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))

$(ODIR)/%.o: %.cpp $(DEPS) ; $(CC) -c -o $@ $< $(CFLAGS)

test: $(OBJ) ; $(CC) -o $@ $^ $(CFLAGS) -L$(LDIR) $(LIBS)

.PHONY: clean

clean: ; rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~ ./test
