# $FreeBSD$

PORTNAME=	sonarr
PORTVERSION=	2.0.0.5225
PORTREVISION=	0
CATEGORIES=	net-p2p
MASTER_SITES=	http://download.sonarr.tv/v2/master/mono/
DISTNAME=	NzbDrone.master.${PORTVERSION}.mono

MAINTAINER=	feld@FreeBSD.org
COMMENT=	PVR for Usenet and BitTorrent users

LICENSE=	GPLv3

RUN_DEPENDS=	mono>0:lang/mono \
		mediainfo>0:multimedia/mediainfo \
		sqlite3>0:databases/sqlite3
LIB_DEPENDS=	libcurl.so:ftp/curl

USE_RC_SUBR=	sonarr

NO_ARCH=	YES
NO_BUILD=	YES
WRKSRC=	${WRKDIR}/NzbDrone

USERS=	sonarr
GROUPS=	sonarr

OPTIONS_DEFINE=	X11

# Permits image resizing
X11_LIB_DEPENDS+=libgdiplus.so:x11-toolkits/libgdiplus

.include <bsd.port.options.mk>

do-install:
	${INSTALL} -d -m 755 ${STAGEDIR}/${DATADIR}
	cd ${WRKSRC} && ${COPYTREE_SHARE} \* ${STAGEDIR}/${DATADIR}

post-install:
	@${FIND} -s ${STAGEDIR}${DATADIR} -not -type d | ${SORT} | \
		${SED} -e 's#^${STAGEDIR}${PREFIX}/##' >> ${TMPPLIST}

.include <bsd.port.mk>
