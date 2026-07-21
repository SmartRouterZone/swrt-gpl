EXEC = regs
SRC = regs.c

ifneq ($(wildcard prebuild/$(BUILD_NAME)/$(EXEC)),)
all:
	cp prebuild/$(BUILD_NAME)/$(EXEC) $(EXEC)
else
all: $(EXEC)

$(EXEC): $(SRC)
	$(CC) $(CFLAGS) $(LDFLAGS) -o $@ $<
endif

install: all
	install -D $(EXEC) $(INSTALLDIR)/bin/$(EXEC)
	$(STRIP) $(INSTALLDIR)/bin/$(EXEC)

clean:
	-rm -f $(EXEC) *.elf *.gdb *.o
