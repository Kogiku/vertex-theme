AC_INIT(
    [vertex-theme],
    [20200130],
    [https://github.com/horst3180/Vertex-theme/issues],
    [vertex-theme],
    [https://github.com/horst3180/Vertex-theme],
    []
)

AC_CONFIG_AUX_DIR([build-aux])
AC_CONFIG_MACRO_DIR([m4])
AM_INIT_AUTOMAKE([foreign])
AC_PROG_MKDIR_P

VERTEX_ENABLE([CINNAMON],    [cinnamon],    [Cinnamon],     [disable])
VERTEX_ENABLE([DARK],        [dark],        [Vertex Dark],  [disable])
VERTEX_ENABLE([GNOME_SHELL], [gnome-shell], [GNOME Shell],  [disable])
VERTEX_ENABLE([GTK2],        [gtk2],        [GTK2],         [disable])
VERTEX_ENABLE([GTK3],        [gtk3],        [GTK3],         [disable])
VERTEX_ENABLE([LIGHT],       [light],       [Vertex Light], [disable])
VERTEX_ENABLE([METACITY],    [metacity],    [Metacity],     [disable])
VERTEX_ENABLE([UNITY],       [unity],       [Unity],        [disable])
VERTEX_ENABLE([XFWM],        [xfwm],        [XFWM],         [disable])
VERTEX_ENABLE([PLANK],       [plank],       [Plank theme],  [disable])

AS_IF([test "x$ENABLE_GTK3" != xno], [VERTEX_GTK3])
AS_IF([test "x$ENABLE_GNOME_SHELL" != xno], [VERTEX_GNOME_SHELL])

AS_IF([test "x$ENABLE_GTK3" != xno -o "x$ENABLE_GNOME_SHELL" != xno], [
    AC_PATH_PROG([SASSC], [sassc])
    AS_IF([test "x$ac_cv_path_SASSC" = x], [AC_MSG_ERROR([sassc not found])])
])

AC_CONFIG_FILES([
    common/Makefile
    extra/Makefile
    Makefile
])

AC_OUTPUT
