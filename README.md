# Image Generation from Customer Reviews 

This project leverages **prompt engineering** and **Retrieval-Augmented Generation (RAG)** to summarize product descriptions and customer reviews. The refined prompts are then used with diffusion models (Stable Diffusion & DALL-E) to generate product images, which can be compared against actual product images.

## Project Overview

The entire end-to-end process is contained within a single, executable Jupyter Notebook: `Agentic_Product_Image_Generator.ipynb`.

1.  **Agentic Prompt Engineering:** Uses OpenAI's GPT models (e.g., GPT-3.5-turbo) to process raw product descriptions and customer reviews, extracting key features and positive sentiment.
2.  **Multimodal Generation:** The refined prompt is simultaneously fed into two different image generation systems for comparison:
    * **Stable Diffusion 2.1 Base** (via Hugging Face Diffusers)
    * **DALL-E 3** (via OpenAI API)
3.  **RAG Capability:** The Agent is structured to optionally incorporate a Retrieval-Augmented Generation (RAG) system (using Pinecone/LlamaIndex) to fetch information from large, unstructured review documents (like PDFs), ensuring the generated prompt is comprehensive.

## 🚀 Generated Image Demo

Here is a side-by-side comparison of the images generated from the same customer-review-driven prompt, demonstrating the different styles of Stable Diffusion and DALL-E 3.

| Stable Diffusion 2.1 | DALL-E 3 |
| :---: | :---: |
| <image src="images/mesh chair_dalle_1.png"> | <image src="images/mesh chair_sd_1.png"> |

## 🛠️ Key Technologies

* **Image Generation**: Stable Diffusion 2.1 (Diffusers), DALL-E 3 (OpenAI)
* **Prompt Engineering**: OpenAI GPT-3.5-Turbo
* **Vector Database (Optional RAG)**: Pinecone, LlamaIndex
* **Frameworks**: PyTorch, Diffusers, Hugging Face Hub

## 💻 Getting Started

### 1. Clone the Repository

```bash
git clone <your-repository-url>
cd IMAGE-GEN-FROM-REVIEWS
```

### 2. Set Up Environment

It is recommended to use a virtual environment.

```bash
python -m venv venv
source venv/bin/activate
```

Install the required packages using pip:

```bash
pip install -r requirements.txt
```

### 3. Configure API Keys

Create a `.env` file in the root directory of the project and add your API keys:

```
OPENAI_API_KEY="your_openai_api_key"
PINECONE_API_KEY="your_pinecone_api_key"
HF_KEY="your_huggingface_api_key"
```

### 4. Run the Project

1.  Open the `Agentic_Product_Image_Generator.ipynb` file in Google Colab (recommended for GPU access) or VS Code.
2.  Select a GPU Runtime (e.g., T4, L4, or A100 in Colab).
3.  Run all cells sequentially. The Agent will:
    - Initialize LLMs and Diffusion Models.

    - Generate a descriptive prompt from the embedded product data.

    - Call both Stable Diffusion and DALL-E 3 to generate and save the final images.
