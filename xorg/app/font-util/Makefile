#
# Copyright (C) 2006-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=font-util
PKG_VERSION:=1.4.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://xorg.freedesktop.org/releases/individual/font/
PKG_HASH:=5c9f64123c194b150fee89049991687386e6ff36ef2af7b80ba53efaf368cc95

include $(INCLUDE_DIR)/package.mk

define Package/font-util
  SECTION:=xorg-font
  CATEGORY:=Xorg
  SUBMENU:=app
  TITLE:=misc tool to generate x fonts
  DEPENDS:=+xserver
  URL:=http://xorg.freedesktop.org/
endef

define Build/Configure
	cd  $(PKG_BUILD_DIR)/; ./configure  
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)
	$(MAKE) -C $(PKG_BUILD_DIR) install DESTDIR="$(PKG_INSTALL_DIR)"
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig $(1)/usr/lib/X11 $(2)/bin
	$(INSTALL_DATA) $(PKG_INSTALL_DIR)/usr/local/lib/pkgconfig/fontutil.pc $(1)/usr/lib/pkgconfig
	$(CP) $(PKG_INSTALL_DIR)/usr/local/lib/X11/* $(1)/usr/lib/X11/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/local/bin/* $(2)/bin/
endef

$(eval $(call BuildPackage,font-util))
