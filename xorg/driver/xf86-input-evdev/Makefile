#
# Copyright (C) 2007-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xf86-input-evdev
PKG_RELEASE:=1
PKG_VERSION:=2.10.6

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/driver
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_HASH:=8726073e81861bc7b2321e76272cbdbd33c7e1a121535a9827977265b9033ec0

PKG_FIXUP:=libtool
PKG_INSTALL:=1

PKG_BUILD_DEPENDS:=randrproto inputproto xproto

include $(INCLUDE_DIR)/package.mk
$(call include_mk, xorg-driver.mk)

define Package/xf86-input-evdev
  SECTION:=xorg-driver
  CATEGORY:=Xorg
  SUBMENU:=driver
  DEPENDS:=+xserver-xorg
  TITLE:=xf86-input-evdev
  URL:=http://xorg.freedesktop.org/
endef

define Package/xf86-input-evdev/install
	$(INSTALL_DIR) $(1)/usr/lib/xorg/modules/input
	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/xorg/modules/input/evdev_drv.so \
		$(1)/usr/lib/xorg/modules/input/
endef

$(eval $(call BuildPackage,xf86-input-evdev))
