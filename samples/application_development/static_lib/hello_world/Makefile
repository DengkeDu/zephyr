#
# Copyright (c) 2016 Intel Corporation
#
# SPDX-License-Identifier: Apache-2.0
#

BOARD ?= qemu_x86
CONF_FILE = prj.conf

export SOURCE_DIR = $(CURDIR)
export LDFLAGS_zephyr += -L$(O)/mylib/lib
export ALL_LIBS += mylib

include ${ZEPHYR_BASE}/Makefile.inc

all qemu flash zephyr : all-mylib
clean pristine mrproper : clean-mylib
all-mylib: outputexports

all-mylib clean-mylib:
	$(MAKE) -C ../mylib O=$(O) $(@:-mylib=)
