# Generated automatically from Makefile.in by configure.
include ../Makefile.config

TARGET = gopherd.conf.5 gopherd.8 gopherindex.8 gopher.1 \
	 gophfilt.1 gopherrc.5

install: $(TARGET)
	/usr/bin/install -c  gopherd.conf.5 $(MAN5DIR)
	/usr/bin/install -c  gopherd.8 $(MAN8DIR)
	/usr/bin/install -c  gopherindex.8 $(MAN8DIR)
	/usr/bin/install -c  gopher.1 $(MAN1DIR)
	/usr/bin/install -c  gophfilt.1 $(MAN1DIR)
	/usr/bin/install -c  gopherrc.5 $(MAN5DIR)

all:
	$(NROFF)    gopherd.conf.5 >gopherd.conf.cat
	$(NROFF)    gopherd.8      >gopherd.cat
	$(NROFF)    gopherindex.8  >gopherindex.cat
	$(NROFF)    gopher.1       >gopher.cat
	$(NROFF)    gophfilt.1     >gophfilt.cat
	$(NROFF)    gopherrc.5     >gopherrc.cat

clean:
	-rm -f *~
