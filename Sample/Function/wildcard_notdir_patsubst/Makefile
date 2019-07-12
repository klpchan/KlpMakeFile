###learning wildcard / notdir / patsubst/

src=$(wildcard *.c *.o ./sub/*.c ./sub/*.o)

notdir=$(notdir $(src))

dir:=$(dir $(src))

obj=$(patsubst %.c,%.o,$(dir))

obj2=$(dir:%.c=%.o)

suffix=$(suffix $(src))

basename=$(basename $(src))

addsuffix=$(addsuffix .suffix,$(basename))

addprefix=$(addprefix  prefix, $(basename))

join=$(join $(basename), $(suffix))


foreach := $(foreach n,$(basename),$(n)fe)

all:
	@echo "src is "$(src)
	@echo "dir is "$(dir)
	@echo "not dir is "$(notdir)
	@echo "obj is "$(obj)
	@echo "obj2 is "$(obj2)
	@echo "basename is "$(basename)
	@echo "suffix is "$(suffix)
	@echo "addsuffix is "$(addsuffix)
	@echo "addprefix is "$(addprefix)
	@echo "join is "$(join)
	@echo "foreach is "$(foreach)
