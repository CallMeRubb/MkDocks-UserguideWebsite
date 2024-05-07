# Foocus Installation

## What is Foocus?
Fooocus is an image generating software (based on Gradio).

Fooocus is a rethinking of Stable Diffusion and Midjourney’s designs:

Learned from Stable Diffusion, the software is offline, open source, and free.

Learned from Midjourney, the manual tweaking is not needed, and users only need to focus on the prompts and images.


## Information
Installation guide on how to install Foocus. Keep in mind, that this requires a NVIDIA driver. Installation could take multible GB, so it may take a while.
Here is the link for the github, to the creator of Foocus. You can also find further installation guidance for other platforms aswell.

[Foocus Github Page](https://github.com/lllyasviel/Fooocus)
***
## Setup


<br>Clone the repo.
```shell
git clone https://github.com/lllyasviel/Foocus.git
```
<br>Now activate scripts on your computer. (Needed)
```shell
Set-ExecutionPolicy bypass
```
<br>Create a virtual enviroment for python
```shell
python -m venv foocus_env
```
<br>Enter ***Foocus_env*** file
```shell
cd .\foocus_env\
```
<br>Activate a script, inside of Scripts.
```shell
Scripts/activate
```
<br>Go back to previous cd, by doing this. Previous cd is going to be ***Foocus-Main***.
```shell
cd ..
```
<br>And then install the packages. 
```shell
pip install -r requirements_versions.txt
```
<br>When that is done. Run this python script. This will automatically download the defult models in the backgroud. These files are multible GB large, so it may take a while.
```shell
python entry_with_update.py
```
<br>Installation should start. And when its finished. You can go ahead and create your own images.

