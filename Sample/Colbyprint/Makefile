CC=gcc
CFLAGS=-I.

TARGET=helloMake
TARGET_TEST=test

$(info "+++++++starting Make++++++++")

#INCDEP=hellofun.h

##INCDEP request rebuild with Header file change.


LOCAL_SRC_FILES := $(wildcard *.c)
LOCAL_OBJ_FILES := $(patsubst %.c,%.o,$(LOCAL_SRC_FILES))


#################Test Start#################
LOCAL_SRC_FILES_TEST := \
	hellofun.c \
	dearfun.c \
	main.c

LOCAL_OBJ_FILES_TEST := $(patsubst %.c,%.o,$(LOCAL_SRC_FILES_TEST))

$(LOCAL_OBJ_FILES_TEST) : %.o : %.c
	@echo buiding : $^
	$(CC) $(CFLAGS) -c -o $@ $<

$(TARGET_TEST): $(LOCAL_OBJ_FILES_TEST)
	@echo linking : $^
	$(CC) $(CFLAGS) -o $@ $^ 
#################Test End#################

#%.o:%.c
#	@echo building : $^
#	$(CC) $(CFLAGS) -c $< -o $@ 
#
#$(TARGET): main.o hellofun.o
#	@echo linking : $^
#	$(CC) $(CFLAGS) -o $@ main.o hellofun.o


.PHONY : clean
clean : 
	rm -rf ./$(TARGET)
	find . -name "*.o" | xargs rm -rf
