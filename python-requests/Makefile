#
# Copyright (C) 2011-2014 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#


include $(TOPDIR)/rules.mk

PKG_NAME:=python-requests
PKG_VERSION:=2.3.0
PKG_RELEASE:=1

PKG_SOURCE:=requests-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=http://pypi.python.org/packages/source/r/requests/
PKG_MD5SUM:=7449ffdc8ec9ac37bbcd286003c80f00

PKG_BUILD_DIR:=$(BUILD_DIR)/requests-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

#PKG_BUILD_DEPENDS:=python distribute/host

define Package/$(PKG_NAME)
	SUBMENU:=Python
	SECTION:=lang
	CATEGORY:=Languages
	TITLE:=Python HTTP for Humans
	URL:=http://python-requests.org
	DEPENDS:=+python
	MAINTAINER:=Entware team, entware.wl500g.info
endef

define Package/$(PKG_NAME)/description
 Requests allow you to send HTTP/1.1 requests. You can add headers,
 form data, multipart files, and parameters with simple Python dictionaries,
 and access the response data in the same way. It's powered by
 httplib and urllib3, but it does all the hard work and crazy hacks for you.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/opt --root=$(PKG_INSTALL_DIR))
endef

define Package/$(PKG_NAME)/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
	    $(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
	    $(1)$(PYTHON_PKG_DIR)/
endef

$(eval $(call BuildPackage,$(PKG_NAME)))
