CC = gcc
CXX ?= g++
CFLAGS ?= -O0 -ggdb3

all: PoissonRecon

%.o: %.cpp
	$(CXX) -I. $(CFLAGS) -DFAST_COMPILE=1 -Wno-error=misleading-indentation $< -c -o $@

PoissonRecon: Src/PoissonRecon.o
	$(CXX) -o $@ $< -lpthread

clean:
	rm -f PoissonRecon
	make -C PNG -f GNUmakefile clean

cleaner: clean
	rm -f Src/*.o
	make -C PNG -f GNUmakefile cleaner

cleanest: cleaner
	make -C PNG -f GNUmakefile cleanest
