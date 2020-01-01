SRC = $(wildcard *.c)
OBJ = $(SRC:.c=.o)
DEP = $(OBJ:.o=.d)
CFLAGS = -Wall -Werror -std=c99 -pedantic -DNIX -DMULTIPLE_SCORE_ENTRY -DEXTRA
LDFLAGS = -lm -lncurses

larn: $(OBJ)
	$(CC) -o $@ $^ $(LDFLAGS)

-include $(DEP)

%.d: %.c
	@$(CPP) $(CFLAGS) $< -MM -MT $(@:.d=.o) >$@

.PHONY: clean
clean:
	rm -f $(OBJ) larn

.PHONY: cleandep
cleandep:
	rm -f $(DEP)