# $OpenBSD: Makefile.template,v 1.75 2016/03/20 17:19:49 naddy Exp $

COMMENT =	web application framework for writing scalable web APIs in C

GH_ACCOUNT =	jorisvink
GH_PROJECT =	kore
GH_TAGNAME =	1.2.3-release

PKGNAME = 	${DISTNAME:S/-release//}

CATEGORIES =	www

HOMEPAGE =	https://kore.io/

MAINTAINER =	Frederic Cambus <fred@statdns.com>

# ISC
PERMIT_PACKAGE_CDROM =	Yes

WANTLIB +=	c crypto pthread ssl z

FLAVORS =	pgsql
FLAVOR ?=

.if ${FLAVOR} == "pgsql"
MAKE_ENV =	PGSQL=1
WANTLIB +=	pq
LIB_DEPENDS +=	databases/postgresql,-main
.endif

CONFIGURE_STYLE = none

USE_GMAKE =	Yes
MAKE_ENV +=	DEBUG=1 TASKS=1

NO_TEST =	Yes

.include <bsd.port.mk>