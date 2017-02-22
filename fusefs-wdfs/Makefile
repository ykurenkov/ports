# Created by: Gyorgy Teubel <tgyurci@freemail.hu>
# $FreeBSD: tags/RELEASE_10_0_0/sysutils/fusefs-wdfs/Makefile 327772 2013-09-20 23:05:58Z bapt $

PORTNAME=	wdfs
PORTVERSION=	1.4.2
PORTREVISION=	4
CATEGORIES=	local/sysutils
MASTER_SITES=	http://noedler.de/projekte/wdfs/
PKGNAMEPREFIX=	fusefs-

MAINTAINER=	kamikaze@bsdforen.de
COMMENT=	Mount remote WedDAV directories with Fuse

#LIB_DEPENDS=	neon.29:${PORTSDIR}/www/neon29
#LIB_DEPENDS=	libneon.so:${PORTSDIR}/www/neon29
LIB_DEPENDS=	libneon.so:${PORTSDIR}/www/neon

GNU_CONFIGURE=	yes
USES=		fuse pkgconfig
USE_GNOME=	glib20

PLIST_FILES=	bin/wdfs

.include "../Mk/local.port.mk"
.include <bsd.port.mk>
