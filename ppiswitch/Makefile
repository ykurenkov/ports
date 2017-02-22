PORTNAME=	ppiswitch	
PORTVERSION=	1.0
PORTREVISION=	1
CATEGORIES=	sysutils	
DISTNAME=	# intentionally left blank
EXTRACT_SUFX=	# intentionally left blank

MAINTAINER=	yuri.kurenkov@gmail.com	
COMMENT=	Control programm for ppi(4)	

NOFETCHFILES=	yes
PLIST_FILES=	sbin/ppiswitch man/man8/ppiswitch.8.gz sbin/compreboot etc/compreboot.conf.sample
#MAN8=	ppiswitch.8
USE_RC_SUBR=	ppiswitch
SUB_FILES=	compreboot compreboot.conf.sample
PORT_DOCS=	circuit.txt
#USE_GCC=	yes

WRKSRC_SUBDIR=${PORTNAME}-${PORTVERSION}

post-extract:
	mkdir ${WRKSRC}
	cd ${FILESDIR} ; \
	${CP} -p * ${WRKSRC}

do-install:
	${INSTALL_PROGRAM} ${WRKSRC}/${PORTNAME} ${STAGEDIR}${PREFIX}/sbin
	${INSTALL_MAN} ${WRKSRC}/${PORTNAME}.8 ${STAGEDIR}${MANPREFIX}/man/man8
	${INSTALL_DATA} ${WRKSRC}/circuit.txt ${STAGEDIR}${DOCSDIR}
	${INSTALL_SCRIPT} ${WRKDIR}/compreboot ${STAGEDIR}${PREFIX}/sbin/compreboot
	${INSTALL_DATA} ${WRKDIR}/compreboot.conf.sample ${STAGEDIR}${PREFIX}/etc/compreboot.conf.sample

.include <bsd.port.mk>
