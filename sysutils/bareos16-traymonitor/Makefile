# $FreeBSD$

PORTNAME=	bareos16

PKGNAMESUFFIX=	-traymonitor
PORTREVISION=	1

COMMENT=	Backup archiving recovery open sourced (traymonitor)

LIB_DEPENDS+=	libqwt.so:x11-toolkits/qwt5 \
		libbareos.so:sysutils/bareos16-client

CONFLICTS=	bacula*-bat-* bareos-traymonitor-*

USES=		pkgconfig gettext-runtime desktop-file-utils qt:4
USE_QT=		qmake_build uic_build moc_build rcc_build gui corelib
WITH_BAT=	yes

PLIST=		${.CURDIR}/pkg-plist
MAKE_ENV+=	MAKEOBJDIRPREFIX=/

MASTERDIR=	${.CURDIR}/../../sysutils/bareos16-server

CONFIGURE_ARGS+=	--enable-traymonitor=yes \
			--with-qwt=${LOCALBASE}/lib \
			--disable-build-dird \
			--disable-build-stored \
			--enable-client-only \
			--with-jansson=${LOCALBASE} \
			--enable-nls=yes

.include "${MASTERDIR}/Makefile"
