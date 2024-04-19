CXX = g++-11
CXXFLAGS = -std=c++20 -Wall -g -MMD -Werror=vla
SOURCES = $(wildcard *.cpp)
OBJECTS = ${SOURCES:.cpp=.o}
DEPENDS = ${OBJECTS:.o=.d}
EXEC=monopoly

$(EXEC): $(OBJECTS)
	$(CXX) $(CXXFLAGS) $(OBJECTS) -o $(EXEC)

%.o: %.cc 
	$(CXX) -c -o $@ $< $(CXXFLAGS)

-include ${DEPENDS}

.PHONY: clean 
clean:
	rm -f $(OBJECTS) $(DEPENDS) $(EXEC)
