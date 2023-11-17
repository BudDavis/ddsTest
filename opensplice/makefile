CFLAGS=-Wall -g -O0 -std=gnu11
CINCS = -I${OSPL_HOME}/include/dcps/C/SAC/

GENERATED_FILES= HelloWorldDataDcps.h  HelloWorldDataSacDcps.h  HelloWorldDataSplDcps.h \
                 HelloWorldData.h      HelloWorldDataSacDcps.c    HelloWorldDataSplDcps.c


default:HelloWorldDataPublisher

${GENERATED_FILES}: HelloWorldData.idl
	${OSPL_HOME}/bin/idlpp -l c HelloWorldData.idl

COMMON_FILES= DDSEntitiesManager.c HelloWorldDataPublisher.c CheckStatus.c

HelloWorldDataPublisher: ${GENERATED_FILES} ${COMMON_FILES}
	${CC} -o HelloWorldDataPublisher ${COMMON_FILES} \
		${CFLAGS} ${CINCS} ${GENERATED_FILES} \
		-L${OSPL_HOME}/lib \
		-ldcpssac -lddskernel
clean:
	-rm -f ${GENERATED_FILES} HelloWorldDataPublisher HelloWorldDataSubscriber

