#
# Copyright (C) 2011-2014 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=pbzip2
PKG_VERSION:=1.1.8
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://compression.ca/$(PKG_NAME)
PKG_MD5SUM:=a5400b652f4d3a91d68971f0f52a5dc1

PKG_INSTALL:=1

include $(INCLUDE_DIR)/package.mk

define Package/pbzip2
	SECTION:=utils
	CATEGORY:=Utilities
	SUBMENU:=compression
	DEPENDS:=+libpthread +libstdcpp +libbz2
	TITLE:=parallel bzip2
	URL:=http://compression.ca/pbzip2/
	MAINTAINER:=Entware team, entware.wl500g.info
endef

define Package/pbzip2/description
 PBZIP2 is a parallel implementation of the bzip2 block-sorting file compressor
endef

TARGET_LDFLAGS += \
	-lstdc++ \

MAKE_VARS += \
	PREFIX="$(PKG_INSTALL_DIR)/opt" \

define Package/pbzip2/install
	$(INSTALL_DIR) $(1)/opt/bin
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/opt/bin/pbzip2 $(1)/opt/bin/
	$(LN) -s /opt/bin/pbzip2 $(1)/opt/bin/pbunzip2
	$(LN) -s /opt/bin/pbzip2 $(1)/opt/bin/pbzcat
endef

$(eval $(call BuildPackage,pbzip2))
