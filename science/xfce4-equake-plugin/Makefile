# Created by: Olivier Duchateau
# $FreeBSD$

PORTNAME=	xfce4-equake-plugin
PORTVERSION=	1.3.8.1
CATEGORIES=	science xfce
MASTER_SITES=	XFCE/src/panel-plugins/${PORTNAME}/${PORTVERSION:C/^([0-9]+\.[0-9]+).*/\1/}
DIST_SUBDIR=	xfce4

MAINTAINER=	xfce@FreeBSD.org
COMMENT=	Earthquake monitor plugin for the Xfce panel

LICENSE=	GPLv3
LICENSE_FILE=	${WRKSRC}/COPYING

LIB_DEPENDS=	libfontconfig.so:x11-fonts/fontconfig \
	libfreetype.so:print/freetype2 \
	libcurl.so:ftp/curl

GNU_CONFIGURE=	yes
USES=	gettext gmake libtool pkgconfig tar:bzip2 xfce
USE_GNOME=	glib20 gtk20 intltool cairo
USE_XFCE=	panel
USE_XORG=	x11
INSTALLS_ICONS=	yes

.include <bsd.port.mk>
