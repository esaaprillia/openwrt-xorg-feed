#
# Copyright (C) 2008-2010 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=xcb-proto
PKG_VERSION:=1.15.2
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.xz
PKG_SOURCE_URL:=https://xorg.freedesktop.org/releases/individual/xcb/
PKG_HASH:=7072beb1f680a2fe3f9e535b797c146d22528990c72f63ddb49d2f350a3653ed
PKG_INSTALL:=1

#PKG_BUILD_DEPENDS:=python-mini/host

include $(INCLUDE_DIR)/package.mk
#$(call include_mk, python-package.mk)

#STAMP_CONFIGURED:=$(STAMP_CONFIGURED)_$(call confvar,PACKAGE_python PACKAGE_python-mini)

define Package/xcbproto
  SECTION:=xorg-xcb
  CATEGORY:=Xorg
  SUBMENU:=xcb
  BUILDONLY:=1
  TITLE:=xcbproto
  URL:=http://xcb.freedesktop.org/
endef

#define InstallPy
#	$(INSTALL_DIR) $(1)/host/lib/$(PYTHON)/site-packages/xcbgen
#	$(INSTALL_DATA) \
#		$(PKG_INSTALL_DIR)/usr/lib/$(PYTHON)/site-packages/xcbgen/*.py \
#		$(1)/host/lib/$(PYTHON)/site-packages/xcbgen/
#endef

define Build/InstallDev
#	$(call InstallPy,$(1),$(2))
	$(INSTALL_DIR) \
		$(1)/usr/lib/pkgconfig \
		$(1)/host/share/xcb

	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/share/xcb/* \
		$(1)/host/share/xcb/

	$(INSTALL_DATA) \
		$(PKG_INSTALL_DIR)/usr/lib/pkgconfig/* \
		$(1)/usr/lib/pkgconfig/

	$(SED) 's,datadir=/usr,datadir=$(STAGING_DIR)/host,g' $(1)/usr/lib/pkgconfig/xcb-proto.pc
endef

$(eval $(call BuildPackage,xcbproto))
