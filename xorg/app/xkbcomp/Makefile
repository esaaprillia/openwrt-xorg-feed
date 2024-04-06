#
# Copyright (C) 2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xkbcomp
PKG_RELEASE:=1
PKG_VERSION:=1.4.7

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/app
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_HASH:=0a288114e5f44e31987042c79aecff1ffad53a8154b8ec971c24a69a80f81f77

PKG_INSTALL:=1
PKG_BUILD_PARALLEL:=1

include $(INCLUDE_DIR)/package.mk

TARGET_LDFLAGS+= \
    -Wl,-rpath-link=$(STAGING_DIR)/usr/lib \
    -Wl,-rpath=/usr/lib

define Package/xkbcomp
  SECTION:=xorg-app
  CATEGORY:=Xorg
  SUBMENU:=app
  DEPENDS:=+libX11 +libxkbfile
  TITLE:=xkbcomp
  URL:=http://xorg.freedesktop.org/
endef

define Package/xkbcomp/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) \
		$(PKG_INSTALL_DIR)/usr/bin/* \
		$(1)/usr/bin
	$(INSTALL_DIR) $(PKG_INSTALL_DIR)/usr/share/xkbdata/compiled
endef

$(eval $(call BuildPackage,xkbcomp))
