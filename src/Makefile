DIRS = libmseed \
ms2ampmax \
ms2ampmax0 \
ms2fft \
ms2fft0 \
ms2filter \
ms2go \
ms2rms

FFTW_TARBALL = fftw-3.3.8.tar.gz
FFTW_DOWNLOAD_LINK = http://www.fftw.org/${FFTW_TARBALL}

.PHONY: all clean download 

all:
	cd fftw-3.3.8; \
	./configure; \
	${MAKE} all; \
	cd ..; \
	cd liquid-dsp; \
	./configure --enable-fftoverride; \
	${MAKE} all; \
	cd ..; \
	for i in ${DIRS}; do \
	(	echo; \
		echo "<<<<<<< Compiling stuff: $$i >>>>>>>"; \
		cd $$i; \
		${MAKE} static; \
		cd ..; \
	); done 

download:
	wget ${FFTW_DOWNLOAD_LINK}; \
	tar zxvf ${FFTW_TARBALL}; 

clean:
	cd fftw-3.3.8; \
	${MAKE} clean; \
	cd ..; \
	cd liquid-dsp; \
	${MAKE} clean; \
	cd ..; \
	for i in ${DIRS}; do \
	(	echo; \
		echo "<<<<<<< Cleaning stuff: $$i >>>>>>>"; \
		cd $$i; \
		${MAKE} clean; \
		cd ..; \
	); done 
