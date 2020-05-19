CC = gcc
CFLAGS ?= -Wall -Werror -O0 -ggdb3

all: libmypng.a

%.o: %.c
	$(CC) -I.. $(CFLAGS) -Wno-error=misleading-indentation -fPIC $< -c -o $@

libmypng.a: png.o pngerror.o pnggccrd.o pngget.o pngmem.o pngpread.o pngread.o pngrio.o pngrtran.o pngrutil.o pngset.o pngtest.o pngtrans.o pngvcrd.o pngwio.o pngwrite.o pngwtran.o pngwutil.o
	ar rcs $@ $^

clean:
	rm -f libmypng.a

cleaner: clean
	rm -f *.o

cleanest: cleaner
