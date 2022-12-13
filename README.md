# TextToImage_StableDiffusionV2
This is a simple project which can convert the user text to artwork using Stable diffusionV2 
#Convert CoreML models
Convert the PyTorch SD2 model to CoreML models, following Apple's instructions. (https://github.com/apple/ml-stable-diffusion)

# create a Python environment and install dependencies
% conda create -n coremlsd2_38 python=3.8 -y
% conda activate coremlsd2_38
% cd SD2ModelConvChunked
% git clone https://github.com/apple/ml-stable-diffusion
% cd ml-stable-diffusion
pip install -e .
Visit the Hugging Face Hub - stabilityai/stable-diffusion-2 model's page. （https://huggingface.co/stabilityai/stable-diffusion-2） Check the Terms and Use and accept it. Then you can use the model.

And you need a Hugging Face's User Access Token, to download huggingface/models. Please visit Hugging Face's site and make an access token at Account Settings.

# cli login
% huggingface-cli login
Token:    # <- input your Access Token

How to add Core ML model files to Xcode project:

In Finder, make the directory, CoreMLModels, and put CoreML model files into the directory.
merges.txt, vacab.json, UnetChunk2.mlmodelc, UnetChunk1.mlmodelc, VAEDecoder.mlmodelc, TextEncoder.mlmodelc
when you make an app for only Mac, use the Unet.mlmodelc instead of UnetChunk1/2, which are for mobile devices.
Remove the CoreMLModels group in the Xcode Project Navigator.
Drag and drop the CoreMLModels directory in Finder into the Xcode Project Navigator, to add the files.
At Choose options for adding these files dialog, check the [v] Copy items if needed and [v] Create folder references, and Add to targets: TextToImageSD2
