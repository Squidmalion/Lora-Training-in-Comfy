
# TO DO
Remove Tensorboard stuff for now.
Remove hard-codings.
Implement logging.
Implement stand-alone launcher.

# MY NOTES
The project was completely defective upon discovery on 12/30/25.
No output including log files; zero accountability of any kind regarding the failure.
Software that CAN produce zero output is defective by nature and uncacceptable for publication, even for free. 
The world does not need more free garbage.

*** LEAD, FOLLOW, OR GET OUT OF THE WAY!!! ****

# ORIGINAL NOTES:

I'll link my tutorial. Download it from here, then follow the guide:

https://www.reddit.com/r/StableDiffusion/comments/193hqkz/lora_training_directly_in_comfyui/

In short, you have to put it in custom_nodes and install the requirements (from requirements_win.txt if you're on Windows). Pretty standard for custom nodes!
![LoRATrainingNode](https://github.com/LarryJane491/Lora-Training-in-Comfy/assets/156431112/ff9453a7-498e-4e26-a2b9-003f9667cbb2)

After installing, you can find it in the LJRE/LORA category or by double-clicking and searching for Training or LoRA.
Make sure you have a folder containing multiple images with captions.
Then, rename that folder into something like [number]_[whatever].
Copy the path of the folder ABOVE the one containing images and paste it in data_path. For example, if it's in C:/database/5_images, data_path MUST be C:/database.
Finally, just choose a name for the LoRA, and change the other values if you want. Then just click Queue Prompt and training starts!

Original author had a bunch of crap related to auto-captioning that is not appropriate for professional use (which should always be hand-captioned).

This node is confirmed to work for SD 1.5, SD2.0, SDTurbo and LCM.
But I have no idea about SDXL. If someone could test it and confirm or infirm, I’d appreciate ^^. I know the LoRA project included custom scripts for SDXL, so maybe it’s more complicated.

----

TROUBLESHOOT:
The very first version I published online had very strict requirements, which made conflicts likely. I've reduced requirements to the bare minimum, but conflicts can still arise. If that happens to you, please let me know!

"No module X found" : This error happens when Python can't find the required modules for the running program. For ComfyUI, it often happens if you forgot to install requirements for the custom node.
But it can also happen if you installed the requirements in the wrong folder! If your ComfyUI folder has a virtual environment (venv), make sure to enable it before installing requirements.

"Something about cuda.dll missing" : there's a lot of variants of this error, but they're all the same problem (hopefully): it happens if you haven't installed CUDA properly (or, again, if it's not installed in the right folder). Here is what to do in this case:
1) Open a command prompt and make absolutely sure that it's the right environment.
2) Go there: https://pytorch.org and scroll down. Follow the instructions to get a line of code, something like pip3 install torch torchvision torchaudio --index-url https://download.pytorch.org/whl/cu121. Copy-paste the line the website gives you into the command prompt you opened and press Enter. This will install CUDA.

----

TO GO FURTHER
Even the Advanced node doens't include all inputs available for LoRA training, but you can find them all in the script train.py! All of that can be modified by the user directly within the script.

----

This is based off an existing project, lora-scripts, available on github. 

