CC=gcc
CFLAGS=-I.

TARGET=helloMake
TARGET_TEST=test


HOME=.
SRCD=$(HOME)/src/
INCD=$(HOME)/inc/
OBJD=$(HOME)/obj/


CFLAGS += -I$(INCD)
$(info "+++++++starting Make++++++++")

#INCDEP=hellofun.h
##INCDEP request rebuild with Header file change.

#################Test Start#################
LOCAL_SRC_FILES_TEST := \
	$(SRCD)hellofun.c \
	$(SRCD)main.c \
	$(SRCD)dearfun.c \

LOCAL_OBJ_FILES_TEST := $(patsubst %.c,%.o,$(notdir $(LOCAL_SRC_FILES_TEST)))
$(info "LOCAL_OBJ_FILES_TEST is $(LOCAL_OBJ_FILES_TEST)")

$(OBJD)%.o : $(SRCD)%.c
	@echo buiding : $^
	$(CC) $(CFLAGS) -c -o $@ $<

$(TARGET_TEST): $(patsubst %.c,$(OBJD)%.o,$(notdir $(LOCAL_SRC_FILES_TEST)))
	@echo linking : $^
	$(CC) $(CFLAGS) -o $@ $^ 
#################Test End#################


LOCAL_SRC_FILES := $(wildcard *.c)
LOCAL_OBJ_FILES := $(patsubst %.c,%.o,$(LOCAL_SRC_FILES))

#%.o:%.c
#	@echo building : $^
#	$(CC) $(CFLAGS) -c $< -o $@ 
#
$(TARGET): $(LOCAL_OBJ_FILES)
	@echo linking : $^
	$(CC) $(CFLAGS) -o $@ $(LOCAL_OBJ_FILES)

RM=rm -rf

.PHONY : clean
clean : 
	$(RM) $(TARGET)
	$(RM) $(TARGET_TEST)
	find . -name "*.o" | xargs rm -rf
