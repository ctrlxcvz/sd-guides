<h2> KRITA + STABLE DIFFUSION PC INSTALLATION GUIDE <br> 
FOR WINDOWS 11 & NVIDIA GPUs </h2> 

### This guide is for local installation exclusively on your own machine currently.

**Difficulty: Easy - Intermediate - [Advanced]**

- There is a Google Colab method that might be added later.
- I recommend trying that on your own for now as that is an easier, albeit more limiting, method due to Colabs limitations.
 
**Optional Pre-Req - BUT makes things a lot easier later:**
- You can skip this step entirely and manually download the required zip file later if you prefer <sup>[1](https://github.com/ctrlxcvz/sd-guides/blob/main/krita-sd-local.md#-do-the-following-step-only-if-you-didnt-install-github-desktop-and-webui-folder-earlier-)</sup>
- I recommend creating a GitHub account, star the repository below (or at least bookmark it in your browser), and install GitHub Desktop:
```
https://github.com/imperator-maximus/stable-diffusion-webui
```
- Install GitHub Desktop:
``` 
https://desktop.github.com/
```
- Go here:
```
https://github.com/imperator-maximus/stable-diffusion-webui
```
- Click "CODE" > "OPEN WITH GITHUB DESKTOP"
- GitHub Desktop default directory should be Documents > GitHub on your PC where it downloaded the folder "stable-diffusion-webui".
- Make note of this directory for later.
 
#### TECHNICAL REQUIREMENTS:
- !! PC/WINDOWS WITH NVIDIA GRAPHICS CARD ONLY !! REQUIRES A LOT OF VRAM FOR LOCAL INSTALLATION !!
- You need Python, Git, MS Visual Studio, and CUDA for Nvidia GPU all installed 
- Make sure Windows and all of your Nvidia Drivers are up to date before starting
 
<details>
<summary>
  <h1>
Guide Overview
  </h1>
</summary>

1. Installing Python
2. (Optional) Install Notepad++
3. Install Git
4. Install Microsoft Visual Studio Community 2022
5. Install Windows Nvidia CUDA Toolkit
6. Preparing Stable Diffusion Components
7. Download/Install Krita & Plugin
8. Krita + SD setup
9. Getting Started Running SD in Krita
10. Acknowledgements
</details>
<br>
 

**Install Python:**
```
https://www.python.org/downloads/windows/
```
- I suggest selecting "COPY PATH" check mark box during installation. 
 
**(Optional) Install Notepad++ Editor:**
```
https://notepad-plus-plus.org/downloads/
```
- Primarily used as an optional editor you can select during the Git installation in the step below.
- Notepad++ is usually recommended over the default (Vim) - but we won't actively be using it.
- You can edit .bat (& many more) files with Notepad++ - so it's good to have installed if you ever need to modify those files. 
- If skipped, select Vim during Git install and proceed.
 
**Install Git:**
```
https://git-scm.com/download/win
```
- Git Installation Guide: 
```
https://victorkarp.com/git-tutorial-for-beginners-how-to-install-git-on-windows/
```
 
**Install Microsoft Visual Studio:**
```
https://visualstudio.microsoft.com/
```
- Select Download Visual Studio > Community 2022
- Click on VisualStudioSetup.exe file you downloaded > Select "Desktop & Mobile" in launcher > select "Desktop Development with C++" > Select "Install while Downloading" > and wait for it to finish. Once completed, you can close any instance of Visual Studio.
- This is required for CUDA components to run correctly - check your Nvidia GPU card documentation for more information.
- The primary objective is to get MSVC installed for the CUDA components. This accomplishes that goal. 
 
**Install Windows Nvidia CUDA Toolkit:**
```
https://developer.nvidia.com/cuda-downloads?target_os=Windows&target_arch=x86_64
```
- Information on CUDA installation can be found here: 
```
https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html
```

**Download the Stable Diffusion neural network weights here:**
```
https://huggingface.co/CompVis/stable-diffusion-v-1-4-original
```
- The Stable Diffusion model checkpoint file is roughly ~4GB in size. 
- Once downloaded - rename the file from "stable-diffusion-v-1-4-original.ckpt" to "model.ckpt"
- Leave this file in your "Downloads" folder for now.
 
**(Optional - but recommended)**
- You can use GPFGAN to improve faces, then you'll need to download the model from here:
``` 
https://github.com/TencentARC/GFPGAN/releases/download/v1.3.0/GFPGANv1.3.pth
```
- Leave this file in your "Downloads" folder for now.

### !! DO THE FOLLOWING STEP ONLY IF YOU DIDN'T INSTALL GITHUB DESKTOP AND WEBUI FOLDER EARLIER !!
- You can skip this step if you did the GitHub Desktop Pre-Req above<sup>[1](https://github.com/ctrlxcvz/sd-guides/blob/main/krita-sd-local.md#this-guide-is-for-local-installation-exclusively-on-your-own-machine-currently)</sup>
- Download the Krita Stable Diffusion WebUI Local Interface here:
```
https://codeload.github.com/imperator-maximus/stable-diffusion-webui/zip/refs/heads/master
```
- Extract the "stable-diffusion-webui" folder from the downloaded zip file into a directory of your choice.
- Make note of this directory.

**Move the "model.ckpt" and the "GFPGANV1.3.pth" files to the "stable-diffusion-webui" directory**
- If you installed from GitHub Desktop at the beginning, that folder should be in Documents > GitHub > stable-diffusion-webui.
- If you downloaded the zip file, it's where you extracted the folder to.
 
**Download Krita here:**
```
https://krita.org/en/download/krita-desktop/
```
- Select your version > typically Windows Installer 64-Bit > download and install it.
- Launch Krita after installation, minimize it if needed.
 
**Download and Install Krita Stable Diffusion Plugin here:**
```
https://www.flyingdog.de/sd/en/sd_plugin_krita_beta5.zip
```
- Go back to the running instance of Krita.
- Select Tools > Scripts > Import Python Plugin from File > and select the "sd_plugin_krita_beta5.zip" file you just downloaded.
- This will require Krita to restart, so once the plugin is installed, close Krita and relaunch it.
- The "Stable Diffusion" panel should be loaded in the bottom right window with the options "From Text", "From Image", and "Inpaint".
- Once you have confirmed the plugin installed correctly, you can minimize Krita.
 
**Open the "stable-diffusion-webui" folder you downloaded earlier**
- Click on the "api.bat" file; a windows Command Prompt should launch a local instance of Stable Diffusion on your machine.
- ! If it fails the first time, click on it again to run it.
- ! If it seems to be hanging on any part for long periods I.E. "Installing Requirements for Web UI", select the Command Prompt window and hit "Enter" (or any key) to get it going again. If it continues to hang, try hitting a key again.
- If everything is successful, you should see in the Command Prompt window output at the end:
```
> Global Step: 470000
> Model loaded.
> Running on local URL:
http://127.0.0.1:[XXXX]
```
- Where X = 4 digit number of your local SD instance.
- Note down the "127.0.0.1:[XXXX]" URL output somewhere.
- !! LEAVE THIS COMMAND PROMPT WINDOW RUNNING TILL YOU ARE FINISHED !!
- !! CLICK API.BAT TO RUN YOUR LOCAL SD FROM HERE ON EVERY TIME YOU WANT TO RUN KRITA + SD PLUGIN !! 
 
**PUTTING IT ALL TOGETHER AND RUNNING IT**
- Minimize the CMD Prompt window or move it aside.
- Open Krita again > on the "Stable Diffusion" plugin window > click on the Square Icon on the bottom left.
- A configuration window should appear and under the "Webservice URL" box enter the URL you noted down earlier.
- Leave all settings as is and click "OK".
 
**FINISHING UP: GETTING STARTED IN KRITA**
- Click "New File" on the Krita main page under "Start" OR hit Ctrl + N OR select File > New
- Create a new document of any size - 512px X 512px or 1024px X 1024px @ 150-300 Resolution is usually a good place to start.
- Select the "Rectangular Selection Tool" in the tool panel on the left - or hit Ctrl + R
- Using this tool - draw a box selecting your entire canvas, or size you want the image to be.
- Select "From Text" in the "Stable Diffusion" plugin window.
- Enter whatever prompt you want to see + modifier words describing the style and detail.
```
Prompt: An astronaut riding a horse on mars. 
Modifiers: Oil on canvas, detailed, van gough.
```
- For more prompt engineering tips and ideas: https://beta.dreamstudio.ai/prompt-guide
- Click "OK" and VOILA! you should see it processing in the "api.bat" CMD Prompt window you left open earlier.
- You can experiment with "Steps", "Guidance", and "Sampling Method" for different results.
- Steps: Higher = Slower but often better quality.
- Number Images = How many images you want generated per instance - maximum of 4.
- Advanced - Seed (empty=random) = Random images are generated each time when left blank.
- Guidance Scale = How strongly the image should follow the prompt.
- Sampling Method = Various diffusion and sampling methods using the Stable Diffusion model.
 
!!!! CONGRATULATIONS !!!! YOU DID IT !!!!
- HAVE FUN AND EXPERIMENT
- There are plenty of settings to experiment with; there is no wrong method.
- "From Image" = img2img processing where it combines an image + text prompt to generate a new image.
- You can experiment with how much the image or text influences the overall output by tinkering with settings.
- "Inpaint" = Allows you to generate a prompt within an image where there are empty pixels. <br>
I.E. - You can input an image of a landscape, erase a part of the sky, select it w/ Ctrl + R, "Inpaint", and input the text prompt "UFO flying in the sky" and it should give you a selection of outputs to realistically place in that spot.
 
**==== ACKNOWLEDGMENTS ====** <br>

This guide was assembled from the following websites:
- https://www.flyingdog.de/sd/en/
- https://github.com/imperator-maximus
- https://victorkarp.com/git-tutorial-for-beginners-how-to-install-git-on-windows/
- https://docs.nvidia.com/cuda/cuda-installation-guide-microsoft-windows/index.html
- https://beta.dreamstudio.ai/prompt-guide
 
**==== DONATIONS SO I CAN KEEP ON TINKERING IF YOU FOUND THIS USEFUL ====** <br>
- ETH: ctrlxcvz.eth
- BTC: bc1qxdr9869dh42vtuctn5a4s3f68secyzal4e7gnn
- SOL: 4CeqibD5LqpPb5XgC9TdxfA2NMUBntnUTRFTEWzvBzVo
- XMR: 88hWjDuptnBerfkoTTAUhJ4AFuiMnMPSVVQhAbiV2rSEV7Gj2FaytRv1bnL8gPmL6U4L4XhFVBc4KbQLDmDM9hEaC4S1FV5 <br>

**==== EVERY BIT HELPS - THANKS FOR READING ====**
