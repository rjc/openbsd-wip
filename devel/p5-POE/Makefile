# $OpenBSD: Makefile,v 1.27 2017/12/02 11:34:17 espie Exp $

COMMENT=	portable multitasking and networking framework for perl

MODULES=	cpan
PKG_ARCH=	*
DISTNAME=	POE-1.367
CATEGORIES=	devel
FIX_EXTRACT_PERMISSIONS=	Yes

HOMEPAGE=	http://poe.perl.org/

# perl
PERMIT_PACKAGE_CDROM=	Yes

CONFIGURE_ARGS=	--default

RUN_DEPENDS=	devel/p5-Curses \
		devel/p5-IO-Pipely \
		devel/p5-IO-Tty \
		devel/p5-POE-Test-Loops>=1.360 \
		net/p5-Socket6 \
		www/p5-libwww
TEST_DEPENDS=	devel/p5-Term-Size \
		net/p5-Socket-GetAddrInfo

MAKE_ENV=	TEST_POD=Yes

MODCPAN_EXAMPLES=	Yes

post-build:
	# XXX prevent gen-tests from running again during fake
	touch ${WRKDIST}/lib/POE.pm

.include <bsd.port.mk>
