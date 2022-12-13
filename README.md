# __TextToImage_StableDiffusionV2__
This is a simple project which can convert the user prompt text to artwork using Stable diffusionV2 <br>
# __Convert CoreML models__
Convert the PyTorch SD2 model to CoreML models, following Apple's instructions. (https://github.com/apple/ml-stable-diffusion)

<html>
<body>
<p>
 %create a Python environment and install dependencies <br>
% conda create -n coremlsd2_38 python=3.8 -y <br>
% conda activate coremlsd2_38 <br>
% cd SD2ModelConvChunked <br>
% git clone https://github.com/apple/ml-stable-diffusion <br>
% cd ml-stable-diffusion <br>
pip install -e . <br>
</body>
</html>
<br>
<p>
Visit the Hugging Face Hub - stabilityai/stable-diffusion-2 model's page. （https://huggingface.co/stabilityai/stable-diffusion-2） Check the Terms and Use and accept it. Then you can use the model.

And you need a Hugging Face's User Access Token, to download huggingface/models. Please visit Hugging Face's site and make an access token at Account Settings.
</p>

# __cli login__
% huggingface-cli login <br>
Token:    # <- input your Access Token

# __How to add Core ML model files to Xcode project:__ 

In Finder, make the directory, CoreMLModels, and put CoreML model files into the directory. <br>
'merges.txt', 'vacab.json', 'UnetChunk2.mlmodelc', 'UnetChunk1.mlmodelc', 'VAEDecoder.mlmodelc', 'TextEncoder.mlmodelc' <br>
when you make an app for only Mac, use the Unet.mlmodelc instead of UnetChunk1/2, which are for mobile devices. <br>
Remove the CoreMLModels group in the Xcode Project Navigator. <br>
Drag and drop the CoreMLModels directory in Finder into the Xcode Project Navigator, to add the files. <br>
At Choose options for adding these files dialog, check the [v] Copy items if needed and [v] Create folder references, and Add to targets: TextToImageSD2 <br>
