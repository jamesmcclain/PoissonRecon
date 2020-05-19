CC = gcc
CXX = g++
CFLAGS ?= -Wall -Werror -O0 -ggdb3

all: libmyjpg.a

%.o: %.c
	$(CC) -I.. $(CFLAGS) -Wno-error=misleading-indentation -fPIC $< -c -o $@

%.o: %.cpp
	$(CXX) -I.. $(CFLAGS) -Wno-error=misleading-indentation -fPIC $< -c -o $@

libmyjpg.a: ckconfig.o jccolor.o jcmainct.o jcparam.o jctrans.o jdatasrc.o jdhuff.o jdmaster.o jdsample.o jfdctfst.o jidctint.o jquant1.o jcapimin.o jcdctmgr.o jcmarker.o jcphuff.o jdapimin.o jdcoefct.o jdinput.o jdmerge.o jdtrans.o jfdctint.o jidctred.o jquant2.o jcapistd.o jchuff.o jcmaster.o jcprepct.o jdapistd.o jdcolor.o jdmainct.o jdphuff.o jerror.o jidctflt.o jmemmgr.o jutils.o jccoefct.o jcinit.o jcomapi.o jcsample.o jdatadst.o jddctmgr.o jdmarker.o jdpostct.o jfdctflt.o jidctfst.o jmemnobs.o
	ar rcs $@ $^

clean:
	rm -f libmyjpg.a

cleaner: clean
	rm -f *.o
