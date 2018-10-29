FROM ubuntu:14.04

RUN apt-get update \
  && apt-get upgrade -y \
  && apt-get install -y unzip wget build-essential \
    cmake git pkg-config libswscale-dev \
    python3-dev python3-numpy \
    libtbb2 libtbb-dev libjpeg-dev \
    libpng-dev libtiff-dev libjasper-dev 

RUN apt-get install -y libgtk2.0-dev

RUN cd \
  && wget https://github.com/Itseez/opencv/archive/2.4.13.6.zip \
  && unzip 2.4.13.6.zip \
  && cd opencv-2.4.13.6 \
  && mkdir build \
  && cd build \
  && cmake -DBUILD_opencv_highgui=ON .. \
  && make -j3 \
  && make install \
  && cd \
  && rm 2.4.13.6.zip

RUN apt-get -y update \
  && apt-get install libcanberra-gtk-module

ENV LD_LIBRARY_PATH /usr/local/lib
WORKDIR /root
