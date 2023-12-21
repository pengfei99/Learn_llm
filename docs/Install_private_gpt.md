# PrivateGPT

PrivateGPT provides an API containing all the building blocks  required to build private, context-aware AI 
applications. The API follows and extends OpenAI API standard, and supports both normal and streaming responses. 
That means that, if you can use OpenAI API in one of your tools, you can use your own PrivateGPT API instead, with 
no code changes, and for free if you are `running privateGPT in local mode`.


## Installation

You can find the official doc [here](https://docs.privategpt.dev/installation)

### Prerequisite

You need to have the below prerequisite before you start the installation process

- A python env with python 3.11 or later (pyenv+virtualenv is recommended).
- Install poetry
- Have a valid C++ compiler like **gcc**. See Troubleshooting: C++ Compiler for more details.
- Install **make**. (In debian, you can use `sudo apt show make` to check the current installed version)

### App installation

```shell
# get the source of privateGPT
git clone https://github.com/imartinez/privateGPT
cd privateGPT

# install the dependencies for the front
poetry install --with ui

# Install extra dependencies for local execution
poetry install --with local
```

With the above command we only have the binary and dependencies of the private gpt. 

### App Configuration

For PrivateGPT to run locally, we need to download llm models and run them by ourselves. PrivateGPT uses `llama-cpp-python`
(llama.cpp python wrapper) to run local models. So the downloaded models must be compatible with the llama.cpp.

These two models are known to work well:

https://huggingface.co/TheBloke/Llama-2-7B-chat-GGUF
https://huggingface.co/TheBloke/Mistral-7B-Instruct-v0.1-GGUF (recommended)

#### Quick start

To ease the installation process, we can use the setup script which is provided by the privateGPT. It will download
both the embedding and the LLM model and place them in the correct location (under models folder):

```shell
poetry run python scripts/setup
```