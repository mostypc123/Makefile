CC := gcc
CFLAGS := -std=c11 -Wall -Wextra -O2
LDFLAGS :=

SOURCES = $(wildcard src/*.c)
OBJECTS = $(SOURCES:src/%.c=obj/%.o)
TARGET = bin/program

all: $(TARGET)

$(TARGET): $(OBJECTS) | bin
	$(CC) $(CFLAGS) -o $@ $^ $(LDFLAGS)

obj/%.o: src/%.c | obj
	$(CC) $(CFLAGS) -c -o $@ $<

bin obj:
	mkdir -p $@

clean:
	rm -rf obj bin

rebuild: clean all

run: $(TARGET)
	./$(TARGET)

.PHONY: all clean rebuild run
