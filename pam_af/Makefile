# Ports collection makefile for:	pam_af
# Date created:				5 Marth 2006
# Whom:					Stanislav Sedov <ssedov@mbsd.msk.ru>
#
# $FreeBSD: ports/security/pam_af/Makefile,v 1.9 2011/10/24 03:33:14 stas Exp $
#

PORTNAME=	pam_af
PORTVERSION=	1.0.2
PORTREVISION=	0
CATEGORIES=	security
MASTER_SITES=	http://mbsd.msk.ru/dist/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Anti-bruteforce PAM module

USE_BZIP2=	yes

MAN8=		pam_af.8 pam_af_tool.8

do-install:
	${INSTALL_DATA} ${WRKSRC}/pam_af.so ${STAGEDIR}${PREFIX}/lib
	${INSTALL_PROGRAM} ${WRKSRC}/pam_af_tool/pam_af_tool ${STAGEDIR}${PREFIX}/sbin
	${INSTALL_MAN} ${WRKSRC}/pam_af.8 ${STAGEDIR}${MANPREFIX}/man/man8
	${INSTALL_MAN} ${WRKSRC}/pam_af_tool/pam_af_tool.8 ${STAGEDIR}${MANPREFIX}/man/man8

post-install:
.if !defined(NOPORTDOCS)
	${MKDIR} ${STAGEDIR}${DOCSDIR}
	${INSTALL_DATA} ${WRKSRC}/README ${STAGEDIR}${DOCSDIR}
.endif

.include <bsd.port.mk>
