TESTS=opusfile seeking

VPATH=../../examples


all: $(TESTS:%=%_example) $(TESTS:%=%_test)
clean:
	@rm -f $(TESTS:%=%_example) $(TESTS:%=%_test)

.PHONY: all clean

CFLAGS=$(shell pkg-config --cflags opusfile opusurl)
LDLIBS=$(shell pkg-config --libs opusfile opusurl)
infile=silence.opus

%_test: %_example
	./$^ $(infile) 2>&1 >$@

%: %.c
	$(LINK.c) $^ -o $@ $(LDLIBS)
