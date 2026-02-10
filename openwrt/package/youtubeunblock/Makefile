include $(TOPDIR)/rules.mk

PKG_NAME:=youtubeunblock
PKG_VERSION:=1.0
PKG_RELEASE:=1

PKG_LICENSE:=GPL-3.0

include $(INCLUDE_DIR)/package.mk

define Package/youtubeunblock
  SECTION:=net
  CATEGORY:=Network
  TITLE:=YouTube DPI bypass tool
  DEPENDS:=+libpthread +libnfnetlink +libnetfilter-queue
endef

define Package/youtubeunblock/description
YouTube DPI bypass using NFQUEUE (OpenWrt build)
endef

define Build/Compile
	$(TARGET_CC) $(TARGET_CFLAGS) $(TARGET_LDFLAGS) \
		$(CURDIR)/src/*.c \
		-o $(PKG_BUILD_DIR)/youtubeunblock \
		-lnfnetlink -lnetfilter_queue -lpthread
endef

define Package/youtubeunblock/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/youtubeunblock $(1)/usr/bin/youtubeunblock

	$(INSTALL_DIR) $(1)/etc/init.d
	$(INSTALL_BIN) $(CURDIR)/init.d/youtubeUnblock $(1)/etc/init.d/youtubeunblock
endef

$(eval $(call BuildPackage,youtubeunblock))
