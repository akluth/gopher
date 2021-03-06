# Generated automatically from Makefile.in by configure.
#********************************************************************
# $Author: jgoerzen $
# $Revision: 1.3 $
# $Date: 2002/01/11 15:55:59 $
# $Source: /var/cvs/gopher/gophfilt/Makefile.in,v $
# $State: Exp $
#
# Paul Lindner, University of Minnesota CIS.
#
# Copyright 1991, 1992 by the Regents of the University of Minnesota
# see the file "Copyright" in the distribution for conditions of use.
#********************************************************************
# MODULE: Makefile
# Makefile for gopher filter client
#*********************************************************************
# Revision History:
# $Log: Makefile.in,v $
# Revision 1.3  2002/01/11 15:55:59  jgoerzen
#   * Using $(INSTALL) from subdirectories broke on systems
#     where install-sh was used because $(INSTALL) would always
#     resolve to ./install-sh.  Replaced all instances of
#     $(INSTALL) with /usr/bin/install -c (autoconf would provide the correct
#     path) and removed INSTALL from Makefile.config.  Reported
#     by Don Fike <fike@cs.utk.edu> on Solaris 2.6.
#   * Updated our copy of install-sh with the one from
#     a current automake.
#
# Revision 1.2  2002/01/08 17:36:14  jgoerzen
# Finally builds!
#
# Changes:
#
#   * config.h.in: rebuilt by autoheader
#
#   * configure: rebuilt by autoconf
#
#   * configure.in:
#     * Added REGEXLIBS test for NetBSD -- look for re_comp in -lcompat
#     * Added checkes for term.h, re_comp.h, regex.h
#
#   * gopher/ourutils.c, gopher/CURcurses.c: Use term.h check
#
#   * gopher/Makefile.in, gopherd/Makefile.in, gophfilt/Makefile.in:
#     * Use REGEXLIBS
#
#   * gopher/globals.h, gopher/gopher.c: Remove sys_errlist
#
#   * object/GSgopherobj.c: Removed <regex.h> #include, now use
#     "Regex.h" that has proper regex determining logic
#
#   * object/Regex.h: Moved regex.h include to here.  Make it conditional
#     based on configure test.  Add conditional re_comp.h include.
#
# Revision 1.1.1.1  2000/08/19 00:28:56  jgoerzen
# Import from UMN Gopher 2.3.1 after GPLization
#
# Revision 1.1  1996/01/06  00:33:31  lindner
# rel 2.3
#
#********************************************************************/

srcdir = .
top_srcdir = ..

include ../Makefile.config

OBJS	= gophfilt.o

CCFLAGS	= $(OPT) $(INTLOPTS) -I.. -I$(top_srcdir) -I$(top_srcdir)/object

TARGET	= gophfilt

all:	$(TARGET)

.c.o:
	$(CC) $(CCFLAGS) -c $<

../object/libgopher.a:
	(cd ..; $(MAKE) $(MFLAGS) objects)

$(TARGET) : $(OBJS) ../object/libgopher.a
	$(CC) $(LDFLAGS) -o $@ $(OBJS) ../object/libgopher.a  -lutil -lelf -lm  

install : all
	-mv $(CLIENTDIR)/$(TARGET) $(CLIENTDIR)/$(TARGET).old
	/usr/bin/install -c $(TARGET) $(CLIENTDIR)

clean:
	-rm -f $(TARGET) $(OBJS) *.out *~ core

$(OBJS): $(srcdir)/../object/GSgopherobj.h $(srcdir)/../conf.h
