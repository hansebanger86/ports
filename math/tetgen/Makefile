# Created by: Pedro F. Giffuni
# $FreeBSD$

PORTNAME=	tetgen
PORTVERSION=	1.5.0.20131104
CATEGORIES=	math
MASTER_SITES=	http://wias-berlin.de/software/tetgen/1.5/src/
DISTNAME=	${PORTNAME}${PORTVERSION:R}
DIST_SUBDIR=	${PORTNAME}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Quality Tetrahedral Mesh Generator and Delaunay Triangulator

LICENSE=	AGPLv3
LICENSE_FILE=	${WRKSRC}/LICENSE

MAKEFILE=	makefile
ALL_TARGET=	tetgen tetlib

PORTEXAMPLES=	example.poly
PLIST_FILES=	bin/tetgen include/tetgen.h lib/libtet.a

OPTIONS_DEFINE=	EXAMPLES

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/tetgen ${STAGEDIR}${PREFIX}/bin
	${INSTALL_DATA} ${WRKSRC}/tetgen.h ${STAGEDIR}${PREFIX}/include
	${INSTALL_DATA} ${WRKSRC}/libtet.a ${STAGEDIR}${PREFIX}/lib

do-install-EXAMPLES-on:
	${MKDIR} ${STAGEDIR}${EXAMPLESDIR}
	${INSTALL_DATA} ${WRKSRC}/example.poly ${STAGEDIR}${EXAMPLESDIR}

do-test:
	(cd ${INSTALL_WRKSRC} && ./tetgen -p example.poly )

.include <bsd.port.mk>
