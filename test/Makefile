PHONY: all

CC := gcc
CFLAGS := -DMACRO_DEF -DMACRO_DEF_WITH_VAL=1 -D MACRO_DEF_WITH_SPACE
CFLAGS += -I./ -I include_path_after_whitespace -I/a/b/c
all: a.out 
SRCS := $(addsuffix _src.c, 0 1 2 3 4 5 6 7)
OBJS := $(SRCS:%.c=%.o)
a.out:  $(OBJS)
	@echo "ENV[CC]=$(CC)"
	@echo "ENV[CC]=$(CXX)"
	$(CC) -o $@ $^ $(CFLAGS)
#	@gcc -o $@ $^

%_src.o : %_src.c
	@$(CC) -c -o $@ $< $(CFLAGS)

clean:
	-rm a.out $(OBJS)

