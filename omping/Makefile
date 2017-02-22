# New ports collection makefile for:	omping
# Date Created:				28 June 2013
# Whom:					Yuri Kurenkov <yuri.kurenkov@gmail.com>
#
#

PORTNAME=	omping
PORTVERSION=	0.0.4
PORTREVISION=	0
CATEGORIES=	net
MASTER_SITES=	https://fedorahosted.org/releases/o/m/omping/

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Tool to test IP multicast functionality

USE_GMAKE=	yes

MAN8=		omping.8
PLIST_FILES=	bin/omping

do-install:
	(cd ${WRKSRC} \
		&& ${INSTALL_PROGRAM} omping ${STAGEDIR}${PREFIX}/bin/omping \
		&& ${INSTALL_DATA} omping.8 ${STAGEDIR}${PREFIX}/man/man8/)

.include <bsd.port.mk>
