include_directories (
    ${PROJECT_BINARY_DIR}
    ${FCITX4_FCITX_UTILS_INCLUDE_DIRS}
    ${FCITX4_FCITX_CONFIG_INCLUDE_DIRS}
    ${FCITX4_FCITX_INCLUDE_DIRS}
    ${GLIB2_INCLUDE_DIR}
    ${DBUS_INCLUDE_DIR}
    ${DBUS_ARCH_INCLUDE_DIR}
    )


set(fcitx_kimpanel_sources
  kimpanel.c
  )

add_definitions( -DLOCALEDIR=\"${CMAKE_INSTALL_PREFIX}/share/locale\" )

fcitx_add_addon_full(dueimkimpanel
SOURCES ${fcitx_kimpanel_sources}
IM_CONFIG fcitx-dueimkimpanel.conf
LINK_LIBS ${GLIB2_LIBRARIES} ${DBUS_LIBRARIES}
)
