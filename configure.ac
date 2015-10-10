#                                               -*- Autoconf -*-
# Process this file with autoconf to produce a configure script.

AC_PREREQ([2.69])
AC_INIT([libGLUES], [1.5])
AC_CONFIG_SRCDIR([src/glu.h])
AM_INIT_AUTOMAKE([foreign subdir-objects])
AM_SILENT_RULES([yes])
LT_INIT

# Checks for programs.
AC_PROG_CXX
AC_PROG_CC

# Checks for libraries.
AC_CHECK_LIB([GLESv1_CM], [glDrawArrays], [], [AC_MSG_ERROR([an OpenGL ES library was not found])])
AC_CHECK_LIB([SDL2], [SDL_GL_CreateContext], [], [AC_MSG_ERROR([the SDL2 library was not found])])

# Checks for header files.
AC_CHECK_HEADERS([limits.h memory.h stddef.h stdlib.h string.h])
AC_CHECK_HEADER([GLES/gl.h], [], [AC_MSG_ERROR([OpenGL ES headers were not found])])
AC_CHECK_HEADER([SDL2/SDL_opengles.h], [], [AC_MSG_ERROR([SDL2 headers were not found])])

# Checks for typedefs, structures, and compiler characteristics.
AC_CHECK_HEADER_STDBOOL
AC_C_INLINE
AC_TYPE_SIZE_T

# Checks for library functions.
AC_CHECK_FUNCS([bzero floor memset select sqrt])

# Right now we only support SDL2
AM_CFLAGS="-D__USE_SDL_GLES__ -DLIBRARYBUILD"
AM_CXXFLAGS=$AM_CFLAGS
AC_SUBST(AM_CFLAGS)
AC_SUBST(AM_CXXFLAGS)

# Finish
AC_CONFIG_FILES([Makefile
                 docs/Makefile
                 src/Makefile])
AC_OUTPUT
