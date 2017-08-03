NAME = twemproxy
VERSION = 0.4.1
ITERATION = 1
DOWNLOAD_VERSION = 49a96c4884332524d78eab8774f0229aa4398431
SOURCE_URL = https://github.com/mattrobenolt/twemproxy/archive/$(DOWNLOAD_VERSION).tar.gz
FPM_SOURCE = dir

PACKAGE_URL = https://github.com/mattrobenolt/twemproxy
PACKAGE_DESCRIPTION = A fast, light-weight proxy for memcached and redis

include ../include/base.mk

export DESTDIR

extract: fetch default_build
	cd $(BUILDDIR); \
	tar xzf $(CACHEDIR)/$(notdir $(SOURCE_URL)); \
	mv twemproxy-$(DOWNLOAD_VERSION) twemproxy-$(VERSION)

build: extract
	cd $(BUILDDIR)/twemproxy-$(VERSION); \
	autoreconf -fvi && \
	./configure --prefix=/usr && make && \
	env DESTDIR=$(DESTDIR) make install
