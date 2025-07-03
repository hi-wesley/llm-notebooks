# LLM recipes
## Overview
This repository contains Jupyter notebooks demonstrating how to interact with and utilize various Large Language Models. It includes both cloud-based and locally hosted models. These examples can help anyone experiment with or build applications with LLMs.
## Repository Contents

### multimodel\_chat.ipynb
* **Multimodel Chat Integration**: Integrates ChatGPT, Gemini, and Claude APIs.
* **State Handling for Gemini**: Maintains a persistent chat session initialized once (`start_chat`). ChatGPT and Claude APIs require explicit conversation history with each request.
* **Conversation History**: Explicitly tracked and updated after each chatbot response.
* **System Prompts Handling**: Explores model-specific content policies by testing prompts with varying tones.

### first\_gradio.ipynb
* **Interactive UI with Gradio**: Uses (`gradio`) for rapid UI development, providing an easy-to-use, interactive web-based interface. Launches with parameters (`share=True, inbrowser=True`), allowing easy sharing and immediate browser opening.
* **Multimodel Chat Integration**: Allows model selection dynamically with a dropdown menu.
* **Error Handling and Logging**: Utilizes Python's built-in (`logging`) module to record errors.

### ai\_pipelines.ipynb
* **Demonstrates two AI pipelines**: Uses Hugging Face libraries and runs on Google Colab
* **Text-to-Speech (Audio Generation)**: Uses the `microsoft/speecht5_tts` model to synthesize realistic speech audio from text prompts.
* **Text-to-Image (Image Generation)**: Employs the `stabilityai/sd-turbo` model to rapidly generate images based on textual descriptions.

### stateful\_gradio.ipynb
* **Stateful chat**: Maintains conversation history for contextual understanding.

### summarize\_webpage.ipynb
* **OpenAI API Integration**: Sends requests and handles responses via the OpenAI API.
* **Web Content Parsing**: Utilizes BeautifulSoup for webpage content extraction.
* **Markdown Summary Generation**: Converts webpage content into markdown-formatted summaries from a provided URL.

### use\_local\_models.ipynb
* **HTTP Requests**: Demonstrates interaction with local Ollama models through HTTP.
* **Ollama Library**: Highlights the Ollama Python library for local model interactions.
* **OpenAI Library**: Configured specifically for interacting locally with Ollama-hosted models.

### use\_different\_models.ipynb
* **OpenAI Integration**: Uses the OpenAI library to initialize models from OpenAI, Gemini, and DeepSeek.
* **Google API**: Separately initializes Gemini via Google’s official API.
* **Anthropic API**: Initializes Claude through Anthropic’s API.

### brochure\_creator.ipynb
* **Webpage Retrieval and Parsing**: Uses Requests and BeautifulSoup to collect and analyze webpage content.
* **Relevant Page Selection**: Leverages the OpenAI API to identify relevant pages from scraped links.
* **Brochure Generation**: Streams generated content into brochure form.

## Setup
### Requirements
* [Git](https://git-scm.com/downloads)
* [Anaconda](https://www.anaconda.com/products/distribution)
* API Keys:
  * [OpenAI API key](https://platform.openai.com/settings/organization/api-keys)
  * [Google API key](https://console.cloud.google.com/apis/credentials)
  * [Anthropic API key](https://console.anthropic.com/settings/keys)
  * [DeepSeek API key](https://platform.deepseek.com/api_keys)
  * [Hugging Face API key](https://huggingface.co/settings/tokens)
### Installation
Clone this repository and set up your environment using the provided configuration file (`environment.yml`):
```bash
git clone https://github.com/hi-wesley/llms.git
cd llms
conda env create -f environment.yml
conda activate llms
```
Scripts that rely on Google Colab run in Google Colab and will not work on Jupyter Notebook
### Configuration
Create a `.env` file at the root of your repository and add your API keys (replace placeholders with actual values):
```bash
OPENAI_API_KEY=your_openai_key
GOOGLE_API_KEY=your_google_key
ANTHROPIC_API_KEY=your_anthropic_key
DEEPSEEK_API_KEY=your_deepseek_key
For Google Colab scripts, import the .ipynb to Google Colab, click the key icon on the left sidebar and create a new entry.
For name put HF_TOKEN and value put your Hugging Face API key, and give it notebook access.
```
## Usage
Launch Jupyter Notebook:
```bash
jupyter notebook
```
Launch Google Colab:
On the top right click change runtime type to Python 3, hardware accelerator to T4 GPU, and connect to 
## License
This repository is provided under the [MIT License](LICENSE).