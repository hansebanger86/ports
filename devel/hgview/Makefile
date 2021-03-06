# Created by: Dmitry Marakasov <amdmi3@FreeBSD.org>
# $FreeBSD$

PORTNAME=	hgview
PORTVERSION=	1.9.0
PORTREVISION=	3
CATEGORIES=	devel
MASTER_SITES=	CHEESESHOP \
		http://download.logilab.org/pub/${PORTNAME}/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Fast Mercurial log navigator written in pyqt4

LICENSE=	GPLv2

DEPRECATED=		Qt4 has been EOL since december 2015
EXPIRATION_DATE=	2019-03-15

BROKEN=		fails to configure
DEPRECATED=	Broken for more than 6 months
EXPIRATION_DATE=	2019-03-05

RUN_DEPENDS=	hg:devel/mercurial \
		${PYTHON_PKGNAMEPREFIX}mx-base>0:lang/py-mx-base@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}docutils>0:textproc/py-docutils@${PY_FLAVOR}
BUILD_DEPENDS=	hg:devel/mercurial \
		xmlto:textproc/xmlto \
		asciidoc:textproc/asciidoc

NO_ARCH=	yes
USES=		gmake pyqt:4 python:2.7
USE_PYQT=	gui_run qscintilla2_run xml_build
USE_PYTHON=	distutils
PORTDOCS=	*

OPTIONS_DEFINE=	DOCS

post-patch:
	@${REINPLACE_CMD} -e 's|path/to.*hgview.py|${PYTHON_SITELIBDIR}/hgext/hgview.py|' \
		${WRKSRC}/README
	@${REINPLACE_CMD} -e 's|'make'|'${MAKE_CMD}'|' ${WRKSRC}/setup.py
	@${REINPLACE_CMD} \
		-e 's,distutils\.command\.install ,setuptools\.command\.install ,' \
		${WRKSRC}/setup.py

post-install-DOCS-on:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README ${STAGEDIR}${DOCSDIR}

.include <bsd.port.mk>
