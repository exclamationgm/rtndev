#
# Copyright (C) 2011-2014 Entware
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#

include $(TOPDIR)/rules.mk

PKG_NAME:=python-cups
PKG_VERSION:=1.9.67
PKG_RELEASE:=1

PKG_SOURCE:=pycups-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://cyberelk.net/tim/data/pycups
PKG_MD5SUM:=7275811ac3c0abc2fd50cbad935b09a5

PKG_BUILD_DEPENDS:=distribute/host
PKG_BUILD_DIR:=$(BUILD_DIR)/pycups-$(PKG_VERSION)

include $(INCLUDE_DIR)/package.mk
$(call include_mk, python-package.mk)

define Package/python-cups
	SECTION:=lang
	CATEGORY:=Languages
	SUBMENU:=Python
	DEPENDS:=+python +cups
	TITLE:=Python bindings for the CUPS API
	URL:=http://cyberelk.net/tim/software/pycups/
	MAINTAINER:=Entware team, entware.wl500g.info
endef

define Package/python-cups/description
 This is a Python bindings for the CUPS API, known as pycups. It was written
 for use with system-config-printer, but can be put to other uses as well.
endef

define Build/Compile
	$(call Build/Compile/PyMod,,install --prefix=/opt --root=$(PKG_INSTALL_DIR))
endef

define Package/python-cups/install
	$(INSTALL_DIR) $(1)$(PYTHON_PKG_DIR)
	$(CP) \
		$(PKG_INSTALL_DIR)$(PYTHON_PKG_DIR)/* \
		$(1)$(PYTHON_PKG_DIR)
endef

$(eval $(call BuildPackage,python-cups))
