COMMENT =	ruby version manager
CATEGORIES =	devel
HOMEPAGE =	https://github.com/rbenv/rbenv#readme

MAINTAINER =	Ben Lovett <ben@tilderoot.com>

GH_ACCOUNT =	rbenv
GH_PROJECT =	rbenv
GH_TAGNAME =	v1.1.0

RUN_DEPENDS =	lang/ruby-build

# MIT
PERMIT_PACKAGE_CDROM =	yes

do-build:
	@cd ${WRKSRC} && ./src/configure
	@cd ${WRKSRC}/src && make

LIBEXEC_FILES = --version commands completions exec global help hooks init \
		local prefix realpath.dylib rehash root sh-rehash sh-shell \
		shims version version-file version-file-read \
		version-file-write version-name version-origin versions \
		whence which

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/bin/rbenv ${PREFIX}/bin
	${INSTALL_PROGRAM_DIR} ${PREFIX}/libexec/rbenv
	${INSTALL_PROGRAM} ${WRKSRC}/libexec/rbenv ${PREFIX}/libexec/rbenv
.for i in ${LIBEXEC_FILES}
	${INSTALL_PROGRAM} ${WRKSRC}/libexec/rbenv-${i} ${PREFIX}/libexec/rbenv
.endfor
.for i in completions rbenv.d
	${INSTALL_DATA_DIR} ${PREFIX}/share/rbenv/${i}
	${INSTALL_DATA} ${WRKSRC}/${i} ${PREFIX}/share/rbenv/${i}
.endfor

.include <bsd.port.mk>
