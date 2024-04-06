#
# Copyright (C) 2011 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xprop
PKG_RELEASE:=1
PKG_VERSION:=1.2.7

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/app/
PKG_HASH:=4436e3148bb91a162406230d9f736a49ca8b50b74790015dc15d78d6ce8e825f

PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/

PKG_BUILD_DEPENDS:=xproto
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

TARGET_LDFLAGS+=-Wl,-rpath-link=$(STAGING_DIR)/usr/lib

define Package/xprop
  SECTION:=xorg-app
  CATEGORY:=Xorg
  SUBMENU:=app
  DEPENDS:=+libX11
  TITLE:=xprop
  URL:=http://xorg.freedesktop.org/
endef

define Package/xprop/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) \
		$(PKG_INSTALL_DIR)/usr/bin/xprop \
		$(1)/usr/bin/
endef

$(eval $(call BuildPackage,xprop))
