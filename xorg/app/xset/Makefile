#
# Copyright (C) 2007-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
# blogic@openwrt.org

include $(TOPDIR)/rules.mk

PKG_NAME:=xset
PKG_RELEASE:=1
PKG_VERSION:=1.2.5

PKG_SOURCE_URL:=https://xorg.freedesktop.org/releases/individual/app/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/

PKG_HASH:=9f692d55635b3862cd63633b1222a87680ec283c7a8e8ed6dd698a3147f75e2f
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk


TARGET_LDFLAGS+= \
    -Wl,-rpath-link=$(STAGING_DIR)/usr/lib \
    -Wl,-rpath=/usr/lib

define Package/xset
  SECTION:=xorg-app
  CATEGORY:=Xorg
  SUBMENU:=app
  DEPENDS:=+libXmuu +libX11 +libXext
  TITLE:=xset
  URL:=http://xorg.freedesktop.org/
endef

define Package/xset/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) \
		$(PKG_INSTALL_DIR)/usr/bin/* \
		$(1)/usr/bin
endef

$(eval $(call BuildPackage,xset))
