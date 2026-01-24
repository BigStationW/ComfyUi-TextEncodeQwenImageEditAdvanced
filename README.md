# ComfyUi-TextEncodeEditAdvanced

## Intro

This is a text encoding node designed for Edit models (Flux Kontext, Qwen Image Edit, Flux 2 Klein...).

Key features:
- Adjustable Vision Language Model (VLM) resolution via `vl_megapixels`
- Control over the number of images processed via `max_images_allowed`
- Support for up to 3 input images

<img width="500" alt="image" src="https://github.com/user-attachments/assets/919b7ed1-8223-4f05-8905-cba137dcaf13" />

## vl_megapixels

**This parameter is only relevant for Qwen Image Edit (for other Edit models you must set this value to 0).**

Qwen Image Edit uses a Vision Language Model (VLM) to analyze your input images and automatically enhance your prompt with more detailed descriptions.

The default TextEncodeQwenImageEdit node downscales your images to 0.15 megapixels before feeding them to the VLM.

This gives you control over that value, allowing you to eventually find a better sweet spot for your specific use case.

By adjusting this threshold, you may achieve:

- Better style preservation
- Reduced zoom effect: Mitigate the tendency for Qwen Image Edit to zoom in on images

https://github.com/user-attachments/assets/23dca6a6-6add-44b5-8777-9c206ea66f9f

## max_images_allowed
Controls the maximum number of images to process from the available inputs (image1, image2, image3).

**For example**: If you have 3 images connected to the node, setting this to "1" will only process image1.

## Installation

Navigate to the **ComfyUI/custom_nodes** folder, [open cmd](https://www.youtube.com/watch?v=bgSSJQolR0E&t=47s) and run:

```bash
git clone https://github.com/BigStationW/ComfyUi-TextEncodeEditAdvanced
```

Restart ComfyUI after installation.

## Usage
Find the **TextEncodeEditAdvanced** node.

I also provide [worksflows](https://github.com/BigStationW/ComfyUi-TextEncodeEditAdvanced/tree/main/workflow) for those interested.


## Conditioning Add Image Reference

A variant of ```TextEncodeEditAdvanced``` that let's you use ```CLIP Text Encode (Prompt)``` [(Or something else)](https://github.com/asagi4/comfyui-prompt-control)

<img width="500" alt="image" src="https://github.com/user-attachments/assets/baad54c8-8a6d-4efe-b783-8c627687f655" />

A workflow using this node for [Flux 2 Klein](https://github.com/BigStationW/ComfyUi-TextEncodeEditAdvanced/blob/main/workflow/workflow_Flux2_Klein_9b_clip_text_encode.json) is provided.
