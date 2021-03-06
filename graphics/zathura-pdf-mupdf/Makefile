# Created by: Zsolt Udvari <udvzsolt@gmail.com>
# $FreeBSD$

PORTNAME=	zathura-pdf-mupdf
PORTVERSION=	0.3.3
PORTREVISION=	2
CATEGORIES=	graphics
MASTER_SITES=	https://pwmt.org/projects/zathura-pdf-mupdf/download/ \
		http://www.madpilot.net/~mad/pwmt.org/

MAINTAINER=	uzsolt@uzsolt.hu
COMMENT=	MuPDF render PDF plugin for Zathura PDF viewer

LICENSE=	ZLIB
LICENSE_FILE=	${WRKSRC}/LICENSE

BUILD_DEPENDS=	zathura:graphics/zathura
RUN_DEPENDS=	zathura:graphics/zathura
LIB_DEPENDS=	libjbig2dec.so:graphics/jbig2dec \
		libfreetype.so:print/freetype2 \
		libgirara-gtk3.so:x11-toolkits/girara \
		libharfbuzz.so:print/harfbuzz \
		libmupdf.so:graphics/mupdf \
		libopenjp2.so:graphics/openjpeg

PLIST_FILES=	lib/zathura/libpdf-mupdf.so \
		share/applications/org.pwmt.zathura-pdf-mupdf.desktop \
		share/metainfo/org.pwmt.zathura-pdf-mupdf.metainfo.xml

#MAKE_ARGS=	OPENSSL_INC=-I${OPENSSLINC} OPENSSL_LIB="-L${OPENSSLLIB} -lcrypto"
USES=		compiler:c11 desktop-file-utils gmake jpeg meson pkgconfig tar:xz
USE_GNOME=	cairo gdkpixbuf2 glib20 gtk30
USE_LDCONFIG=	yes

CONFLICTS_INSTALL=	zathura-pdf-poppler-[0-9]*

post-patch:
	${REINPLACE_CMD} "s@\(cc.find_library(.*\))@\1,dirs:'${PREFIX}/lib')@" ${WRKSRC}/meson.build

.include <bsd.port.mk>
