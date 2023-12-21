# LLaMA CPP python

`llama-cpp-python` is the Python bindings for **Llama CPP**, which is an open-source C/C++ implementation of the 
LLaMA language model. It lets you run the model on your own machine, without worrying about the computational 
resources required. It’s a lightweight and efficient implementation of the model, and it can be run on various 
platforms, including CPUs, GPUs, and Apple Silicon.

Python bindings for Llama CPP are a set of Python modules that make it easy to use the Llama CPP library from Python. 
These bindings provide a high-level interface to the library, so you don’t have to worry about the low-level details of C/C++ 😊.


## 1. Setting Up Python Bindings for Llama CPP

```shell
# create a virtual env with python 3.11, then run the below command
pip install llama-cpp-python
```

Depending on your version of llama-cpp-python, follow these guidelines to download the appropriate LLaMA model format:

For llama-cpp-python version `0.1.79 or higher`: You will need to download a LLaMA GGUF model format from 
[Hugging Face](https://huggingface.co/TheBloke/Llama-2-13B-GGUF/tree/main).

 For llama-cpp-python versions `lower than 0.1.79`: You will need to download a LLaMA GGMLV3 model format, which can be 
 obtained from [GPT4All](https://gpt4all.io/index.html) or [Hugging Face](https://huggingface.co/TheBloke/Llama-2-13B-chat-GGML).