CC = gcc
CXX ?= g++
CFLAGS ?= -Os

all: PoissonRecon

%.o: %.cpp
	$(CXX) -I. $(CFLAGS) -DFAST_COMPILE=1 -Wno-error=misleading-indentation $< -c -o $@

PoissonRecon: Src/PoissonRecon.o
	$(CXX) -o $@ $< -lpthread
	strip $@

clean:
	rm -f PoissonRecon
	make -C PNG -f GNUmakefile clean

cleaner: clean
	rm -f Src/*.o
	make -C PNG -f GNUmakefile cleaner

cleanest: cleaner
	make -C PNG -f GNUmakefile cleanest
