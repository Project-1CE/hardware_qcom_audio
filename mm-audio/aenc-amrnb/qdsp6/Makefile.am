AM_CFLAGS = -Wundef \
        -Wstrict-prototypes \
        -Wno-trigraphs \
        -g  -O0 \
        -fno-inline \
        -fno-short-enums \
        -fpic \
        -I inc \
        -I ${WORKSPACE}/hardware/qcom/media/mm-core/inc/

# required pre-processor flags
AM_CPPFLAGS = -D__packed__=
AM_CPPFLAGS += -DIMAGE_APPS_PROC
AM_CPPFLAGS += -DFEATURE_Q_SINGLE_LINK
AM_CPPFLAGS += -DFEATURE_Q_NO_SELF_QPTR
AM_CPPFLAGS += -DFEATURE_LINUX
AM_CPPFLAGS += -DFEATURE_NATIVELINUX -Dstrlcpy=g_strlcpy
AM_CPPFLAGS += -DFEATURE_DSM_DUP_ITEMS
AM_CPPFLAGS += -I ${WORKSPACE}/hardware/qcom/media/mm-core/inc/
AM_CPPFLAGS += -I $(PKG_CONFIG_SYSROOT_DIR)/usr/include/audio-kernel

AM_CPPFLAGS += -g
AM_CPPFLAGS += -DNDEBUG
AM_CPPFLAGS += -Iinc

c_sources = src/omx_amr_aenc.cpp \
            src/aenc_svr.c

lib_LTLIBRARIES = libOmxAmrEnc.la
libOmxAmrEnc_la_CC = @CC@
libOmxAmrEnc_la_SOURCES = $(c_sources)
libOmxAmrEnc_la_LIBADD  = -lcutils -llog
libOmxAmrEnc_la_CFLAGS = $(AM_CFLAGS) $(AM_CPPFLAGS) $(GLIB_CFLAGS) -include glib.h -Dstrlcpy=g_strlcpy
libOmxAmrEnc_la_CPPFLAGS = $(AM_CFLAGS) $(AM_CPPFLAGS) $(GLIB_CFLAGS) -include glib.h -Dstrlcpy=g_strlcpy
libOmxAmrEnc_la_LDFLAGS = $(GLIB_LIBS) -shared -avoid-version
