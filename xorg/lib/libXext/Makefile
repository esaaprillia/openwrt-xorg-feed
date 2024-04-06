#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=libXext
PKG_RELEASE:=1
PKG_VERSION:=1.3.6

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/lib/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_HASH:=edb59fa23994e405fdc5b400afdf5820ae6160b94f35e3dc3da4457a16e89753

PKG_FIXUP:=libtool
PKG_INSTALL:=1
PKG_BUILD_DEPENDS:=xproto xextproto

include $(INCLUDE_DIR)/package.mk

define Package/libXext
  SECTION:=xorg-libraries
  CATEGORY:=Xorg
  SUBMENU:=libraries
  DEPENDS:=+libX11 +libXau
  TITLE:=libXext
  URL:=http://xorg.freedesktop.org/
endef

define Build/Configure
	$(call Build/Configure/Default, \
		--enable-malloc0returnsnull \
	)
endef

define Build/InstallDev
	$(INSTALL_DIR) $(1)/usr/lib/pkgconfig
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/*.{so*,a,la} \
		$(1)/usr/lib/
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/* \
		$(1)/usr/lib/pkgconfig/
	$(INSTALL_DIR) $(1)/usr/include/X11/extensions
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/include/X11/extensions/* \
		$(1)/usr/include/X11/extensions/
endef

define Package/libXext/install
	$(INSTALL_DIR) $(1)/usr/lib
	$(CP) \
		$(PKG_INSTALL_DIR)/usr/lib/*.so* \
		$(1)/usr/lib/
endef

$(eval $(call BuildPackage,libXext))
