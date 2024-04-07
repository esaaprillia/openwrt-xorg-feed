#
# Copyright (C) 2009-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xf86-input-keyboard
PKG_VERSION:=2.0.0
PKG_RELEASE:=1

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/driver
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_HASH:=3266fdf1a2175fd4fe999527ae8527cc59f3f01a1d6271ad474bff0b9451feb9

PKG_BUILD_DEPENDS:=randrproto inputproto kbproto xproto
PKG_FIXUP:=libtool
PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk
$(call include_mk, xorg-driver.mk)

define Package/xf86-input-keyboard
  SECTION:=xorg-driver
  CATEGORY:=Xorg
  SUBMENU:=driver
  DEPENDS:=+xserver-xorg
  TITLE:=xf86-input-keyboard
  URL:=http://xorg.freedesktop.org/
endef

define Package/xf86-input-keyboard/install
	$(INSTALL_DIR) $(1)/usr/lib/xorg/modules/input
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/xorg/modules/input/kbd_drv.so \
		$(1)/usr/lib/xorg/modules/input/
endef

$(eval $(call BuildPackage,xf86-input-keyboard))
