# Created by: Alan Eldridge <alane@FreeBSD.org>
# $FreeBSD$

PORTNAME=	txt2tags
PORTVERSION=	2.6
PORTREVISION=	3
CATEGORIES=	textproc

MAINTAINER=	lbartoletti@tuxfamily.org
COMMENT=	Convert simply formatted text into markup (e.g., HTML)

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

USES=		python:2.7 shebangfix
SHEBANG_FILES=	extras/html-update.sh txt2tags
USE_GITHUB=	yes
NO_BUILD=	yes
NO_ARCH=	yes

PLIST_FILES=	bin/${PORTNAME}
PORTDOCS=	*
PORTEXAMPLES=	*

OPTIONS_DEFINE=	DOCS EXAMPLES

do-install:
	${INSTALL_SCRIPT} ${WRKSRC}/txt2tags ${STAGEDIR}${PREFIX}/bin

do-install-EXAMPLES-on:
	@cd ${WRKSRC}/samples && ${COPYTREE_SHARE} . ${STAGEDIR}${EXAMPLESDIR}
	@cd ${WRKSRC} && ${COPYTREE_SHARE} extras ${STAGEDIR}${EXAMPLESDIR}

do-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/ChangeLog ${WRKSRC}/README ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/doc/*/*.pdf ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
