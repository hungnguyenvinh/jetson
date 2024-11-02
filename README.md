# Detect 6 facial emotions: anger, disgust, fear, happy, pain and sad with EfficientNetB0 

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
- 
- pip3 install jupyterlab
- pip3 install 'Cython<3'
- pip3 install pillow
- pip install opencv-python



- pip uninstall keras
- pip install keras==2.6
- pip install opencv-python
- pip install pandas
- pip install seaborn
- pip install scikit-learn
- pip install matplotlib
