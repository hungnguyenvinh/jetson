# Detect 6 facial emotions: anger, disgust, fear, happy, pain and sad with Xception

Project based on image classification

## Device

[JETSON-IO-BASE-A - Custom model from Waveshare](https://www.waveshare.com/jetson-nano-dev-kit-a.htm)

OS Ubuntu 18.04

Jetpack 4.6 (L4T R32.6.1)

[Flashed following this wiki page](https://www.waveshare.com/wiki/JETSON-NANO-DEV-KIT)

## Dependencies

- [Opencv-4.5.1](https://www.youtube.com/watch?v=P-EZr0zy53g&list=PLv8Cp2NvcY8AkXRldCAYCvFxRUs0h5JJF&index=3)
- [Jolov9](https://github.com/spacewalk01/yolov9-face-detection.git)
- [Jupyter Lab](https://jupyter.org/)

## Start Project

To start the project, open the folder in Jupyter Lab using command
```
jupyter lab --no-browser
```

In case you want to remote to jupyter lab, use this command instead
```
jupyter lab --ip xx.xx.xx.xx --port 8888 --no-browser
```
Where xx.xx.xx.xx is your current ip in ifconfig, after this, other PCs in the same network can use xx.xx.xx.xx:8888 to access it, there should be token showed in the console where you run the command, use it for authentication

File trainingEmotions.ipynb
- Use to train the model

File live-detection.ipynb
- Live detection face emotions

The data for training, validation, and testing the model was downloaded from [Google Drive](https://drive.google.com/file/d/1NFapaYLKhER7Z4M_eP4tns9TQ3ywCZU9/view?usp=sharing). In the script trainingEmotions.ipynb, the data was divided as folders following: anger, disgust, fear, happy, pain and sad.

## Some note
- To install the libraries needed to run the above script, I used a virtual environment created with Conda.
- Use opencv for camera real time
- Use joloV9 to detect face/person

## some commands to install lib and env
- sudo apt-get install python3-pip
- sudo apt-get install python3-pip libopenblas-base libopenmpi-dev libomp-dev
- wget https://github.com/conda-forge/miniforge/releases/latest/download/Miniforge3-Linux-aarch64.sh
- chmod +x Miniforge3-Linux-aarch64.sh
- ./Miniforge3-Linux-aarch64.sh
- (add more 'export PATH="$HOME/miniconda3/bin:$PATH"' into your .bashrc)
- source ~/.bashrc
- conda --version
- conda create -n myenv python=3.6.9
- conda activate myenv
- conda install pip
- pip3 install --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v46 tensorflow==2.6.2+nv21.12
- wget https://nvidia.box.com/shared/static/fjtbno0vpo676a25cgvuqc1wty0fkkg6.whl
- pip3 install torch-1.10.0-cp36-cp36m-linux_aarch64.whl
- pip3 install jupyterlab
- pip3 install 'Cython<3' pillow keras==2.6 pandas seaborn scikit-learn matplotlib

### How to install opencv
#### Install these Dependencies before installing OpenCV
- sudo sh -c "echo '/usr/local/cuda/lib64' >> /etc/ld.so.conf.d/nvidia-tegra.conf“
- sudo ldconfig
- sudo apt-get install build-essential cmake git unzip pkg-config
- sudo apt-get install libjpeg-dev libpng-dev libtiff-dev
- sudo apt-get install libavcodec-dev libavformat-dev libswscale-dev
- sudo apt-get install libgtk2.0-dev libcanberra-gtk*
- sudo apt-get install python3-dev python3-numpy python3-pip
- sudo apt-get install libxvidcore-dev libx264-dev libgtk-3-dev
- sudo apt-get install libtbb2 libtbb-dev libdc1394-22-dev
- sudo apt-get install libv4l-dev v4l-utils
- sudo apt-get install libgstreamer1.0-dev libgstreamer-plugins-base1.0-dev
- sudo apt-get install libavresample-dev libvorbis-dev libxine2-dev
- sudo apt-get install libfaac-dev libmp3lame-dev libtheora-dev
- sudo apt-get install libopencore-amrnb-dev libopencore-amrwb-dev
- sudo apt-get install libopenblas-dev libatlas-base-dev libblas-dev
- sudo apt-get install liblapack-dev libeigen3-dev gfortran
- sudo apt-get install libhdf5-dev protobuf-compiler
- sudo apt-get install libprotobuf-dev libgoogle-glog-dev libgflags-dev
#### Download and Install opencv
- Download OpenCV: <br>
cd ~ <br>
wget -O opencv.zip https://github.com/opencv/opencv/archive/4.5.1.zip <br>
wget -O opencv_contrib.zip https://github.com/opencv/opencv_contrib/archive/4.5.1.zip <br>
unzip opencv.zip <br>
unzip opencv_contrib.zip <br>

- Now rename the directories. Type each command below, one after the other. <br>
mv opencv-4.5.1 opencv <br>
mv opencv_contrib-4.5.1 opencv_contrib <br>
rm opencv.zip <br>
rm opencv_contrib.zip <br>

- Lets build OpenCV now: <br>
cd ~/opencv <br>
mkdir build <br>
cd build <br>

- copy and paste this entire block of commands below into your terminal. <br>

cmake -D CMAKE_BUILD_TYPE=RELEASE -D CMAKE_INSTALL_PREFIX=/usr -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib/modules -D EIGEN_INCLUDE_PATH=/usr/include/eigen3 -D WITH_OPENCL=OFF -D WITH_CUDA=ON -D CUDA_ARCH_BIN=5.3 -D CUDA_ARCH_PTX="" -D WITH_CUDNN=ON -D WITH_CUBLAS=ON -D ENABLE_FAST_MATH=ON -D CUDA_FAST_MATH=ON -D OPENCV_DNN_CUDA=ON -D ENABLE_NEON=ON -D WITH_QT=OFF -D WITH_OPENMP=ON -D WITH_OPENGL=ON -D BUILD_TIFF=ON -D WITH_FFMPEG=ON -D WITH_GSTREAMER=ON -D WITH_TBB=ON -D BUILD_TBB=ON -D BUILD_TESTS=OFF -D WITH_EIGEN=ON -D WITH_V4L=ON -D WITH_LIBV4L=ON -D OPENCV_ENABLE_NONFREE=ON -D INSTALL_C_EXAMPLES=OFF -D INSTALL_PYTHON_EXAMPLES=OFF -D BUILD_NEW_PYTHON_SUPPORT=ON -D BUILD_opencv_python3=TRUE -D OPENCV_GENERATE_PKGCONFIG=ON -D BUILD_EXAMPLES=OFF ..

- Build OpenCV. This command below will take a long time (around 2 hours), make -j4     # (make then space single dash and then j4) <br>

- Finish the install: <br>
cd ~ <br>
sudo rm -r /usr/include/opencv4/opencv2 <br>
cd ~/opencv/build <br>
sudo make install <br>
sudo ldconfig <br>
make clean <br>
sudo apt-get update <br>
