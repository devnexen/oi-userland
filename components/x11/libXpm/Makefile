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

COMPONENT_NAME=           libXpm
COMPONENT_VERSION=        3.5.12
COMPONENT_FMRI=           x11/library/libxpm
COMPONENT_CLASSIFICATION= System/X11
COMPONENT_SUMMARY=  libXpm - X Pixmap library 
COMPONENT_SRC=      $(COMPONENT_NAME)-$(COMPONENT_VERSION)
COMPONENT_ARCHIVE=  $(COMPONENT_SRC).tar.bz2
COMPONENT_ARCHIVE_HASH= \
  sha256:fd6a6de3da48de8d1bb738ab6be4ad67f7cb0986c39bd3f7d51dd24f7854bdec
COMPONENT_ARCHIVE_URL= \
  http://www.x.org/releases/individual/lib/$(COMPONENT_ARCHIVE)
COMPONENT_PROJECT_URL = http://www.x.org/
COMPONENT_LICENSE=      MIT License
COMPONENT_LICENSE_FILE= libXpm.license

include $(WS_MAKE_RULES)/prep.mk
include $(WS_MAKE_RULES)/configure.mk
include $(WS_MAKE_RULES)/ips.mk

PATH=/usr/gnu/bin:/usr/bin

COMPONENT_PREP_ACTION = ( cp -r $(COMPONENT_DIR)/srcs/* $(SOURCE_DIR) && \
                          cd $(@D) &&  autoreconf -f  -i )

CONFIGURE_DEFAULT_DIRS=no
CONFIGURE_OPTIONS+= --mandir=$(CONFIGURE_MANDIR)
CONFIGURE_OPTIONS+= --bindir=$(USRBINDIR$(BITS))
CONFIGURE_OPTIONS+= --libdir=$(CONFIGURE_LIBDIR.$(BITS))
CONFIGURE_OPTIONS+= --sbindir=$(USRSBINDIR$(BITS))
CONFIGURE_OPTIONS+= --disable-static
CONFIGURE_OPTIONS+= --enable-shared

LD_OPTIONS_SO += -M$(COMPONENT_DIR)/mapfile-vers


build: $(BUILD_32_and_64)

install: $(INSTALL_32_and_64)

test: $(NO_TESTS)

# Build dependencies
REQUIRED_PACKAGES += x11/header/xproto
REQUIRED_PACKAGES += x11/header/xextproto

# Auto-generated dependencies
REQUIRED_PACKAGES += system/library
REQUIRED_PACKAGES += x11/library/libx11
REQUIRED_PACKAGES += x11/library/libxext
REQUIRED_PACKAGES += x11/library/toolkit/libxt
