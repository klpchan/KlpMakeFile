CC=gcc
CFLAGS=-I.

TARGET=helloMake


$(info "+++++++starting Make++++++++")

#INCDEP=hellofun.h

##INCDEP request rebuild with Header file change.

%.o:%.c
	@echo building : $^
	$(CC) $(CFLAGS) -c $< -o $@ 

$(TARGET): main.o hellofun.o
	@echo linking : $^
	$(CC) $(CFLAGS) -o $@ main.o hellofun.o


.PHONY : clean
clean : 
	rm -rf ./$(TARGET)
	find . -name "*.o" | xargs rm -rf
