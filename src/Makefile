DIRS = ms2ampmax \
ms2ampmax0 \
ms2fft \
ms2fft0 \
ms2filter \
ms2go \
ms2rms
STATIC_MAKEFILES = Makefile_static

FFTW_VERSION = fftw-3.3.8
FFTW_TARBALL = ${FFTW_VERSION}.tar.gz
FFTW_DOWNLOAD_LINK = http://www.fftw.org/${FFTW_TARBALL}
FFTW_DIR = ${FFTW_VERSION}
FFTW_LIB_INSTALL_DIR = $(shell pwd)/${FFTW_VERSION}

.PHONY: all clean download

all:
	cd ${FFTW_DIR}; \
	./configure --prefix=${FFTW_LIB_INSTALL_DIR}; \
	${MAKE} all; \
	${MAKE} install; \
	cd ..; \
	cd liquid-dsp; \
	./bootstrap.sh; \
	./configure --enable-fftoverride; \
	${MAKE} all; \
	cd ..; \
	cd libmseed; \
	${MAKE} all; \
	cd ..; \
	for i in ${DIRS}; do \
	(	echo; \
		echo "<<<<<<< Compiling program: $$i >>>>>>>"; \
		cd $$i; \
		${MAKE} -f ${STATIC_MAKEFILES} FFTW_DIR_NAME=FFTW_DIR; \
		cd ..; \
	); done 

download:
	wget ${FFTW_DOWNLOAD_LINK}; \
	tar zxvf ${FFTW_TARBALL}; 

clean:
	cd ${FFTW_DIR}; \
	${MAKE} clean; \
	cd ..; \
	cd liquid-dsp; \
	${MAKE} clean; \
	cd ..; \
	for i in ${DIRS}; do \
	(	echo; \
		echo "<<<<<<< Cleaning program: $$i >>>>>>>"; \
		cd $$i; \
		${MAKE} -f ${STATIC_MAKEFILES} clean; \
		cd ..; \
	); done 
