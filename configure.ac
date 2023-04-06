# Autoconf requirements
# Force autoconf to be at least this version number:
AC_PREREQ([2.71])
# Initialize, but use more options.  Note parameters brackets and whitespace.
AC_INIT([ata],[1.0],[w7og@yahoo.com])
# Safety check - list a source file that wouldn't be in other directories:
AC_CONFIG_SRCDIR([ata.for])
# Put autotools auxiliary files in a subdir, so they don't clutter top dir:
AC_CONFIG_AUX_DIR([build-aux])

AC_CONFIG_MACRO_DIR([m4])

AC_CANONICAL_TARGET
# AC_CANONICAL_HOST is needed to access the 'host_os' variable
AC_CANONICAL_HOST

build_linux=no
build_windows=no
build_freebsd=no
build_darwin=no

# Detect the target system
case "${host_os}" in
    linux*)
        build_linux=yes
        ;;
    cygwin*|mingw*)
        build_windows=yes
        ;;
    freebsd*)
        build_freebsd=yes
        ;;
    darwin*)
        build_darwin=yes
        ;;
    *)
        AC_MSG_ERROR(["OS $host_os is not supported"])
        ;;
esac

# Pass the conditionals to automake
AM_CONDITIONAL([LINUX], [test "$build_linux" = "yes"])
AM_CONDITIONAL([WINDOWS], [test "$build_windows" = "yes"])
AM_CONDITIONAL([FREEBSD], [test "$build_freebsd" = "yes"])
AM_CONDITIONAL([DARWIN], [test "$build_darwin" = "yes"])

#AM_GNU_GETTEXT([external])
#AM_GNU_GETTEXT_VERSION(0.17)
# see GNU autoconf archive = perdefined macros
if test "$build_linux" = "yes"; then
AX_GENERATE_CHANGELOG
fi

# Enable "automake" to simplify creating makefiles:
AM_INIT_AUTOMAKE([1.11 subdir-objects -Wall -Werror])
# Look for a fortran compiler:
AC_PROG_CC
AC_PROG_F77([gfortran mpif90])
AC_PROG_FC([gfortran mpif90])

ata_version_1=`echo $PACKAGE_VERSION | cut -d . -f 1`
ata_version_2=`echo $PACKAGE_VERSION | cut -d . -f 2`
ata_version_3=`echo $PACKAGE_VERSION | cut -d . -f 3`
ata_version=$ata_version_1.$ata_version_2.$ata_version_3
AC_DEFINE_UNQUOTED(ATA_VERSION,  "$ata_version",  [ ATA version string.  ])
AC_DEFINE_UNQUOTED(ATA_VERSION_1, $ata_version_1, [ ATA version level 1. ])
AC_DEFINE_UNQUOTED(ATA_VERSION_2, $ata_version_2, [ ATA version level 2. ])
AC_DEFINE_UNQUOTED(ATA_VERSION_3, $ata_version_3, [ ATA version level 3. ])
AC_SUBST(ATA_VERSION, $ata_version)

AC_CONFIG_FILES([Makefile])
AC_OUTPUT


# Print configuration summary

cat <<EOF


Configuration summary
=====================

ata is now configured as follows:

* Compilation environment

  CC       = $CC
  CFLAGS   = $CFLAGS
  CPP      = $CPP
  CPPFLAGS = $CPPFLAGS
  LD       = $LD
  LDFLAGS  = $LDFLAGS
  LIBS     = $LIBS
  F77      = $F77
  FFLAGS   = $FFLAGS

* ata options


EOF

