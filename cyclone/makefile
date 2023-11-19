CFLAGS = -Wall -g -O0 -std=gnu11

CYCLONE_DDS_HOME = ${HOME}/cyclone_dds_install
CYCLONE_DDS_BIN = ${CYCLONE_DDS_HOME}/bin
CYCLONE_DDS_INC = ${CYCLONE_DDS_HOME}/include
CYCLONE_DDS_LIB = ${CYCLONE_DDS_HOME}/lib64

CPPINCS = -I${CYCLONE_DDS_INC}
LIBS = -lddsc

GENERATED_FILES = HelloWorldData.c HelloWorldData.h

all: publisher subscriber

${GENERATED_FILES}: HelloWorldData.idl
	${CYCLONE_DDS_HOME}/bin/idlc $^

publisher: publisher.c ${GENERATED_FILES}
	${CC} ${CPPINCS} ${CFLAGS} -o $@ $^  -L${CYCLONE_DDS_LIB}/  ${LIBS}

subscriber: subscriber.c ${GENERATED_FILES}
	${CC} ${CPPINCS} ${CFLAGS} -o $@ $^  -L${CYCLONE_DDS_LIB}/  ${LIBS}

clean:
	-rm -f ${GENERATED_FILES} publisher subscriber
