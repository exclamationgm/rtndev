#
# Copyright (C) 2011-2014 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=vsftpd-ext
PKG_VERSION:=3.0.2
PKG_RELEASE:=1

PKG_SOURCE:=vsftpd-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://vsftpd.devnet.ru/files/$(PKG_VERSION)
PKG_MDSUM:=8b00c749719089401315bd3c44dddbb2
PKG_UNPACK=$(HOST_TAR) -C $(PKG_BUILD_DIR) --strip-components=1 -xzf $(DL_DIR)/$(PKG_SOURCE)

include $(INCLUDE_DIR)/package.mk

define Package/vsftpd-ext
	SECTION:=net
	CATEGORY:=Network
	SUBMENU:=File Transfer
	TITLE:=A fast and secure FTP server
	URL:=http://vsftpd.devnet.ru
	MAINTAINER:=Entware team, entware.wl500g.info
endef

define Package/vsftpd-ext/descriptio
 vsftpd-ext is a GPL licensed FTP server for UNIX systems, including Linux.
endef

define Package/vsftpd-ext/conffiles
/opt/etc/vsftpd/vsftpd.conf
endef

define Package/vsftpd-ext/install
	$(INSTALL_DIR) $(1)/opt/sbin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/vsftpd $(1)/opt/sbin/
	$(INSTALL_DIR) $(1)/opt/etc/vsftpd
	$(INSTALL_CONF) $(PKG_BUILD_DIR)/vsftpd.conf $(1)/opt/etc/vsftpd/
	$(INSTALL_DIR) $(1)/opt/etc/init.d
	$(INSTALL_BIN) ./files/S49vsftpd $(1)/opt/etc/init.d/
	$(INSTALL_DIR) $(1)/opt/share/empty
endef

$(eval $(call BuildPackage,vsftpd-ext))
