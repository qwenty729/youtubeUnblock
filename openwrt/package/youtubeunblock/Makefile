
include $(TOPDIR)/rules.mk

PKG_NAME:=youtubeunblock
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_SOURCE_PROTO:=git
PKG_SOURCE_URL:=https://github.com/Waujito/youtubeUnblock.git
PKG_SOURCE_VERSION:=HEAD
PKG_MIRROR_HASH:=skip

PKG_LICENSE:=GPL-3.0
PKG_MAINTAINER:=github-actions

include $(INCLUDE_DIR)/package.mk

define Package/youtubeunblock
  SECTION:=net
  CATEGORY:=Network
  TITLE:=YouTube DPI bypass tool
  URL:=https://github.com/Waujito/youtubeUnblock
  DEPENDS:=+libpthread
endef

define Package/youtubeunblock/description
 Tool to bypass DPI blocking of YouTube using TCP tricks
endef

define Build/Compile
	$(MAKE) -C $(PKG_BUILD_DIR)
endef

define Package/youtubeunblock/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/youtubeUnblock $(1)/usr/bin/

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/init.d/youtubeUnblock $(1)/etc/init.d/youtubeunblock
endef

$(eval $(call BuildPackage,youtubeunblock))
