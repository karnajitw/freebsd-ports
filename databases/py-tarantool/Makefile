# Created by: Veniamin Gvozdikov <vg@FreeBSD.org>
# $FreeBSD$

PORTNAME=	tarantool
PORTVERSION=	0.6.4
CATEGORIES=	databases python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	sunpoet@FreeBSD.org
COMMENT=	Client library for Tarantool Database

LICENSE=	BSD3CLAUSE

RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}msgpack>=0.4:devel/py-msgpack@${PY_FLAVOR}

NO_ARCH=	yes
REINPLACE_ARGS=	-i ''
USES=		python
USE_PYTHON=	autoplist concurrent distutils

post-patch:
	@${REINPLACE_CMD} -e 's|msgpack-python|msgpack|' ${WRKSRC}/setup.py ${WRKSRC}/tarantool.egg-info/requires.txt

.include <bsd.port.mk>
