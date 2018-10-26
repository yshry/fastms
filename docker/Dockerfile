FROM nvidia/cuda:6.5-devel-ubuntu14.04

RUN apt-get update \
  && apt-get upgrade -y \
  && apt-get install -y unzip wget build-essential \
    cmake git pkg-config libswscale-dev \
    python3-dev python3-numpy \
    libtbb2 libtbb-dev libjpeg-dev \
    libpng-dev libtiff-dev libjasper-dev 

RUN cd \
  && wget https://github.com/Itseez/opencv/archive/2.4.13.6.zip \
  && unzip 2.4.13.6.zip \
  && cd opencv-2.4.13.6 \
  && mkdir build \
  && cd build \
  && cmake .. \
  && make -j3 \
  && make install \
  && cd \
  && rm 2.4.13.6.zip 
