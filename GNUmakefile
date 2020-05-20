CC = gcc
CXX ?= g++
CFLAGS ?= -O0 -ggdb3

all: PoissonRecon

%.o: %.cpp
	$(CXX) -I. $(CFLAGS) -Wno-error=misleading-indentation -fPIC $< -c -o $@

PNG/libmypng.a:
	make -C PNG -f GNUmakefile

PoissonRecon: Src/PoissonRecon.o PNG/libmypng.a
	$(CXX) -DFAST_COMPILE=1 -I. -L PNG -o $@ $< -ljpeg -lmypng -lz -lpthread

clean:
	rm -f PoissonRecon
	make -C PNG -f GNUmakefile clean

cleaner: clean
	rm -f Src/*.o
	make -C PNG -f GNUmakefile cleaner

cleanest: cleaner
	make -C PNG -f GNUmakefile cleanest
