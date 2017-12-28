FROM tensorflow/tensorflow:1.3.0-py3
#FROM tensorflow/tensorflow:1.3.0-gpu-py3

# Various Python and C/build deps
RUN apt-get update && apt-get install -y \ 
    wget \
    build-essential \ 
    cmake \ 
    git \
    unzip \ 
    pkg-config \
    python-dev \ 
    python-opencv \ 
    libopencv-dev \ 
    libav-tools  \ 
    libjpeg-dev \ 
    libpng-dev \ 
    libtiff-dev \ 
    libjasper-dev \ 
    libgtk2.0-dev \ 
    python-numpy \ 
    python-pycurl \ 
    libatlas-base-dev \
    gfortran \
    webp \ 
    python-opencv \ 
    qt5-default \
    libvtk6-dev \ 
    zlib1g-dev 


COPY jupyter_notebook_config.py /root/.jupyter/
COPY run_jupyter.sh /
RUN chmod +x /run_jupyter.sh
WORKDIR "/notebooks" 
RUN pip install keras

## Install openai gym
RUN apt-get update && apt-get install -y python-numpy python-dev cmake zlib1g-dev libjpeg-dev xvfb libav-tools xorg-dev python-opengl libboost-all-dev libsdl2-dev swig
RUN pip install gym[all]
RUN jupyter nbextension enable --py --sys-prefix widgetsnbextension
RUN apt-get install -y xvfb
RUN apt-get update && apt-get install -y imagemagick
RUN pip install tqdm

RUN apt-get install -y git

RUN pip install scikit-image
RUN pip install git+https://github.com/jakevdp/JSAnimation.git
RUN pip install scikit-image
#RUN pip install scikit-image
RUN apt-get update && apt-get install -y python-pyglet
CMD ["/run_jupyter.sh"]

