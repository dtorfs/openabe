include ../Makefile.common

.PHONY: all clean

# relic gtest and, optionally, openssl
SYS_OPENSSL_VERSION := $(shell openssl version | cut -b 9-13 | tr -d .)
export SYS_OPENSSL_VERSION
ifeq (${SYS_OPENSSL_VERSION}, 111)
ssl:
	@echo
else
ssl:
	make -C openssl
endif

all: ssl
	mkdir -p root/lib
	make -C relic
	make -C gtest

clean:
	rm -rf root
	make -C relic clean
	make -C gtest clean
	make -C openssl clean
