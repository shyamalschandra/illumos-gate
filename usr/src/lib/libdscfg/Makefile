# CDDL HEADER START
#
# The contents of this file are subject to the terms of the
# Common Development and Distribution License (the "License").
# You may not use this file except in compliance with the License.
#
# You can obtain a copy of the license at usr/src/OPENSOLARIS.LICENSE
# or http://www.opensolaris.org/os/licensing.
# See the License for the specific language governing permissions
# and limitations under the License.
#
# When distributing Covered Code, include this CDDL HEADER in each
# file and include the License file at usr/src/OPENSOLARIS.LICENSE.
# If applicable, add the following below this CDDL HEADER, with the
# fields enclosed by brackets "[]" replaced with your own identifying
# information: Portions Copyright [yyyy] [name of copyright owner]
#
# CDDL HEADER END
#
# 
# Copyright 2008 Sun Microsystems, Inc.  All rights reserved.
# Use is subject to license terms.
#

include		../Makefile.lib

HDRS=		cfg.h\
		cfg_cluster.h\
		cfg_impl.h\
		cfg_lockd.h
HDRDIR= common

SUBDIRS=	$(MACH)

ROOTDIR= $(ROOT)/usr/include/sys/nsctl

ROOTHDRS= $(HDRS:%=$(ROOTDIR)/%)

all :=		TARGET= all
clean :=	TARGET= clean
clobber :=	TARGET= clobber
install :=	TARGET= install
lint :=		TARGET= lint
_msg :=		TARGET= _msg

.KEEP_STATE:

all clean clobber install lint: $(SUBDIRS)

$(MACH):	FRC
	@cd $@; pwd; $(MAKE) $(TARGET)

install_h: $(ROOTDIR) $(ROOTHDRS)

check:  $(CHECKHDRS)

$(ROOTDIR)/%:	common/%
	$(INS.file)

$(ROOTDIR):
	$(INS.dir)


FRC:
