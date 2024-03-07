# Local Text-to-Image Generation using older Nvidia GPU and Gradio Interface

## Description
This project demonstrates the setup of a GPU-accelerated text-to-image generator. 
It includes a Gradio interface for user control, a locally stored text-to-image diffusion model, and the option to install the Gradio interface offline. 
The entire text-to-image generator operates efficiently on a local setup, utilizing a local GPU, locally stored model, and local interface.

## Setup Instructions
1. **Create a Project Folder**
   - On your system, create a separate folder for the project.

2. **Load the Safetensors Model File**
   - Download the safetensor model file from [here](https://huggingface.co/dreamlike-art/dreamlike-diffusion-1.0/blob/main/dreamlike-diffusion-1.0.safetensors)
   - Move the file into the project folder along with the Jupyter notebook file.

3. **Anaconda Navigator**
   - Environments: Create a new environment, providing a name and selecting the Python package.
   - Home: Install JupyterLab and launch it.

4. **JupyterLab**
   - Navigate to the project folder.
   - Open the Jupyter notebook file and follow the remaining steps.
   - In the notebook, verify that you are working in the newly created environment:
     ```python
     `!conda env list`.

5. **Connecting CUDA**
   - In Anaconda Navigator, go to the Terminal of the current environment and enter:

     `conda install pytorch torchvision pytorch-cuda -c pytorch -c nvidia`.

6. **Verifying CUDA-enabled GPU**
   - Check if CUDA is available:
     ```python
     `import torch`
     `torch.cuda.is_available()`.

7. **Install Necessary Packages**
   - Use the Terminal of the Anaconda environment for installation:
     
     `conda install conda-forge::gradio`
     
     `conda install diffusers`
     
     `conda install transformers`
     
     `pip install omegaconf`

8. **Import Libraries and Modules**
   ```python
   import gradio as gr
   from diffusers import StableDiffusionPipeline
   from diffusers.schedulers.scheduling_dpmsolver_multistep import DPMSolverMultistepScheduler
   import safetensors

9. **Run the Code for Image Generation**
    - The code calls a function to generate images based on provided parameters like prompt, dimensions, seed, and inference steps.
    - The code creates an interface using Gradio to generate images based on user inputs.
