CC = g++
CCOPT = -Wall -c
LINK = g++
LINKOPT = 
PACK = ar
PACKOPT = rc
DOPACK = $(PACK) $(PACKOPT) $@ $?
DOLINK = $(LINK) $(LINKOPT) -o $@ $?

CMLIB = cmlib.a

%.o: %.cpp
	$(CC) $(CCOPT) $<

all: $(CMLIB)

$(CMLIB): file_functs.o io_functs.o
	$(DOPACK) 
	
file_functs.test: file_functs.cpp file_functs.h
	g++ -o $@ $< -DTEST_FILE_FUNCTS
io_functs.test: io_functs.cpp io_functs.h
	g++ -o $@ $< -DTEST_IO_FUNCTS

clean:
	rm -f *.test *.o $(CMLIB)
