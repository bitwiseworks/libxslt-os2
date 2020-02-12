VENDOR ?=community
BUILD_INFO=\#\#1\#\# $(shell date +'%d %b %Y %H:%M:%S')     $(shell uname -n)
BUILDLEVEL_INFO=@\#$(VENDOR):$(LIBEXSLT_VERSION)\#@$(BUILD_INFO)::::$(LIBEXSLT_MICRO_VERSION)::

AM_CPPFLAGS = -I$(top_srcdir) -I$(top_srcdir)/libxslt -I$(top_srcdir)/libexslt \
	      -I$(top_builddir) -I$(top_builddir)/libxslt \
	      -I$(top_builddir)/libexslt

AM_CFLAGS = $(LIBGCRYPT_CFLAGS) $(LIBXML_CFLAGS)

lib_LTLIBRARIES = libexslt.la

exsltincdir = $(includedir)/libexslt

exsltinc_HEADERS =                      \
	exslt.h				\
	exsltexports.h
nodist_exsltinc_HEADERS =               \
	exsltconfig.h

libexslt_la_SOURCES =                   \
	exslt.c				\
	common.c			\
	crypto.c			\
	math.c				\
	sets.c				\
	functions.c			\
	strings.c			\
	date.c				\
	saxon.c				\
	libexslt.h			\
	dynamic.c

libexslt_la_LIBADD = $(top_builddir)/libxslt/libxslt.la $(EXTRA_LIBS) $(LIBGCRYPT_LIBS) $(M_LIBS)
libexslt_la_LDFLAGS = -version-info $(LIBEXSLT_VERSION_INFO)
libexslt_la_LDFLAGS += -buildlevel '$(BUILDLEVEL_INFO)'

man_MANS = libexslt.3

EXTRA_DIST = $(man_MANS)
