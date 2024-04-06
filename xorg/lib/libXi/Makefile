#
# Copyright (C) 2007-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libXi
PKG_RELEASE:=1
PKG_VERSION:=1.8.1

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/lib/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_HASH:=89bfc0e814f288f784202e6e5f9b362b788ccecdeb078670145eacd8749656a7

PKG_FIXUP:=libtool
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=xproto xextproto inputproto

include $(INCLUDE_DIR)/package.mk

define Package/libXi
  SECTION:=xorg-libraries
  CATEGORY:=Xorg
  SUBMENU:=libraries
  DEPENDS:=+libX11 +libXext
  TITLE:=libXi
  URL:=http://xorg.freedesktop.org/
endef

define Build/Configure
	$(call Build/Configure/Default, --enable-malloc0returnsnull)
endef

define Package/libXi/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/libXi.so* \
		$(1)/usr/lib/
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/libXi.{so*,a,la} \
		$(1)/usr/lib/

	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/* \
		$(1)/usr/lib/pkgconfig/

	$(INSTALL_DIR) $(1)/usr/include/X11/extensions
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/include/X11/extensions/* \
		$(1)/usr/include/X11/extensions/
endef

$(eval $(call BuildPackage,libXi))
