# $FreeBSD$

PORTNAME=	drf-yasg
DISTVERSION=	1.7.4
CATEGORIES=	www python
MASTER_SITES=	CHEESESHOP
PKGNAMEPREFIX=	${PYTHON_PKGNAMEPREFIX}

MAINTAINER=	freebsd_ports@k-worx.org
COMMENT=	Yet Another Swagger Generator

LICENSE=	BSD3CLAUSE
LICENSE_FILE=	${WRKSRC}/LICENSE.rst

BUILD_DEPENDS=	${PYTHON_PKGNAMEPREFIX}setuptools_scm>=1.15.6:devel/py-setuptools_scm@${PY_FLAVOR}
RUN_DEPENDS=	${PYTHON_PKGNAMEPREFIX}django111>=1.11.7:www/py-django111@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}djangorestframework>=3.7.7:www/py-djangorestframework@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}coreapi>=2.3.3:devel/py-coreapi@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}coreschema>=0.0.4:devel/py-coreschema@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}flex>=6.11.1:devel/py-flex@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}future>=0.16.0:devel/py-future@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}inflection>=0.3.1:devel/py-inflection@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}openapi-codec>=1.3.2:devel/py-openapi-codec@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}ruamel.yaml>=0.15.34:devel/py-ruamel.yaml@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}six>=1.10.0:devel/py-six@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}swagger-spec-validator>=2.1.0:devel/py-swagger-spec-validator@${PY_FLAVOR} \
		${PYTHON_PKGNAMEPREFIX}uritemplate>=3.0.0:net/py-uritemplate@${PY_FLAVOR}

USES=		python
USE_PYTHON=	distutils autoplist

NO_ARCH=	yes

post-patch:
	# Unpin fixed versioning for py-setuptools_scm
	@${REINPLACE_CMD} -e 's|==|>=|' ${WRKSRC}/requirements/setup.txt

.include <bsd.port.mk>
