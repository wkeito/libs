# Copyright (C) 2015 PSP2SDK Project
#
# This Source Code Form is subject to the terms of the Mozilla Public
# License, v. 2.0. If a copy of the MPL was not distributed with this
# file, You can obtain one at http://mozilla.org/MPL/2.0/.

include $(top_srcdir)/stubs/common.mk

PREFIX = _SceLocationExtension-0001_
ENTRIES_PREFIX = $(PREFIX)F00_

NIDS = 0x277da915 0x46d2f044 0x82de9bf8

ENTRIES = $(call GET_ENTRIES,$(ENTRIES_PREFIX),$(NIDS))

lib_LIBRARIES = libSceLocationExtension_stub.a
libSceLocationExtension_stub_a_SOURCES = SceLibLocationExtension_stub.S
am_libSceLocationExtension_stub_a_OBJECTS = $(call GET_OBJECTS,$(PREFIX),$(ENTRIES))

$(PREFIX)head.o: $(libSceLocationExtension_stub_a_SOURCES)
	$(COMPILE_HEAD)

$(PREFIX)NIDS.o: $(libSceLocationExtension_stub_a_SOURCES)
	$(COMPILE_NIDS)

$(ENTRIES): $(libSceLocationExtension_stub_a_SOURCES)
	$(call COMPILE_ENTRIES,$(ENTRIES_PREFIX))
