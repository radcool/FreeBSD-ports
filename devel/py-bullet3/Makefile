# $FreeBSD$

PORTNAME=	bullet3
DISTVERSION=	2.87
PORTREVISION=	1
CATEGORIES=	devel
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	yuri@FreeBSD.org
COMMENT=	Python version of 3D collision detection library Bullet

LICENSE=	ZLIB
LICENSE_FILE=	${WRKSRC}/LICENSE.txt

BROKEN_powerpc64=	fails to compile: FontData.h:265:1: narrowing conversion of '-96' from 'int' to 'char' inside { }

USES=		compiler:c++11-lang localbase python
USE_GITHUB=	yes
GH_ACCOUNT=	bulletphysics
USE_PYTHON=	autoplist distutils
USE_GL=		gl glew

post-patch: # remove examples because they fail: https://github.com/bulletphysics/bullet3/issues/1510, and they shouldn't be built anyway
	@${REINPLACE_CMD} -E 's,"examples/.*\.(cpp|c|m)",,' ${WRKSRC}/setup.py

post-install:
	@${STRIP_CMD} ${STAGEDIR}${PYTHON_SITELIBDIR}/pybullet.so

.include <bsd.port.mk>
