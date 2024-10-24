# Detect 6 facial emotions: anger, disgust, fear, happy, pain and sad

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

## packages are installed by pip
Package                       Version
----------------------------- -------------------
apt-clone                     0.2.1
apturl                        0.5.2
asn1crypto                    0.24.0
beautifulsoup4                4.6.0
blinker                       1.4
Brlapi                        0.6.6
certifi                       2018.1.18
chardet                       3.0.4
click                         6.7
colorama                      0.3.7
cryptography                  2.1.4
cupshelpers                   1.0
cycler                        0.10.0
decorator                     4.1.2
defer                         1.0.6
distlib                       0.3.9
distro-info                   0.18ubuntu0.18.04.1
feedparser                    5.2.1
filelock                      3.4.1
html5lib                      0.999999999
httplib2                      0.9.2
idna                          2.6
importlib-metadata            4.8.3
importlib-resources           5.4.0
Jetson.GPIO                   2.0.17
keyring                       10.6.0
keyrings.alt                  3.0
language-selector             0.1
launchpadlib                  1.10.6
lazr.restfulclient            0.13.5
lazr.uri                      1.0.3
louis                         3.5.0
lxml                          4.2.1
macaroonbakery                1.1.3
Mako                          1.0.7
MarkupSafe                    1.0
matplotlib                    2.1.1
numpy                         1.13.3
oauth                         1.0.1
oauthlib                      2.0.6
onboard                       1.4.1
PAM                           0.4.2
pandas                        0.22.0
pip                           21.3.1
platformdirs                  2.4.0
protobuf                      3.0.0
pycairo                       1.16.2
pycrypto                      2.6.1
pycups                        1.9.73
PyGObject                     3.26.1
PyICU                         1.9.8
PyJWT                         1.5.3
pymacaroons                   0.13.0
PyNaCl                        1.1.2
pyparsing                     2.2.0
pyRFC3339                     1.0
python-apt                    1.6.6
python-dateutil               2.6.1
python-debian                 0.1.32
pytz                          2018.3
pyxattr                       0.6.0
pyxdg                         0.25
PyYAML                        3.12
requests                      2.18.4
requests-unixsocket           0.1.5
scipy                         0.19.1
SecretStorage                 2.3.1
setuptools                    39.0.1
simplejson                    3.13.2
six                           1.11.0
ssh-import-id                 5.7
system-service                0.3
systemd-python                234
typing_extensions             4.1.1
ubuntu-drivers-common         0.0.0
ubuntu-pro-client             8001
unity-scope-calculator        0.1
unity-scope-chromiumbookmarks 0.1
unity-scope-colourlovers      0.1
unity-scope-devhelp           0.1
unity-scope-firefoxbookmarks  0.1
unity-scope-manpages          0.1
unity-scope-openclipart       0.1
unity-scope-texdoc            0.1
unity-scope-tomboy            0.1
unity-scope-virtualbox        0.1
unity-scope-yelp              0.1
unity-scope-zotero            0.1
urllib3                       1.22
urwid                         2.0.1
virtualenv                    20.17.1
wadllib                       1.3.2
webencodings                  0.5
wheel                         0.30.0
xkit                          0.0.0
youtube_dl                    2018.3.14
zipp                          3.6.0
zope.interface                4.3.2
