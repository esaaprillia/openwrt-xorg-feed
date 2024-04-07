#
# Copyright (C) 2006-2009 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=dmxproto
PKG_RELEASE:=1
PKG_VERSION:=2.3.1

PKG_SOURCE_URL:=http://xorg.freedesktop.org/releases/individual/proto/
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_BUILD_DIR:=$(BUILD_DIR)/Xorg/$(PKG_NAME)-$(PKG_VERSION)/
PKG_HASH:=e72051e6a3e06b236d19eed56368117b745ca1e1a27bdc50fd51aa375bea6509

include $(INCLUDE_DIR)/package.mk

define Package/dmxproto
  SECTION:=xorg-proto
  CATEGORY:=Xorg
  SUBMENU:=proto
  DEPENDS:=
  TITLE:=dmxproto
  URL:=http://xorg.freedesktop.org/
endef

define Build/InstallDev
	DESTDIR="$(1)" $(MAKE) -C $(PKG_BUILD_DIR)/ $(MAKE_FLAGS) install
endef

define Build/Compile
	true
endef

$(eval $(call BuildPackage,dmxproto))
