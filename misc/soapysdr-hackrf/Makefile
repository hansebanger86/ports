# $FreeBSD$

PORTNAME=	SoapyHackRF
DISTVERSIONPREFIX=	soapy-hackrf-
DISTVERSION=	0.3.3
CATEGORIES=	misc hamradio

MAINTAINER=	hamradio@FreeBSD.org
COMMENT=	Soapy SDR module for Hack RF

LICENSE=	BSL
LICENSE_FILE=	${WRKSRC}/LICENSE

LIB_DEPENDS=	libhackrf.so:comms/hackrf \
		libSoapySDR.so:misc/soapysdr

USES=		cmake compiler:c++11-lang
USE_GITHUB=	yes
GH_ACCOUNT=	pothosware

PLIST_FILES=	lib/SoapySDR/modules0.7/libHackRFSupport.so

.include <bsd.port.mk>
