# Historical Image Generator

### LLM-guided prompt enrichment for diffusion-based image generation

An AI image-generation project that combines a large language model with a diffusion model to create historically and geographically informed images from natural-language prompts.

The pipeline uses **Mistral-7B-Instruct** to enrich a user's initial description before passing the expanded prompt to **DreamShaper-8** for image synthesis.

## Project overview

The project explores whether adding contextual information before image generation can produce richer and more historically grounded visual prompts.

The workflow separates language reasoning from image synthesis:

1. the user provides a short image request;
2. Mistral-7B-Instruct expands the request with additional context;
3. the enriched prompt is passed to DreamShaper-8;
4. the diffusion model generates the final image;
5. a Gradio interface exposes the pipeline interactively.

## What I implemented

- loading and using an instruction-tuned language model
- prompt-enrichment logic for historical and geographical context
- integration between a language model and a diffusion model
- baseline image generation from the original prompt
- image generation from LLM-enhanced prompts
- comparison of direct and enriched prompting
- diffusion-generation configuration
- Gradio interface for interactive image generation

## Pipeline

    User prompt
        ↓
    Mistral-7B-Instruct
        ↓
    Context-enriched prompt
        ↓
    DreamShaper-8
        ↓
    Generated image

## Prompt enrichment

The language-model stage expands short prompts into more descriptive instructions.

This provides the image-generation model with additional contextual detail instead of relying only on the original user input.

## Image generation

The enriched prompt is passed to DreamShaper-8 using the Hugging Face diffusion ecosystem.

The project therefore combines two pretrained generative systems with different roles:

- an LLM for language understanding and prompt enrichment
- a diffusion model for visual generation

## Interactive interface

A Gradio interface wraps the generation pipeline so prompts can be entered and images generated without directly interacting with the notebook code.

## Repository structure

    historical-image-generator/
    ├── historical_image_generator.ipynb
    ├── requirements.txt
    ├── .gitignore
    └── README.md

## Tech

**Python · PyTorch · Hugging Face Transformers · Hugging Face Diffusers · Mistral-7B-Instruct · DreamShaper-8 · Gradio · generative AI · large language models · diffusion models · prompt engineering · text-to-image generation**
