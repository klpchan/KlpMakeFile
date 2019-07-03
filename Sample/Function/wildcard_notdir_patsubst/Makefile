###learning wildcard / notdir / patsubst/

src=$(wildcard *.c ./sub/*.c)

dir=$(notdir $(src))

obj=$(patsubst %.c,%.o,$(dir))

obj2=$(dir:%.c=%.o)

all:
	@echo "src is "$(src)
	@echo "dir is "$(dir)
	@echo "obj is "$(obj)
	@echo "obj2 is "$(obj2)
