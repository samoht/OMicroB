include ../../../etc/Makefile.conf

SOURCES := buttons.ml
TARGETS := buttons.byte buttons.c buttons.elf buttons.avr buttons.hex

all: $(TARGETS)

$(TARGETS): $(SOURCES)
	$(BIN)/omicrob -v $^ -mlopt -verbose -stack-size 32 -heap-size 32

flash: buttons.hex
	$(BIN)/omicrob -flash -sudo $<

simul: buttons.elf
	./$< '../../../bin/omicrob_circuit_simulator circuit.txt'

clean:
	@rm -f *.cmo *.cmi
	@rm -rf *.elf.dSYM
	@rm -f $(TARGETS)

.PHONY: all flash clean
