COMMENT = embeddable prototype-based language

BASENAME = Io-20111130
PKGNAME = io-20111130
DISTNAME = ${PKGNAME}
CATEGORIES = lang
MASTER_SITES =  http://static.eradman.com/code/
DISTFILES = ${DISTNAME}.tar.gz

HOMEPAGE = http://www.iolanguage.org/
MAINTAINER = Eric Radman <ericshane@eradman.com>

# BSD
PERMIT_PACKAGE_CDROM = Yes
PERMIT_PACKAGE_FTP = Yes
PERMIT_DISTFILES_CDROM = Yes
PERMIT_DISTFILES_FTP = Yes

WANTLIB = edit event expat m pthread readline z

LIB_DEPENDS = devel/libeventextra devel/pcre devel/libyajl textproc/libxml

MODULES = devel/cmake

WRKDIST = ${WRKDIR}/eradman-io-d1d8bac
WRKBUILD = ${WRKSRC}/build

MODCMAKE_VERBOSE = No

do-regress:
	cd ${WRKBUILD} && _build/binaries/io ../libs/iovm/tests/correctness/run.io

.include <bsd.port.mk>
