# $OpenBSD$

SHARED_ONLY =	Yes

CATEGORIES =	devel x11/kde48
COMMENT =	generator for wrappers around the Qt and KDE
DISTNAME =	smokegen-${MODKDE_VERSION}

SHARED_LIBS =	smokebase		0.0 # 3.0
SHARED_LIBS +=	cppparser		0.0

WANTLIB =  c m pthread stdc++
WANTLIB += lib/qt4/QtXml

MODKDE4_USE =

NO_REGRESS =	Yes

.include <bsd.port.mk>
