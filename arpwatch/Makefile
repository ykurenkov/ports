# Created by: Brian Somers <brian@FreeBSD.org>
# $FreeBSD: head/net-mgmt/arpwatch/Makefile 367236 2014-09-03 21:07:17Z antoine $

PORTNAME=	arpwatch
PORTVERSION=	2.1.a15
PORTREVISION=	8
CATEGORIES=	net-mgmt
MASTER_SITES=	ftp://ftp.ee.lbl.gov/ \
		GENTOO/distfiles
DISTNAME=	${PORTNAME}-${PORTVERSION:C/\.([^\.]*)$/\1/}

MAINTAINER=	ports@FreeBSD.org
COMMENT=	Monitor arp & rarp requests

LICENSE=	BSD3CLAUSE

GNU_CONFIGURE=	yes
CONFIGURE_ARGS=	--quiet
INSTALL_TARGET=	install install-man

SUB_FILES=	pkg-message
USE_RC_SUBR=	arpwatch

.ifdef ARPDIR
MAKE_ARGS=	ARPDIR=${ARPDIR}
DATADIR=	${ARPDIR}
.else
DATADIR=	${PREFIX}/${PORTNAME}	
.endif

SUB_LIST+=     DATADIR=${DATADIR}

post-install:
	${MKDIR} ${STAGEDIR}${DATADIR}
	for files in ethercodes.dat d.awk duplicates.awk euppertolower.awk e.awk p.awk; do \
		${INSTALL_DATA} ${WRKSRC}/$$files ${STAGEDIR}${DATADIR};	\
	done
	${INSTALL_SCRIPT} ${WRKSRC}/arp2ethers ${STAGEDIR}${DATADIR}
	${INSTALL_SCRIPT} ${WRKSRC}/massagevendor ${STAGEDIR}${DATADIR}

.include <bsd.port.mk>
