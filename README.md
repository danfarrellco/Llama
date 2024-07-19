<p align="center">
  <img src="https://github.com/meta-llama/llama-models/blob/main/Llama_Repo.jpeg" width="400"/>
</p>

<p align="center">
        🤗 <a href="https://huggingface.co/meta-Llama"> Models on Hugging Face</a>&nbsp | <a href="https://ai.meta.com/blog/"> Blog</a>&nbsp |  <a href="https://llama.meta.com/">Website</a>&nbsp | <a href="https://llama.meta.com/get-started/">Get Started</a>&nbsp
<br>

---

# Llama Models
Llama is an accessible, open large language model (LLM) designed for developers, researchers, and businesses to build, experiment, and responsibly scale their generative AI ideas. Part of a foundational system, it serves as a bedrock for innovation in the global community. A few key aspects:
1. **Open access**: Easy accessibility to cutting-edge large language models, fostering collaboration and advancements among developers, researchers, and organizations
2. **Broad ecosystem**: Llama models have been downloaded hundreds of millions of times, there are thousands of community projects built on Llama and platform support is broad from cloud providers to startups - the world is building with Llama! 
3. **Trust & safety**: Llama models are part of a comprehensive approach to trust and safety, releasing models and tools that are designed to enable community collaboration and encourage the standardization of the development and usage of trust and safety tools for generative AI 

Our mission is to empower individuals and industry through this opportunity while fostering an environment of discovery and ethical AI advancements. The model weights are licensed for researchers and commercial entities, upholding the principles of openness. 

## Llama Models 

|            **Model**                 | **Launch date**                      | **Model sizes**                      |Context Length| **Tokenizer**                      |  **Acceptable use policy**   |                                         **License**                                            |   **Model Card**   |
| :----------------------------------: | :----------------------------------: | :----------------------------------: | :----------------------------------:|:----------------------------------:| :----------------------------------:| :--------------------------------------------------------------------------------------------: | :----------------------------------: |
|             Llama 2                  |      7/18/2023                                |    7B, 13B, 70B                   |4K               |  Sentencepiece                                  | [Llama2 AUP](https://github.com/meta-llama/llama-models/blob/main/AUP/LLAMA2_USE_POLICY.md) | [Llama 2 CLA](https://github.com/meta-llama/llama-models/blob/main/License/Llama2.txt) | [Link](https://github.com/meta-llama/llama-models/blob/main/Model%20Cards/Llama2.md) |
|             Llama 3                  |      4/18/2023                                |                  8B, 70B             |8K       |    TikToken-based                                | [Llama3 AUP](https://github.com/meta-llama/llama-models/blob/main/AUP/LLAMA3_USE_POLICY.md) |  [Llama 3 CLA](https://github.com/meta-llama/llama-models/blob/main/License/Llama3.txt) | [Link](https://github.com/meta-llama/llama-models/blob/main/Model%20Cards/Llama3.md) |
|             Llama 3.1                |      7/23/2024                                |                 8B, 70B, 405B           |128K  |    TikToken-based                                |[Llama3.1 AUP](https://github.com/meta-llama/llama-models/blob/main/AUP/LLAMA3.1_USE_POLICY.md) |  [Llama 3.1 CLA](https://github.com/meta-llama/llama-models/blob/main/License/Llama3.1.txt) | [Link](https://github.com/meta-llama/llama-models/blob/main/Model%20Cards/Llama3.1.md) |

## Download

To download the model weights and tokenizer, please visit the [Meta Llama website](https://llama.meta.com/llama-downloads/) and accept our License.

Once your request is approved, you will receive a signed URL over email. Then, run the download.sh script, passing the URL provided when prompted to start the download.

Pre-requisites: Ensure you have `wget` and `md5sum` installed. Then run the script: `./download.sh`.

Remember that the links expire after 24 hours and a certain amount of downloads. You can always re-request a link if you start seeing errors such as `403: Forbidden`.

### Access to Hugging Face

We also provide downloads on [Hugging Face](https://huggingface.co/meta-llama), in both transformers and native `llama3` formats. To download the weights from Hugging Face, please follow these steps:

- Visit one of the repos, for example [meta-llama/Meta-Llama-3-8B-Instruct](https://huggingface.co/meta-llama/Meta-Llama-3-8B-Instruct).
- Read and accept the license. Once your request is approved, you'll be granted access to all the Llama 3 models. Note that requests used to take up to one hour to get processed.
- To download the original native weights to use with this repo, click on the "Files and versions" tab and download the contents of the `original` folder. You can also download them from the command line if you `pip install huggingface-hub`:

```bash
huggingface-cli download meta-llama/Meta-Llama-3-8B-Instruct --include "original/*" --local-dir meta-llama/Meta-Llama-3-8B-Instruct
```

- To use with transformers, the following [pipeline](https://huggingface.co/docs/transformers/en/main_classes/pipelines) snippet will download and cache the weights:

  ```python
  import transformers
  import torch

  model_id = "meta-llama/Meta-Llama-3-8B-Instruct"

  pipeline = transformers.pipeline(
    "text-generation",
    model="meta-llama/Meta-Llama-3-8B-Instruct",
    model_kwargs={"torch_dtype": torch.bfloat16},
    device="cuda",
  )
  ```

## Responsible Use

Llama models are a new technology that carries potential risks with use. Testing conducted to date has not — and could not — cover all scenarios.
To help developers address these risks, we have created the [Responsible Use Guide](https://ai.meta.com/static-resource/responsible-use-guide/).

## Issues

Please report any software “bug” or other problems with the models through one of the following means:
- Reporting issues with the model: [https://github.com/meta-llama/llama-models/issues](https://github.com/meta-llama/llama-models/issues)
- Reporting risky content generated by the model: [developers.facebook.com/llama_output_feedback](http://developers.facebook.com/llama_output_feedback)
- Reporting bugs and security concerns: [facebook.com/whitehat/info](http://facebook.com/whitehat/info)


## Questions

For common questions, the FAQ can be found [here](https://llama.meta.com/faq), which will be updated over time as new questions arise.
