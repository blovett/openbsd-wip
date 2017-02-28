COMMENT =	installs various ruby versions and implementations
CATEGORIES =	devel
HOMEPAGE =	https://github.com/rbenv/ruby-build

MAINTAINER =	Ben Lovett <ben@tilderoot.com>

GH_ACCOUNT =	rbenv
GH_PROJECT =	ruby-build
GH_TAGNAME =	v20170201

BUILD_DEPENDS =	shells/bash
RUN_DEPENDS =	devel/autoconf/2.69 \
		shells/bash

# MIT
PERMIT_PACKAGE_CDROM =	yes

NO_BUILD =	yes

do-test:
	@cd ${WRKSRC} && ./bin/ruby-build --definitions | grep -q 2.0.0

do-install:
	@cd ${WRKSRC} && ./install.sh

.include <bsd.port.mk>
