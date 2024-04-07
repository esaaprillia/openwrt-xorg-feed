#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xf86-input-mouse
PKG_VERSION:=1.9.5
PKG_RELEASE:=1

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/driver
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_HASH:=4fde8ae9b44352e2a208584c36528ee3ed13cf5fe4417208a9785daccefd9968

PKG_BUILD_DEPENDS:=randrproto inputproto xproto
PKG_FIXUP:=libtool
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
$(call include_mk, xorg-driver.mk)

define Package/xf86-input-mouse
  SECTION:=xorg-driver
  CATEGORY:=Xorg
  SUBMENU:=driver
  DEPENDS:=+xserver-xorg
  TITLE:=xf86-input-mouse
  URL:=http://xorg.freedesktop.org/
endef

define Package/xf86-input-mouse/install
	$(INSTALL_DIR) $(1)/usr/lib/xorg/modules/input
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/xorg/modules/input/mouse_drv.so \
		$(1)/usr/lib/xorg/modules/input/
endef

$(eval $(call BuildPackage,xf86-input-mouse))
