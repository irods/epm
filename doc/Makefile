#
# "$Id: Makefile.in 666 2006-04-04 22:46:25Z mike $"
#
#   Makefile for the ESP Package Manager (EPM) documentation.
#
#   Copyright 1999-2006 by Easy Software Products, all rights reserved.
#
#   This program is free software; you can redistribute it and/or modify
#   it under the terms of the GNU General Public License as published by
#   the Free Software Foundation; either version 2, or (at your option)
#   any later version.
#
#   This program is distributed in the hope that it will be useful,
#   but WITHOUT ANY WARRANTY; without even the implied warranty of
#   MERCHANTABILITY or FITNESS FOR A PARTICULAR PURPOSE.  See the
#   GNU General Public License for more details.
#

#
# Programs...
#

CC	=	gcc
HTMLDOC	=	
NROFF	=	/usr/bin/nroff
RM	=	/bin/rm -f


#
# Man page generation...
#

.SUFFIXES:	.html .man
.man.html:
	$(RM) $@
	./mantohtml $< >$@


#
# Targets...
#

MANPAGES	=	epm.html epminstall.html mkepmlist.html setup.html
HTMLFILES	=	preface.html 1-intro.html 2-building.html \
			3-packaging.html 4-advanced.html 5-examples.html \
			a-license.html b-manpages.html c-reference.html \
			d-relnotes.html $(MANPAGES)

all:	$(MANPAGES)	epm-book.html

clean:
	$(RM) epm-book.html $(MANPAGES) mantohtml mantohtml.o

epm-book.html:	$(HTMLFILES) epm-book.book
	$(HTMLDOC) --batch epm-book.book -f epm-book.html

mantohtml:	mantohtml.o
	$(CC) -o $@ mantohtml.o

$(MANPAGES):	mantohtml


#
# End of "$Id: Makefile.in 666 2006-04-04 22:46:25Z mike $".
#
