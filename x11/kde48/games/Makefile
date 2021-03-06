# $OpenBSD: Makefile,v 1.10 2010/11/22 08:37:02 espie Exp $

COMMENT =	K Desktop Environment, games
DISTNAME =	kdegames-${MODKDE_VERSION}

SHARED_LIBS =	kdegames             5.0      # .4.0
SHARED_LIBS +=	kmahjongglib         0.0      # .1.0
SHARED_LIBS +=	kggzgames            0.0      # .4.0
SHARED_LIBS +=	kggzmod              0.0      # .4.0
SHARED_LIBS +=	kggznet              0.0      # .4.0
SHARED_LIBS +=	kolfprivate          0.0      # .4.0
SHARED_LIBS +=	pala          	     0.0      # .0.1
SHARED_LIBS +=	iris_ksirk    	     0.0      # .2.0

WANTLIB =  c m pthread stdc++ z
WANTLIB += GL GLU ICE SM X11 Xext
WANTLIB += lib/qt4/Qt3Support lib/qt4/QtDBus lib/qt4/QtGui
WANTLIB += lib/qt4/QtNetwork lib/qt4/QtOpenGL
WANTLIB += lib/qt4/QtSvg lib/qt4/QtXml 
WANTLIB += kdeui kdnssd kfile kio knewstuff2 knewstuff3
WANTLIB += knotifyconfig phonon>=6
WANTLIB += openal qca sndfile

MODULES =	devel/cmake lang/python

LIB_DEPENDS =	multimedia/phonon \
		audio/openal \
		audio/libsndfile \
		devel/py-twisted/core \
		games/ggz/ggz-client-libs \
		math/qhull \
		security/qca2 \
		x11/kde48/py-kde

# for Kajongg to avoid build-time dependency and for GGZ
CONFIGURE_ARGS =	-DINSTALL_KAJONGG:Bool=True \
			-DGGZ_FORCEREGISTRY:Bool=True

MODPY_ADJ_FILES =	kajongg/setup.py \
			kajongg/src/deferredutil.py \
			kajongg/src/kajonggtest.py \
			kajongg/src/kajonggserver.py \
			kajongg/src/scoringtest.py \
			kajongg/src/kajongg.py \
			kajongg/src/server.py

.include <bsd.port.mk>
