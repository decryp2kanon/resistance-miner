AUTOMAKE_OPTIONS = subdir-objects

if WANT_JANSSON
JANSSON_INCLUDES= -I$(top_srcdir)/compat/jansson
else
JANSSON_INCLUDES=
endif

EXTRA_DIST	= example-cfg.json

SUBDIRS		= compat

bin_PROGRAMS	= sugarmaker

dist_man_MANS	= sugarmaker.1

sugarmaker_SOURCES	= elist.h miner.h compat.h \
		  cpu-miner.c util.c \
		  sha2.c \
		  random.c cpuinfo.c \
		  yespower/sha256.c yespower/yespower-opt.c res-yespower.c
sugarmaker_LDFLAGS	= $(PTHREAD_FLAGS)
sugarmaker_LDADD	= @LIBCURL@ @JANSSON_LIBS@ @PTHREAD_LIBS@ @WS2_LIBS@
sugarmaker_CPPFLAGS	= $(PTHREAD_FLAGS) @CPPFLAGS@ $(JANSSON_INCLUDES)

