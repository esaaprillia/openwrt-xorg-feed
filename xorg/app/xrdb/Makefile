#
# Copyright (C) 2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xrdb
PKG_RELEASE:=1
PKG_VERSION:=1.2.2

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/X11R7.4/src/app
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_HASH:=31f5fcab231b38f255b00b066cf7ea3b496df712c9eb2d0d50c670b63e5033f4
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

TARGET_LDFLAGS+=-Wl,-rpath-link=$(STAGING_DIR)/usr/lib

define Package/xrdb
  SECTION:=xorg-app
  CATEGORY:=Xorg
  SUBMENU:=app
  DEPENDS:=+libX11 +libXmuu
  TITLE:=xrdb
  URL:=http://xorg.freedesktop.org/
endef

define Package/xrdb/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) \
		$(PKG_INSTALL_DIR)/usr/bin/xrdb \
		$(1)/usr/bin/
endef

$(eval $(call BuildPackage,xrdb))
