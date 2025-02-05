# DeepSeek-R1 on Amazon Bedrock

This repository will guide you through the process of importing and using the distilled **DeepSeek-R1-Distill-Llama-8B** model based on **Llama-3.1-8B** as the base model from [Hugging Face](https://huggingface.co/deepseek-ai/DeepSeek-R1) on [Amazon Bedrock](https://docs.aws.amazon.com/bedrock/latest/userguide/what-is-bedrock.html). 

To learn more about DeepSeek-R1, please visit [DeepSeek](https://www.deepseek.com).

For detailed paper walkthrough on DeepSeek-R1: Incentivizing Reasoning Capability in LLMs via Reinforcement Learning, check out this paper read on DeepSeek-R1 by [Umar Jamil](https://www.youtube.com/watch?v=XMnxKGVnEUc&t=2421s)


![DeepSeek-R1-Distill-Llama-8B](imgs/img4.png)

## Prerequisites

- AWS Account with Bedrock access
- Python environment with the following packages:
  - `huggingface_hub`
  - `boto3`

## Setup Process

1. **Download Model Weights**
   - The model weights are downloaded from Hugging Face Hub
   - Model used: `deepseek-ai/DeepSeek-R1-Distill-Llama-8B`

2. **Upload to S3**
   - Model weights are uploaded to an S3 bucket
   - Target path: `s3://[your-bucket]/models/DeepSeek-R1-Distill-Llama-8B/`

3. **Import to Amazon Bedrock**
   - Navigate to AWS Console > Bedrock > Foundation Models > Imported Models
   - Click "Import Model"
   - Name the model (e.g., `my-DeepSeek-R1-Distill-Llama-8B`)
   - Provide the S3 location of the model weights
   - Wait for successful import
   - Note down the Model ARN for API calls

![Import Model](imgs/img2.png)

## Usage

Run the Jupyter notebook [`deepseek-bedrock.ipynb`](deepseek-bedrock.ipynb) for detailed implementation.

## License

DeepSeek-R1 series support commercial use, allow for any modifications and derivative works, including, but not limited to, distillation for training other LLMs. Please note that:

- DeepSeek-R1-Distill-Qwen-1.5B, DeepSeek-R1-Distill-Qwen-7B, DeepSeek-R1-Distill-Qwen-14B and DeepSeek-R1-Distill-Qwen-32B are derived from [Qwen-2.5 series](https://github.com/QwenLM/Qwen2.5), which are originally licensed under [Apache 2.0 License](https://huggingface.co/Qwen/Qwen2.5-1.5B/blob/main/LICENSE), and now finetuned with 800k samples curated with DeepSeek-R1.
- DeepSeek-R1-Distill-Llama-8B is derived from Llama3.1-8B-Base and is originally licensed under [llama3.1 license](https://huggingface.co/meta-llama/Llama-3.1-8B/blob/main/LICENSE).
- DeepSeek-R1-Distill-Llama-70B is derived from Llama3.3-70B-Instruct and is originally licensed under [llama3.3 license](https://huggingface.co/meta-llama/Llama-3.3-70B-Instruct/blob/main/LICENSE).