# $FreeBSD$

PORTNAME=	orange3
DISTVERSION=	3.14.0
CATEGORIES=	misc python

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Component-based data mining software

LICENSE=	GPLv3

RUN_DEPENDS=	${PYNUMPY} \
		${PYTHON_PKGNAMEPREFIX}AnyQt>=0.0.8:x11-toolkits/py-AnyQt@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}bottleneck>=1.0.0:math/py-bottleneck@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}chardet>=3.0.2:textproc/py-chardet@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}CommonMark>=0.5.5:textproc/py-CommonMark@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}docutils>0:textproc/py-docutils@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}joblib>=0.9.4:devel/py-joblib@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}keyring>0:security/py-keyring@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}keyrings.alt>0:security/py-keyrings.alt@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}PyOpenGL>=0:graphics/py-PyOpenGL@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}pyqtgraph>=0.10.0:graphics/py-pyqtgraph@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}scikit-learn>=0.18.1:science/py-scikit-learn@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}scipy>=0.16.1:science/py-scipy@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}serverfiles>0:misc/py-serverfiles@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}xlrd>=0.9.2:textproc/py-xlrd@${PY_FLAVOR}

USES=		python:3.4+ pyqt:5
USE_GITHUB=	yes
GH_ACCOUNT=	biolab
USE_PYTHON=	distutils autoplist
USE_PYQT=	core_run gui_run printsupport_run widgets_run webengine_run

CFLAGS+=	-DQSORT_R_STYLE_BSD=yes

post-install: # https://github.com/biolab/orange3/issues/3060
	@${REINPLACE_CMD} -e 's|^"${PREFIX}/|| ; s|"$$||' ${_PYTHONPKGLIST}
	@${REINPLACE_CMD} -e 's|import sys|& ; from OpenGL import GL|' ${STAGEDIR}${PREFIX}/bin/orange-canvas # https://github.com/biolab/orange3/issues/3062

.include <bsd.port.mk>
