#
# Copyright (C) 2008 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xbitmaps
PKG_RELEASE:=1
PKG_VERSION:=1.1.3

PKG_SOURCE_URL:=https://xorg.freedesktop.org/releases/individual/data/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/

PKG_HASH:=ad6cad54887832a17d86c2ccfc5e52a1dfab090f8307b152c78b0e1529cd0f7a
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/xbitmaps
  SECTION:=xorg-data
  CATEGORY:=Xorg
  SUBMENU:=data
  TITLE:=xbitmaps
  URL:=http://xorg.freedesktop.org/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/{lib/pkgconfig,include/X11/bitmaps}
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/* \
		$(1)/usr/lib/pkgconfig/
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/include/X11/bitmaps/* \
		$(1)/usr/include/X11/bitmaps/
endef

define Package/xbitmaps/install
	$(INSTALL_DIR) $(1)/usr/include/X11/bitmaps
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/include/X11/bitmaps/* \
		$(1)/usr/include/X11/bitmaps
endef

$(eval $(call BuildPackage,xbitmaps))
