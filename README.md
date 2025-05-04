# fine-tuning-LLM-with-DPO-and-LoRA

## Objective

The aim of this notebook is to use Direct Preference Optimization (DPO) and Low-Rank Adaptation (LoRA) to fine tune a LLM. We use the 'trl' library and the "ultrafeedback_binarized" dataset from Hugging Face to fine tune the model. The dataset uses a completion criteria based on helpfulness and honesty. Therefore, the aim of the fine-tune is to get more 'helpful and honest' responses from the LLM.

##About the data

We use the "ultrafeedback_binarized" data set on Hugging Face, which is a collection of prompts and responses. See https://huggingface.co/datasets/HuggingFaceH4/ultrafeedback_binarized, for details.

Dataset description:\
This is a pre-processed version of the UltraFeedback dataset and was used to train Zephyr-7Β-β, a state of the art chat model at the 7B parameter scale. \
The original UltraFeedback dataset consists of 64k prompts, where each prompt is accompanied with four model completions from a wide variety of open and proprietary models.**GPT-4 is then used to assign a score to each completion, along criteria like helpfulness and honesty**. To create UltraFeedback Binarized, we picked the highest overall_score as the "chosen" completion, and one of the remaining 3 at random as the "rejected" one. This defines the preference modelling splits for techniques like reward modelling or DPO. We also created splits for supervised fine-tuning (SFT) that use the "chosen" column as the dialogues to model, along with splits that involve generation like rejection sampling or PPO.

Code included in the jupyter notebook.
