# Detect 6 facial emotions: anger, disgust, fear, happy, pain and sad with EfficientNetB0 

Project based on image classification

## Device

[JETSON-IO-BASE-A - Custom model from Waveshare](https://www.waveshare.com/jetson-nano-dev-kit-a.htm)

OS Ubuntu 18.04.6

Jetpack 4.6.1 (L4T R32.6.1)

[Flashed following this wiki page](https://www.waveshare.com/wiki/JETSON-NANO-DEV-KIT)

## Dependencies

- [jetcam](https://github.com/NVIDIA-AI-IOT/jetcam)
- [opencv](https://github.com/opencv/opencv)
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

The data for training, validation, and testing the model was downloaded from [Google Drive](https://drive.google.com/file/d/1NFapaYLKhER7Z4M_eP4tns9TQ3ywCZU9/view?usp=sharing). In the script trainingEmotions.ipynb, the data was divided as follows
- anger_path = "/home/nvinhhung/nvidia/data/faceEmotions/anger"
- disgust_path = "/home/nvinhhung/nvidia/data/faceEmotions/disgust"
- fear_path = "/home/nvinhhung/nvidia/data/faceEmotions/fear"
- happy_path = "/home/nvinhhung/nvidia/data/faceEmotions/happy"
- pain_path = "/home/nvinhhung/nvidia/data/faceEmotions/pain"
- sad_path = "/home/nvinhhung/nvidia/data/faceEmotions/sad"

## Some note
- To install the libraries needed to run the above script, I used a virtual environment created with Conda.
- Install TensorFlow using the following command to use the GPU provided by NVIDIA.
pip3 install --pre --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v46 tensorflow==2.5.0+nv21.08

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
- conda install h5py
- conda install pip
- pip3 install jupyterlab
- pip3 install 'Cython<3'
- pip3 install pillow
- pip3 install --pre --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v46 tensorflow==2.5.0+nv21.08

wiki: https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html#overview__section_z4r_vjd_v2c)

wiki: https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html)

- pip uninstall keras
- pip install keras==2.6
- pip install opencv-python
- pip install pandas
- pip install seaborn
- pip install scikit-learn
- pip install matplotlib


## packages are installed by pip
Package                 Version
----------------------- ----------------
absl-py                 0.12.0
anyio                   3.6.2
argon2-cffi             21.3.0
argon2-cffi-bindings    21.2.0
astunparse              1.6.3
async-generator         1.10
attrs                   22.2.0
Babel                   2.11.0
backcall                0.2.0
bleach                  4.1.0
cached-property         1.5.2
cachetools              4.2.4
certifi                 2024.8.30
cffi                    1.15.1
charset-normalizer      2.0.12
clang                   5.0
contextvars             2.4
cycler                  0.11.0
Cython                  0.29.37
dataclasses             0.8
decorator               5.1.1
defusedxml              0.7.1
entrypoints             0.4
flatbuffers             1.12
gast                    0.4.0
google-auth             1.35.0
google-auth-oauthlib    0.4.6
google-pasta            0.2.0
grpcio                  1.48.2
h5py                    3.1.0
idna                    3.10
immutables              0.19
importlib-metadata      4.8.3
ipykernel               5.5.6
ipython                 7.16.3
ipython-genutils        0.2.0
jedi                    0.17.2
Jinja2                  3.0.3
joblib                  1.1.1
json5                   0.9.16
jsonschema              3.2.0
jupyter-client          7.1.2
jupyter-core            4.9.2
jupyter-server          1.13.1
jupyterlab              3.2.9
jupyterlab-pygments     0.1.2
jupyterlab-server       2.10.3
keras                   2.6.0
Keras-Preprocessing     1.1.2
kiwisolver              1.3.1
Markdown                3.3.7
MarkupSafe              2.0.1
matplotlib              3.3.4
mistune                 0.8.4
nbclassic               0.3.5
nbclient                0.5.9
nbconvert               6.0.7
nbformat                5.1.3
nest-asyncio            1.6.0
notebook                6.4.10
numpy                   1.19.5
oauthlib                3.2.2
opencv-python           4.10.0.84
opt-einsum              3.3.0
packaging               21.3
pandas                  1.1.5
pandocfilters           1.5.1
parso                   0.7.1
pexpect                 4.9.0
pickleshare             0.7.5
Pillow                  8.4.0
pip                     21.3.1
prometheus-client       0.17.1
prompt-toolkit          3.0.36
protobuf                3.19.6
ptyprocess              0.7.0
pyasn1                  0.5.1
pyasn1-modules          0.3.0
pycparser               2.21
Pygments                2.14.0
pyparsing               3.1.4
pyrsistent              0.18.0
python-dateutil         2.9.0.post0
pytz                    2024.2
pyzmq                   25.1.2
requests                2.27.1
requests-oauthlib       2.0.0
rsa                     4.9
scikit-learn            0.24.2
scipy                   1.5.4
seaborn                 0.11.2
Send2Trash              1.8.3
setuptools              58.0.4
six                     1.15.0
sniffio                 1.2.0
tensorboard             2.6.0
tensorboard-data-server 0.6.1
tensorboard-plugin-wit  1.8.1
tensorflow              2.6.2+nv21.12
tensorflow-estimator    2.6.0
termcolor               1.1.0
terminado               0.12.1
testpath                0.6.0
threadpoolctl           3.1.0
torch                   1.10.0
torchvision             0.11.0a0+fa347eb
tornado                 6.1
traitlets               4.3.3
typing-extensions       3.7.4.3
urllib3                 1.26.20
wcwidth                 0.2.13
webencodings            0.5.1
websocket-client        1.3.1
Werkzeug                2.0.3
wheel                   0.37.1
wrapt                   1.12.1
zipp                    3.6.0
