#g++ -g -Wall -std=c++11 -I. -I/usr/local/include/eigen3 -I../../Utilities -I../include tcg.cc -o tcg
include ../../../../Makefile.inc
-include Makefile.inc
EIGENDIR=$(EIGEN_DIR)
MMDIR=../../Utilities
THISINCDIR=../include
LDLIBS=-lumfpack
INCLUDES= -I$(THISINCDIR) -I$(MMDIR) -I$(EIGEN_DIR) -I$(UMFPACK_INCDIR)
CPPFLAGS+=$(INCLUDES)
vpath %.h $(INCLUDES)
vpath %.hpp $(INCLUDES)

EXE=$(patsubst %.cc,%,$(wildcard *.cc))
SRCS=$(wildcard *.cc) $(wildcard *.cpp)

all: $(DEPEND) test_all $(EXE) 

clean:
	-rm -f *.o $(EXE) test_all

$(DEPEND): $(SRCS)
	-\rm $(DEPEND)
	for f in $(SRCS); do \
	$(CXX) $(STDFLAGS) $(CPPFLAGS) -MM $$f >> $(DEPEND); \
	done


