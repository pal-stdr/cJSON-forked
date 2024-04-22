# subdir-objects: With this option, Automake places object files into subdirectories corresponding to their source file's directory, which helps avoid filename clashes and keeps the build directory cleaner.
# foreign: Tells Automake not to require all GNU files (NEWS, README, AUTHORS, ChangeLog); this is useful for non-GNU projects.
# 1.16: Specifies the minimum version of Automake required for processing this Makefile.am.
AUTOMAKE_OPTIONS = subdir-objects foreign 1.16
ACLOCAL_AMFLAGS = -I m4

#############################################################################


# Specify the target library
lib_LTLIBRARIES = libcJSON.la

#############################################################################


pkginclude_HEADERS = \
	cJSON.h \
	cJSON_Utils.h

#############################################################################


pkgconfigdir = $(pkgconfig_libdir)
pkgconfig_DATA = $(pkgconfig_libfile)

#############################################################################

DISTCLEANFILES = \
	cJSON.pc \
	cJSON.pc.in \
	cJSON-uninstalled.sh \
	cJSON-uninstalled.pc

install-data-local:
	@test -z "$(DESTDIR)$(libdir)/$(PACKAGE_NAME)" || $(mkdir_p) "$(DESTDIR)$(libdir)/$(PACKAGE_NAME)"


# Include directories for header files, if needed (optional)
# AM_CPPFLAGS =  -I.
AM_CPPFLAGS = -I$(top_builddir)/include -I$(top_srcdir)/
AM_CFLAGS = $(CFLAGS_WARN)

#############################################################################

libcJSON_la_CPPFLAGS = -I$(top_builddir)/include -I$(top_srcdir)/
libcJSON_la_SOURCES = \
	cJSON.c \
	cJSON_Utils.c


MAINTAINERCLEANFILES 	=			\
	Makefile.in				\
	aclocal.m4				\
	configure				\
	stamp-h.in			\
	$(AUX_DIST)


EXTRA_DIST = CHANGELOG.md CONTRIBUTORS.md LICENSE LICENSE_ADDITIONAL fuzzing tests Docs




# # Specify any compiler flags you might need.
# # This is optional and can be adjusted as per your project's needs.
# AM_CFLAGS = -Wall


# distclean-local:
#     rm -R autom4te.cache/
#     rm aclocal.m4 config.sub configure ltmain.sh m4/libtool.m4 m4/lt~obsolete.m4 m4/ltoptions.m4 m4/ltsugar.m4 m4/ltversion.m4 depcomp compile fuzzing Makefile.in config.guess install-sh missing





