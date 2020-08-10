## ms_bundle
Bundle for manipulate with miniSEED data.

## Installation
### Install with Git 
```
## clone the repository
$ git clone --depth 1 --recurse-submodules https://github.com/Cuda-Chen/ms_bundle.git

## compile and install
$ cd src
$ make download
$ make
$ make install
```

### Install with ZIP File
```
## extract the ZIP file downloaded from GitHub Release part
$ unzip ms_bundle.zip

## compile and install
## no need to download FFTW tar ball since I have attached in the ZIP file
$ cd src
$ make
$ make install
```

## Where're the Built Programs?
All of the built programs are in `bin` directory.

## A Note How to Clone Git Submodules
https://stackoverflow.com/questions/3796927/how-to-git-clone-including-submodules
