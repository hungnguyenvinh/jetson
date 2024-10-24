# Detect 6 facial emotions: anger, disgust, fear, happy, pain and sad

Project based on image classification

## Device

[JETSON-IO-BASE-A - Custom model from Waveshare](https://www.waveshare.com/jetson-nano-dev-kit-a.htm)

OS Ubuntu 18.04.6

Jetpack 4.6.1 (L4T R32.6.1)

[Flashed following this wiki page](https://www.waveshare.com/wiki/JETSON-NANO-DEV-KIT)

## Dependencies

- [Pytorch 1.10 - torchvision 0.11.1](https://forums.developer.nvidia.com/t/pytorch-for-jetson/72048)
- [jetcam](https://github.com/NVIDIA-AI-IOT/jetcam)
- [Jetson.GPIO - Linux for Tegra](https://github.com/NVIDIA/jetson-gpio)
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
