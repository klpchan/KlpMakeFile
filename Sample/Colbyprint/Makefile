TARGET=helloMake
TARGET_TEST=test

HOME=.
SRCD=$(HOME)/src/
INCD=$(HOME)/inc/
OBJD=$(HOME)/obj/

CC=gcc
CFLAGS=-I. -I$(INCD)
$(info "+++++++starting Make++++++++")

#INCDEP=hellofun.h
##INCDEP request rebuild with Header file change.

.PHONY : all
all : $(TARGET)

#################Test Start#################
LOCAL_SRC_FILES_TEST := \
	$(SRCD)hellofun.c \
	$(SRCD)main.c \
	$(SRCD)dearfun.c \

LOCAL_OBJ_FILES_TEST := $(patsubst %.c,$(OBJD)%.o,$(notdir $(LOCAL_SRC_FILES_TEST)))
#$(info "LOCAL_OBJ_FILES_TEST is $(LOCAL_OBJ_FILES_TEST)")

#1 common mode
#$(OBJD)%.o : $(SRCD)%.c
#	@echo buiding : $^
#	$(CC) $(CFLAGS) -c -o $@ $<

#2 static mode
$(LOCAL_OBJ_FILES_TEST) : $(OBJD)%.o : $(SRCD)%.c
	@echo buiding : $^
	$(CC) $(CFLAGS) -c -o $@ $<

$(TARGET_TEST): $(LOCAL_OBJ_FILES_TEST)
	@echo "linking : $^ to $@"
	$(CC) $(CFLAGS) -o $@ $^ 
#################Test End###################


#################Target Start#################

LOCAL_SRC_FILES := $(wildcard *.c $(SRCD)*.c)
LOCAL_OBJ_FILES := $(patsubst %.c,$(OBJD)%.o,$(notdir $(LOCAL_SRC_FILES)))

$(TARGET): $(LOCAL_OBJ_FILES)
	@echo "linking : $^ to $@"
	$(CC) $(CFLAGS) -o $@ $(LOCAL_OBJ_FILES)

#################Target End#################
RM=rm -rf

.PHONY : clean
clean :
	$(RM) $(TARGET)
	$(RM) $(TARGET_TEST)
	find . -name "*.o" | xargs rm -rf
