# Textual Inversion Misicka Concept

Repo serves to save my try to create my wife own concept for [Stable diffuser](https://huggingface.co/CompVis/stable-diffusion-v1-4) (textual inversion) following [hugging face](https://huggingface.co/docs/diffusers/training/text_inversion).

## What is Textual Inversion?

> Is a technique for capturing novel concepts from a small number of example images in a way that can later be used to control text-to-image pipelines. It does so by learning new ‘words’ in the embedding space of the pipeline’s text encoder. These special words can then be used within text prompts to achieve very fine-grained control of the resulting images.

I was highly inspirated by [fast.ai](https://www.fast.ai/) presentations where I found nice [youtube video](https://www.youtube.com/watch?v=0_BBRNYInx8) about learning concepts. What engaged me to create my own ones. To getting all done I have used [colab notebook](https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/sd_textual_inversion_training.ipynb)

## How to use it?

  1. Use [inference notebook](https://colab.research.google.com/github/huggingface/notebooks/blob/main/diffusers/stable_conceptualizer_inference.ipynb) from hugging face.

2. Download the learned_embeds.bin file from there and upload the file to wherever this notebook is before running this next cell:

  ```pyhton
  learned_embed = torch.load('data/sd_styles/<learned_embeds.bin>') 
  learned_embed.keys()
  ```
  TODO: add sample script

## first training for `CompVis/stable-diffusion-v1-4`

I used 9 figures from past to train own token.

```python
# placeholder_token is the token you are going to use to represent your new concept (so when you prompt the model, you will say "A `<my-placeholder-token>` in an amusement park"). We use angle brackets to differentiate a token from other words/tokens, to avoid collision.
placeholder_token = "\u003Ckat>"
# initializer_token is a word that can summarise what your new concept is, to be used as a starting point
initializer_token = "kat"
```

