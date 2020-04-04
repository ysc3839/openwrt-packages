include $(TOPDIR)/rules.mk

PKG_NAME:=ethr
PKG_VERSION:=0.2.1
PKG_RELEASE:=1

PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.gz
PKG_SOURCE_URL:=https://codeload.github.com/microsoft/ethr/tar.gz/v${PKG_VERSION}?
PKG_HASH:=skip

PKG_MAINTAINER:=Richard Yu <yurichard3839@gmail.com>
PKG_LICENSE:=MIT
PKG_LICENSE_FILES:=LICENSE

PKG_BUILD_DEPENDS:=golang/host
PKG_BUILD_PARALLEL:=1
PKG_USE_MIPS16:=0

GO_PKG:=github.com/microsoft/ethr

include $(INCLUDE_DIR)/package.mk
include ../../lang/golang/golang-package.mk

define Package/ethr
  SECTION:=net
  CATEGORY:=Network
  TITLE:=Ethr
  URL:=https://github.com/microsoft/ethr
  DEPENDS:=$(GO_ARCH_DEPENDS)
endef

define Package/ethr/description
  Ethr is a Network Performance Measurement Tool for TCP, UDP & HTTP.
endef

define Package/ethr/install
	$(call GoPackage/Package/Install/Bin,$(PKG_INSTALL_DIR))

	$(INSTALL_DIR) $(1)/usr/bin/
	$(INSTALL_BIN) $(PKG_INSTALL_DIR)/usr/bin/ethr $(1)/usr/bin/
endef

$(eval $(call GoBinPackage,ethr))
$(eval $(call BuildPackage,ethr))
