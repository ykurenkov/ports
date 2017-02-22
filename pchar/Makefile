# Created by: David O'Brien (obrien@NUXI.com)
# $FreeBSD: tags/RELEASE_10_0_0/net/pchar/Makefile 327755 2013-09-20 22:10:23Z bapt $

PORTNAME=	pchar
PORTVERSION=	1.5
CATEGORIES=	net ipv6
MASTER_SITES=	http://www.kitchenlab.org/www/bmah/Software/pchar/
MASTER_SITES+=	${MASTER_SITE_LOCAL}
MASTER_SITE_SUBDIR=	bmah

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Sandia Internet path characterization tool

GNU_CONFIGURE=	yes
MAN8=		pchar.8

CONFIGURE_ARGS= --with-pcap
CONFIGURE_ENV+=	ac_cv_sizeof_bool=1

PLIST_FILES=	sbin/pchar

PORTDOCS=	README CHANGES FAQ

.include <bsd.port.options.mk>

do-install:
	(cd ${WRKSRC} \
		&& ${INSTALL_PROGRAM} pchar ${STAGEDIR}${PREFIX}/sbin/pchar \
		&& ${INSTALL_DATA} pchar.8 ${STAGEDIR}${PREFIX}/man/man8/)


.if ${PORT_OPTIONS:MDOCS}
post-install:
	@${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${PORTDOCS:S|^|${WRKSRC}/|} ${STAGEDIR}${DOCSDIR}
.endif

.include <bsd.port.mk>
