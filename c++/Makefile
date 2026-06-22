CXX := g++
CXXFLAGS := -std=c++20 -Wall -Wextra -O2
LDFLAGS :=

SOURCES = $(wildcard src/*.cpp)
OBJECTS = $(SOURCES:src/%.cpp=obj/%.o)
TARGET = bin/program

all: $(TARGET)

$(TARGET): $(OBJECTS) | bin
	$(CXX) $(CXXFLAGS) -o $@ $^ $(LDFLAGS)

obj/%.o: src/%.cpp | obj
	$(CXX) $(CXXFLAGS) -c -o $@ $<

bin obj:
	mkdir -p $@

clean:
	rm -rf obj bin

rebuild: clean all

run: $(TARGET)
	./$(TARGET)

.PHONY: all clean rebuild run
