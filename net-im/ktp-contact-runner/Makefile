# $FreeBSD$

PORTNAME=	ktp-contact-runner
DISTVERSION=	${KDE_APPLICATIONS_VERSION}
CATEGORIES=	net-im kde kde-applications

MAINTAINER=	kde@FreeBSD.org
COMMENT=	KRunner integration module for KDE Telepathy

LIB_DEPENDS=	libtelepathy-qt5.so:net-im/telepathy-qt5 \
		libKTpCommonInternals.so:net-im/ktp-common-internals

USES=		cmake:outsource gettext kde:5 qt:5 tar:xz
USE_KDE=	config coreaddons ecm i18n package plasma-framework runner \
		service wallet
USE_QT=		core dbus gui network widgets xml\
		buildtools_build qmake_build

.include <bsd.port.mk>
