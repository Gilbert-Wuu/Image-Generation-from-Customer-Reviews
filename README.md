# Image Generation from Customer Reviews 

This project leverages **prompt engineering** and **Retrieval-Augmented Generation (RAG)** to summarize product descriptions and customer reviews. The refined prompts are then used with diffusion models (Stable Diffusion & DALL-E) to generate product images, which can be compared against actual product images.

## Project Overview

The workflow is divided into two main parts:

1.  **Prompt Generation (`RAGandPromptGenerationCode.ipynb`)**: This notebook processes a PDF of product reviews, chunks the text, and uses a RAG pipeline with OpenAI's GPT-4 and Pinecone as the vector database to generate concise, descriptive prompts.
2.  **Image Generation (`Image_Generation_from_Prompt.ipynb`)**: The generated prompts are fed into Stable Diffusion and DALL-E to create realistic product images from the summarized text.

## 🚀 Getting Started

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

### 4. Run the Notebooks in VS Code

1.  Open the `IMAGE GEN FROM REVIEWS` folder in Visual Studio Code.
2.  Make sure you select the Python interpreter from your virtual environment (`venv`).
3.  Open `RAGandPromptGenerationCode.ipynb` and run the cells sequentially to process the data and generate prompts.
4.  Open `Image_Generation_from_Prompt.ipynb` and run the cells to generate images based on the prompts. Generated images will be saved in the `output/` directory.

## 🛠️ Key Technologies

* **Language Models**: OpenAI GPT-4, DALL-E 3
* **Image Generation**: Stable Diffusion
* **Vector Database**: Pinecone
* **Frameworks**: LangChain, LlamaIndex, PyTorch, Diffusers
