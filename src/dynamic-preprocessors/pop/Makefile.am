## $Id
AUTOMAKE_OPTIONS=foreign no-dependencies

INCLUDES = -I../include -I${srcdir}/../libs

libdir = ${exec_prefix}/lib/snort_dynamicpreprocessor

lib_LTLIBRARIES = libsf_pop_preproc.la

libsf_pop_preproc_la_LDFLAGS = -shared -export-dynamic -module @XCCFLAGS@
if SO_WITH_STATIC_LIB
libsf_pop_preproc_la_LIBADD = ../libsf_dynamic_preproc.la
else
nodist_libsf_pop_preproc_la_SOURCES = \
../include/sf_dynamic_preproc_lib.c \
../include/mempool.c \
../include/sf_sdlist.c \
../include/util_unfold.c \
../include/sf_base64decode.c \
../include/sf_email_attach_decode.c \
../include/sfPolicyUserData.c
endif

libsf_pop_preproc_la_SOURCES = \
pop_config.c \
pop_config.h \
pop_log.c \
pop_log.h \
pop_util.c \
pop_util.h \
snort_pop.c \
snort_pop.h \
spp_pop.c \
spp_pop.h 

EXTRA_DIST = \
sf_pop.dsp

all-local:
	$(MAKE) DESTDIR=`pwd`/../build install-libLTLIBRARIES

