#
# This file and its contents are supplied under the terms of the
# Common Development and Distribution License ("CDDL"), version 1.0.
# You may only use this file in accordance with the terms of version
# 1.0 of the CDDL.
#
# A full copy of the text of the CDDL should have accompanied this
# source.  A copy of the CDDL is also available via the Internet at
# http://www.illumos.org/license/CDDL.
#

#
# Copyright 2015 Aurelien Larcher
#

include ../../../make-rules/shared-macros.mk

COMPONENT_NAME=           xditview
COMPONENT_VERSION=        1.0.3
COMPONENT_FMRI=           document/viewer/xditview
COMPONENT_CLASSIFICATION= System/X11
COMPONENT_SUMMARY=  xditview - display ditroff output
COMPONENT_SRC=      $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=  $(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH= \
  sha256:30f0eaee7e740a080cfb29e3f57a1202e6a5a19a0bfb099c89060cc2986e0328
COMPONENT_ARCHIVE_URL= \
  http://www.x.org/releases/individual/app/xditview-1.0.3.tar.bz2
COMPONENT_PROJECT_URL = http://www.x.org/
COMPONENT_LICENSE=      MIT License
COMPONENT_LICENSE_FILE= xditview.license

include $(WS_TOP)/make-rules/prep.mk
include $(WS_TOP)/make-rules/configure.mk
include $(WS_TOP)/make-rules/ips.mk

PATH=/usr/gnu/bin:/usr/bin

build: $(BUILD_32_and_64)

install: $(INSTALL_32_and_64)

test: $(NO_TESTS)


REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += system/library/math
REQUIRED_PACKAGES += x11/library/libx11
REQUIRED_PACKAGES += x11/library/libxmu
REQUIRED_PACKAGES += x11/library/toolkit/libxaw7
REQUIRED_PACKAGES += x11/library/toolkit/libxt
