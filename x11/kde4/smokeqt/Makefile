# $OpenBSD$

SHARED_ONLY =	Yes

CATEGORIES =	devel
COMMENT =	introspective wrappers around the Qt
DISTNAME =	smokeqt-${MODKDE_VERSION}

WANTLIB = m stdc++
WANTLIB += lib/qt4/Qt3Support lib/qt4/QtDBus lib/qt4/QtDeclarative
WANTLIB += lib/qt4/QtGui lib/qt4/QtHelp lib/qt4/QtMultimedia
WANTLIB += lib/qt4/QtNetwork lib/qt4/QtOpenGL lib/qt4/QtScript
WANTLIB += lib/qt4/QtSql lib/qt4/QtSvg lib/qt4/QtTest lib/qt4/QtWebKit
WANTLIB += lib/qt4/QtXml lib/qt4/QtXmlPatterns lib/qt4/phonon
WANTLIB += qimageblitz smokebase
WANTLIB += qscintilla2 qwt 

SHARED_LIBS =	smokephonon		0.0 # 3.0
SHARED_LIBS +=	smokeqimageblitz	0.0 # 3.0
SHARED_LIBS +=	smokeqsci		0.0 # 3.0
SHARED_LIBS +=	smokeqt3support		0.0 # 3.0
SHARED_LIBS +=	smokeqtcore		0.0 # 3.0
SHARED_LIBS +=	smokeqtdbus		0.0 # 3.0
SHARED_LIBS +=	smokeqtdeclarative	0.0 # 3.0
SHARED_LIBS +=	smokeqtgui		0.0 # 3.0
SHARED_LIBS +=	smokeqthelp		0.0 # 3.0
SHARED_LIBS +=	smokeqtmultimedia	0.0 # 3.0
SHARED_LIBS +=	smokeqtnetwork		0.0 # 3.0
SHARED_LIBS +=	smokeqtopengl		0.0 # 3.0
SHARED_LIBS +=	smokeqtscript		0.0 # 3.0
SHARED_LIBS +=	smokeqtsql		0.0 # 3.0
SHARED_LIBS +=	smokeqtsvg		0.0 # 3.0
SHARED_LIBS +=	smokeqttest		0.0 # 3.0
SHARED_LIBS +=	smokeqtuitools		0.0 # 3.0
SHARED_LIBS +=	smokeqtwebkit		0.0 # 3.0
SHARED_LIBS +=	smokeqtxml		0.0 # 3.0
SHARED_LIBS +=	smokeqtxmlpatterns	0.0 # 3.0
SHARED_LIBS +=	smokeqwt		0.0 # 3.0

MODULES =	lang/ruby

MODKDE4_USE =

# reminder: flesh out the build_depends here...
#BUILD_DEPENDS =	
LIB_DEPENDS =	editors/qscintilla \
		x11/kde4/qimageblitz \
		x11/kde4/smokegen \
		x11/qwt

.include <bsd.port.mk>
