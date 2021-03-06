# $OpenBSD: Makefile,v 1.193 2011/10/28 13:01:13 robert Exp $

COMMENT =	Mozilla web browser
BROKEN-sparc64 =	https://bugzilla.mozilla.org/show_bug.cgi?id=577056

# Don't forget to bump www/firefox-i18n after updates.
# Don't forget to update devel/xulrunner/2.0 if patches changes.

MOZILLA_VERSION =	8.0.1
MOZILLA_BRANCH =	release
MOZILLA_PROJECT =	firefox
MOZILLA_CODENAME =	browser

# url for beta releases
# MASTER_SITES=  ftp://ftp.mozilla.org/pub/mozilla.org/${MOZILLA_PROJECT}/releases/${MOZILLA_VERSION}/source/
SO_VERSION =	27.0
# NOTE: Must bump minor version if any shlib's are removed from the
# components dir to avoid pkg_add -r issues.
MOZILLA_LIBS =	browsercomps mozalloc \
		xpcom xul

CATEGORIES =	www

# mozilla public license
PERMIT_PACKAGE_CDROM=	Yes
PERMIT_PACKAGE_FTP=	Yes
PERMIT_DISTFILES_CDROM=	Yes
PERMIT_DISTFILES_FTP=	Yes

# lots of logic in mozilla.port.mk
MODULES =	www/mozilla devel/gettext lang/python

MODPY_RUNDEP =	No

USE_GROFF =	Yes
# Regression tests are too hard to adapt to run here
NO_REGRESS =	Yes

CONFIGURE_STYLE =	autoconf no-autoheader
CONFIGURE_ARGS +=	--enable-official-branding
CONFIGURE_ARGS +=	--with-system-libevent=/usr/ --disable-gconf
CONFIGURE_ARGS +=	--with-system-zlib=/usr/ --with-system-bz2=${LOCALBASE}
WANTLIB +=	event

.if ${MACHINE_ARCH:Msparc64}
CONFIGURE_ARGS +=	--disable-tracejit --disable-methodjit
.endif

# needed during make install
BUILD_DEPENDS +=	archivers/unzip

# ensure we depend on cairo with tee backend enabled
LIB_DEPENDS =	graphics/cairo>=1.10.2p0
# --with-system-png=${LOCALBASE}
# no system png : apng support not bundled in

MOZILLA_AUTOCONF_DIRS +=	js/src
MOZILLA_SUBST_FILES +=		config/autoconf.mk.in services/crypto/modules/WeaveCrypto.js

SUBST_VARS +=	MOZILLA_VERSION NSS_SO_VERSION

post-install:
	${SUBST_CMD} -o ${SHAREOWN} -g ${SHAREGRP} -c ${FILESDIR}/mozilla-firefox.1 \
		${PREFIX}/man/man1/mozilla-firefox.1
	cd ${PREFIX}/man/man1/ && ln -sf mozilla-firefox.1 firefox.1
	cd ${PREFIX}/bin/ && ln -sf firefox mozilla-firefox
	# install desktop file
	${INSTALL_DATA_DIR} ${PREFIX}/share/applications/
	${SUBST_CMD} -o ${SHAREOWN} -g ${SHAREGRP} -c ${FILESDIR}/${MOZILLA_PROJECT}.desktop \
		${PREFIX}/share/applications/${MOZILLA_PROJECT}.desktop

	# link default48.png to default.png to be used by default by non-icccm compliant wm
	ln ${PREFIX}/lib/firefox-${MOZILLA_VERSION:C/b.//}/chrome/icons/default/default{48,}.png

.include <bsd.port.mk>
