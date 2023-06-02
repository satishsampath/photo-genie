# photo-genie
Make new photos from your existing ones

This is a demo of using Dreambooth & Stable Diffusion to generate images using your own photos. The demo runs on Google Colab's free tier, on machines with T4 GPUs (thanks, Google!)

## Sample generated images
<p float="left">
  <img src="/sample-1.png" width="300" />
  <img src="/sample-2.png" width="300" /> 
  <img src="/sample-3.png" width="300" />
</p>

## Usage
1. Open the Google Colab notebook [from here](https://olab.research.google.com/github/satishsampath/photo_genie/blob/main/photo_genie.ipynb) (part of this very repo)
2. Follow instructions at the top of the notebook to prepare your photos
3. Run the Colab step by step, and in the end play around with various prompts to create new images

## How does it work?
1. Detects & extracts face info from all the given photos, using the excellent [Deepface library](https://github.com/serengil/deepface)
2. Generates embedding vector using DeepFace for each face
3. Groups similar faces together using DBSCAN algorithm from the [scikit-learn library](https://github.com/scikit-learn/scikit-learn). This identifies a set of unique people in the photos
4. You select a person/group of photos and Dreambooth is fine-tuned with those photos
5. You play around with various prompts to create new images

Steps 4 & 5 above reuse a lot from ShriramShrirao's [excellent Dreambooth tutorial](https://colab.research.google.com/github/ShivamShrirao/diffusers/blob/main/examples/dreambooth/DreamBooth_Stable_Diffusion.ipynb). Thank you!
