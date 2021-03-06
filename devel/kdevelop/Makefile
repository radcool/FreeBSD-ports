# $FreeBSD$

PORTNAME=	kdevelop
DISTVERSION=	5.2.3
CATEGORIES=	devel kde
MASTER_SITES=	KDE/stable/kdevelop/${DISTVERSION}/src
DIST_SUBDIR=	KDE/kdevelop

MAINTAINER=	kde@FreeBSD.org
COMMENT=	Plugin extensible IDE for KDE

LICENSE=	GPLv2
LICENSE_FILE=	${WRKSRC}/COPYING

BUILD_DEPENDS=	kdev-pg-qt:devel/kdevelop-pg-qt
LIB_DEPENDS=	libkasten3controllers.so:devel/okteta \
		libapr-1.so:devel/apr1 \
		libsvn_client-1.so:devel/subversion \
		libboost_thread.so:devel/boost-libs \
		libkomparediff2.so:textproc/libkomparediff2 \
		libclang.so.6:devel/llvm60
RUN_DEPENDS=	gmake:devel/gmake

USES=		cmake:outsource compiler:c++11-lib desktop-file-utils \
		gettext grantlee:5 kde:5 qt:5 shared-mime-info shebangfix tar:xz
USE_KDE=	archive attica auth bookmarks codecs completion config configwidgets \
		coreaddons crash guiaddons emoticons i18n iconthemes init \
		itemmodels itemviews jobwidgets kcmutils kdeclarative \
		kdelibs4support kio libksysguard newstuff notifications \
		notifyconfig package parts plasma-framework \
		runner service solid sonnet texteditor textwidgets threadweaver \
		widgetsaddons windowsystem xmlgui
USE_QT=		concurrent core dbus gui help network qml quick \
		script sql widgets xml buildtools_build qmake_build
CONFLICTS=	kdevelop-kde4-4* kdevelop-4* kdevplatform-kde4-4* kdevplatform-4*
SHEBANG_FILES=	kdevplatform/util/kdevplatform_shell_environment.sh \
		kdevplatform/util/.zshrc

OPTIONS_DEFINE=	WEBENGINE
WEBENGINE_DESC=	Use WebEngine as help reader
WEBENGINE_USES=	qt:5
WEBENGINE_USE=	QT=location,webchannel,webengine
WEBENGINE_USE_OFF=	QT=webkit
WEBENGINE_CMAKE_OFF=	-DCMAKE_DISABLE_FIND_PACKAGE_Qt5WebEngineWidgets:BOOL=TRUE

SHEBANG_LANG=	zsh
zsh_OLD_CMD=	/bin/zsh
zsh_CMD=	${LOCALBASE}/bin/zsh

.include <bsd.port.mk>
