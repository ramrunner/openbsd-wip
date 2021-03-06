# $OpenBSD: Makefile,v 1.71 2011/10/03 21:29:53 landry Exp $

# keep in sync with working archs.. sigh
ONLY_FOR_ARCHS=	amd64 i386 powerpc

PKG_ARCH=	*

V=		8.0.1
NAME=		firefox-i18n
PKGNAME=	${NAME}-${V}

CATEGORIES=	www

HOMEPAGE=	http://www.mozilla.org/projects/l10n/

MAINTAINER=	Martynas Venckus <martynas@openbsd.org>

# Mozilla public license
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM= Yes
PERMIT_DISTFILES_FTP=	Yes

MASTER_SITES=	http://releases.mozilla.org/pub/mozilla.org/firefox/releases/${V}/linux-i686/xpi/ \
		ftp://ftp.mozilla.org/pub/mozilla.org/firefox/releases/${V}/linux-i686/xpi/

LANGUAGES=	af ak ar ast be bg bn-BD bn-IN br bs ca cs cy da de el en-GB en-US en-ZA eo \
		es-AR es-CL es-ES es-MX et eu fa fi fr fy-NL ga-IE gd gl gu-IN he \
		hi-IN hr hu hy-AM id \
		is it ja kk kn ko ku lg lt lv mai mk ml mr nb-NO nl nn-NO nso \
		or pa-IN pl pt-BR pt-PT rm ro ru si sk sl son sq sr sv-SE \
		ta-LK ta te th tr uk vi zh-CN zh-TW zu

BUILD_DEPENDS=	archivers/unzip
RUN_DEPENDS=	firefox-${V}:www/mozilla-firefox

DIST_SUBDIR=	mozilla/${NAME}-${V}
NO_BUILD=	Yes
NO_REGRESS=	Yes
EXTRACT_ONLY=

# define one language for the main package
SUBPACKAGE?=	-en-GB

.for i in ${LANGUAGES}
MULTI_PACKAGES+=-$i
DISTFILES+=	$i.xpi
PKGNAME-$i=	${NAME}-$i-${V}
COMMENT-$i=	$i language pack for Firefox
LPACKDIR-$i=	${PREFIX}/lib/firefox-$V/extensions/langpack-$i@firefox.mozilla.org
.endfor
PKGNAME-en-GB=	${NAME}-en-GB-${V}

# use the same for all subpackages
MESSAGE=	${PKGDIR}/MESSAGE
SUBST_VARS=	V

do-install:
	${INSTALL_DATA_DIR} ${PREFIX}/lib/firefox-$V/extensions
.for i in ${LANGUAGES}
	${INSTALL_DATA} ${FULLDISTDIR}/$i.xpi ${PREFIX}/lib/firefox-$V/extensions/langpack-$i@firefox.mozilla.org.xpi
.endfor

.include <bsd.port.mk>
