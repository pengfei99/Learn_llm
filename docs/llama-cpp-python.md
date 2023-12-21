# LLaMA CPP python

`llama-cpp-python` is the Python bindings for **Llama CPP**, which is an open-source C/C++ implementation of the 
LLaMA language model. It lets you run the model on your own machine, without worrying about the computational 
resources required. It’s a lightweight and efficient implementation of the model, and it can be run on various 
platforms, including CPUs, GPUs, and Apple Silicon.

Python bindings for Llama CPP are a set of Python modules that make it easy to use the Llama CPP library from Python. 
These bindings provide a high-level interface to the library, so you don’t have to worry about the low-level details of C/C++ 😊.


## 1. Setting Up Python Bindings for Llama CPP

The official doc can be found here https://llama-cpp-python.readthedocs.io/en/latest/#installation-with-specific-hardware-acceleration-blas-cuda-metal-etc

```shell
# create a virtual env with python 3.11, then run the below command
pip install llama-cpp-python
```

Depending on your version of llama-cpp-python, follow these guidelines to download the appropriate LLaMA model format:

For llama-cpp-python version `0.1.79 or higher`: You will need to download a LLaMA GGUF model format from 
[Hugging Face](https://huggingface.co/TheBloke/Llama-2-13B-GGUF/tree/main).

 For llama-cpp-python versions `lower than 0.1.79`: You will need to download a LLaMA GGMLV3 model format, which can be 
 obtained from [GPT4All](https://gpt4all.io/index.html) or [Hugging Face](https://huggingface.co/TheBloke/Llama-2-13B-chat-GGML).
 
By default, it will use the cpu to do the calculation, which will take long times.

## 2. Use the High level API

### 2.1 Chat completion

```shell
from llama_cpp import Llama

llm = Llama(model_path="path/to/llama-2/llama-model.gguf", chat_format="llama-2")
llm.create_chat_completion(
      messages = [
          {"role": "system", "content": "You are an assistant who perfectly describes images."},
          {
              "role": "user",
              "content": "Describe this image in detail please."
          }
      ]
)
```

Chat completion is available through the [create_chat_completion](https://llama-cpp-python.readthedocs.io/en/latest/api-reference/#llama_cpp.Llama.create_chat_completion) method of the [Llama class](https://llama-cpp-python.readthedocs.io/en/latest/api-reference/#llama_cpp.Llama).



### 2.2 Function Calling

The high-level API also provides a simple interface for function calling.

Note that the only model that supports full function calling at this time is "functionary". The gguf-converted 
files for this model can be found here: [functionary-7b-v1](https://huggingface.co/abetlen/functionary-7b-v1-GGUF/tree/main).