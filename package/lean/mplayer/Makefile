#
# Copyright (C) 2006-2014 OpenWrt.org
#
# This is free software, licensed under the GNU General Public License v2.
# See /LICENSE for more information.
#
 
include $(TOPDIR)/rules.mk
 
PKG_NAME:=MPlayer
PKG_VERSION:=1.0rc2
PKG_RELEASE:=1
 
PKG_SOURCE:=$(PKG_NAME)-$(PKG_VERSION).tar.bz2
PKG_SOURCE_URL:=http://www.mplayerhq.hu/MPlayer/releases/
PKG_MD5SUM:=7e27e535c2d267637df34898f1b91707
 
PKG_MAINTAINER:= http://www.mplayerhq.hu
PKG_LICENSE:=GPLv2
PKG_LICENSE_FILES:=Copyright
 
include $(INCLUDE_DIR)/package.mk
 
define Package/MPlayer
  SECTION:=multimedia
  CATEGORY:=Multimedia
  DEPENDS:= +libpthread +libjpeg +libncurses +libmad +libc +alsa-lib +zlib +liblzo
  TITLE:=MPlayer1.0rc2
  URL:=$(PKG_SOURCE_URL)
endef
 
TARGET_CFLAGS += -DHAVE_BYTESWAP_H
 
CONFIGURE_ARGS= \
	--enable-cross-compile	\
	--host-cc=gcc  \
	--cc=mipsel-openwrt-linux-gcc \
	--target=mips-linux	\
        --prefix=$(CONFIGURE_PREFIX) \
        --bindir=$(CONFIGURE_PREFIX)/bin \
        --datadir=$(CONFIGURE_PREFIX)/share \
        --mandir=$(CONFIGURE_PREFIX)/man \
	--disable-gif		\
	--disable-png		\
	--disable-real		\
	--disable-speex		\
	--enable-fbdev		\
	--enable-linux-devfs	\
	--enable-alsa		\
	--disable-largefiles	\
	--disable-dvdread	\
	--disable-mencoder	\
	--disable-live		\
	--disable-ossaudio	\
	--disable-libavcodec_a	\
	--disable-libavformat_a	\
	--disable-libpostproc_a	\
	--disable-bitmap-font	\
	--disable-ivtv		\
	--disable-tv		\
	--disable-tga		\
	--disable-pnm		\
	--disable-md5sum	\
	--disable-w32threads	\
	--disable-win32dll	\
	--disable-qtx		\
	--disable-xanim		\
	--disable-libmpeg2	\
	--disable-radio-v4l2	\
	--disable-radio-bsdbt848	\
	--disable-tv-v4l1	\
	--disable-tv-v4l2	\
	--disable-tv-bsdbt848	\
	--disable-tv-teletext	\
	--disable-pvr		\
	--disable-mp3lib	\
	--disable-liba52	\
	--disable-decoder=DECODER	\
	--disable-encoder=ENCODER	\
	--disable-parser=PARSER		\
	--disable-demuxer=DEMUXER	\
	--disable-muxer=MUXER
 
define Package/MPlayer/install
	$(INSTALL_DIR) $(1)/usr/bin
	$(INSTALL_BIN) $(PKG_BUILD_DIR)/mplayer $(1)/usr/bin/
endef
 
$(eval $(call BuildPackage,MPlayer))
