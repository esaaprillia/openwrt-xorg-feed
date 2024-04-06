#
# Copyright (C) 2008-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xkeyboard-config
PKG_VERSION:=2.41
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://xorg.freedesktop.org/releases/individual/data/xkeyboard-config/
PKG_HASH:=f02cd6b957295e0d50236a3db15825256c92f67ef1f73bf1c77a4b179edf728f

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/xkeyboard-config
  SECTION:=xorg-data
  CATEGORY:=Xorg
  SUBMENU:=data
  TITLE:=xkeyboard-config
  DEPENDS:=+xkbcomp
  URL:=http://freedesktop.org/wiki/Software/XKeyboardConfig
endef

define Package/xkeyboard-config/install
	$(INSTALL_DIR) $(1)/usr/share/X11
	$(CP) $(PKG_INSTALL_DIR)/usr/share/X11/xkb $(1)/usr/share/X11/
endef

$(eval $(call RequireCommand,intltool-update, \
	$(PKG_NAME) requires intltool installed on the host-system. \
))

$(eval $(call BuildPackage,xkeyboard-config))
