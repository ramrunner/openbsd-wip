# $OpenBSD$

COMMENT =	K Desktop Environment, document viewer
DISTNAME =	okular-${MODKDE_VERSION}

SHARED_LIBS =	okularcore		0.0	# 1.7

WANTLIB =  c m pthread stdc++ z
WANTLIB += lib/qt4/QtDBus lib/qt4/QtGui lib/qt4/QtNetwork
WANTLIB += lib/qt4/QtSvg lib/qt4/QtXml
WANTLIB += kdeui khtml kio
WANTLIB += kjs kjsapi kparts kprintutils kpty nepomuk
WANTLIB += nepomukutils phonon qimageblitz soprano threadweaver
WANTLIB += chm djvulibre epub freetype poppler-qt4 qca spectre
WANTLIB += jpeg tiff

MODKDE4_USE =	pim

LIB_DEPENDS = 	devel/chmlib \
		devel/ebook-tools \
		graphics/djvulibre \
		graphics/tiff \
		print/freetype \
		print/libspectre \
		print/poppler,-qt4 \
		security/qca2 \
		x11/kde48/qimageblitz

.include <bsd.port.mk>
