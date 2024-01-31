#++
# Makefile - Makefile for the Spare Time Gizmos' SBC6120 EPROM
#
# Copyright (C) 2006 by Spare Time Gizmos.  All rights reserved.
#
# This firmware is free software; you can redistribute it and/or modify it
# under the terms of the GNU General Public License as published by the Free
# Software Foundation; either version 2 of the License, or (at your option)
# any later version.
#
# This program is distributed in the hope that it will be useful, but WITHOUT
# ANY WARRANTY; without even the implied warranty of MERCHANTABILITY or
# FITNESS FOR A PARTICULAR PURPOSE.  See the GNU General Public License for
# more details.
#
# You should have received a copy of the GNU General Public License along with
# this program; if not, write to the Free Software Foundation, Inc., 59 Temple
# Place, Suite 330, Boston, MA  02111-1307  USA
#
#DESCRIPTION:
#   This Makefile will build the Spare Time Gizmos SBC6120 EPROM image from
# the PALX source file.  The result is two files, low.hex and high.hex, which
# are ready to burn into a 27C256 EPROMs...
#
#TARGETS:
#  make all	- rebuild low.hex and high.hex
#  make clean	- clean up all generated files _except_ the .hex files
#
# REVISION HISTORY:
# dd-mmm-yy	who     description
# 22-Feb-06	RLA	New file.
#--

# Tool paths and options - you can change these as necessary...
PALX=/usr/local/bin/tools/palx
PALOPTS=
PDP2HEX=/usr/local/bin/tools/pdp2hex
ECHO=/usr/bin/echo
RM=/usr/bin/rm

# The default target builds everything...
all:	low.hex high.hex

bts6120.bin:	bts6120.plx
	@$(ECHO) -e "\nAssembling SBC6120 Bootstrap ..."
	$(PALX) $(PALOPTS) -l $(@:.bin=.lst) -b $@ $<

low.hex high.hex &:	bts6120.bin
	@$(ECHO) -e "\nBuilding EPROM images ..."
	$(PDP2HEX) -s30000 -c0200 $< low.hex high.hex


# The "clean" target does what you'd expect...
clean:
	$(RM) -f bts6120.list bts6120.bin 
	$(RM) -f *.*\~ \#*.*\#
