CFLAGS = -Wall -g -O0 -std=gnu11

CYCLONE_DDS_HOME = ${HOME}/install
CYCLONE_DDS_BIN = ${CYCLONE_DDS_HOME}/bin
CYCLONE_DDS_INC = ${CYCLONE_DDS_HOME}/include
CYCLONE_DDS_LIB = ${CYCLONE_DDS_HOME}/lib

CPPINCS = -I${CYCLONE_DDS_INC}
LIBS = -lddsc
LD_FLAGS="-Wl,-rpath=/home/bdavis/install/lib"
GENERATED_FILES = HelloWorldData.c HelloWorldData.h

all: publisher subscriber

${GENERATED_FILES}: HelloWorldData.idl
	${CYCLONE_DDS_HOME}/bin/idlc $^

publisher: publisher.c ${GENERATED_FILES}
	${CC} ${CPPINCS} ${CFLAGS} -o $@ $^ ${LD_FLAGS}  -L${CYCLONE_DDS_LIB}/  ${LIBS}

subscriber: subscriber.c ${GENERATED_FILES}
	${CC} ${CPPINCS} ${CFLAGS} -o $@ $^ ${LD_FLAGS} -L${CYCLONE_DDS_LIB}/  ${LIBS}

clean:
	-rm -f ${GENERATED_FILES} publisher subscriber
