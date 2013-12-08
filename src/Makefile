IDIR =../include
CC=gcc
MKDIR_P = mkdir -p
CFLAGS=-I$(IDIR)

ODIR=../obj
LDIR =../lib

LIBS=-lm

.PHONY: clean all dirs hello_world

all : dirs hello_world

_DEPS = test2/test2.h
DEPS = $(patsubst %,$(IDIR)/%,$(_DEPS))

_OBJ = main.o 
OBJ = $(patsubst %,$(ODIR)/%,$(_OBJ))


$(ODIR)/%.o: %.c $(DEPS)
	$(CC) -c -o $@ $< $(CFLAGS)

hello_world : $(OBJ)
	gcc -o $@ $^ $(CFLAGS) $(LIBS)

dirs : $(ODIR)

$(ODIR) :
	$(MKDIR_P) $(ODIR)



clean:
	rm -f $(ODIR)/*.o *~ core $(INCDIR)/*~ 
