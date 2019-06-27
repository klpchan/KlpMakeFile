CC=gcc
CFLAGS=-I.

INCDEP=hellofun.h

##INCDEP request rebuild with Header file change.

%.o:%.c $(INCDEP) 
	$(CC) -c -o $@ $< $(CFLAGS)

helloMake:hellomake.o hellofun.o
	$(CC) -o helloMake hellomake.o hellofun.o $(CFLAGS)
