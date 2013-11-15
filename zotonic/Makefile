# $FreeBSD$

PORTNAME=	zotonic
PORTVERSION=	0.9.4
CATEGORIES=	www
MASTER_SITES=	${MASTER_SITE_GOOGLE_CODE}

MAINTAINER=	marc.vanwoerkom@gmail.com
COMMENT=	Erlang Web Framework and Content Management System

LICENSE=	AL2

BUILD_DEPENDS=	erlc:${PORTSDIR}/lang/erlang
RUN_DEPENDS=	erl:${PORTSDIR}/lang/erlang
# TODO
# require erlang >= R14B03
# require imagemagick >= 6.5
# require postgresql >= 8.4

USES=		gmake iconv
USE_ZIP=	yes
WRKSRC=	${WRKDIR}/${PORTNAME}
# TODO
# check iconv handling on FreeBSD 10-CURRENT

APPDIR=		${PREFIX}/lib/erlang/lib/${PORTNAME}-${PORTVERSION}

.include <bsd.port.pre.mk>

do-build:
	@cd ${BUILD_WRKSRC}; \
		${GMAKE}

do-install:
	@${MKDIR} ${STAGEDIR}${APPDIR}
	@cd ${WRKSRC} && ${COPYTREE_SHARE} "src ebin" \
		${STAGEDIR}${APPDIR}

# TODO
# assist with enabling trust-authentication in postgresql
# see http://zotonic.com/docs/0.9/tutorials/preinstall.html

.include <bsd.port.post.mk>