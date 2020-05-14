DIRS = libmseed \
	#fftw \
	#liquid-dsp \ 
	ms2ampmax \
	ms2ampmax0 \
	ms2fft \
	ms2fft0 \
	ms2filter \
	ms2go \
	ms2rms

.PHONY: all clean

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
	(
		echo; \
		echo "<<<<<<< Compiling stuff: $$i >>>>>>>"; \
		cd $$i; \
		${MAKE} all; \
		cd ..; \
	); done \

clean:
