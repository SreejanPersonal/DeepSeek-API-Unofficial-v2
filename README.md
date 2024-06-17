<div align="center">
  <img src="https://img.shields.io/badge/DeepSeek-API-Unofficial?style=for-the-badge&logo=huggingface" alt="DeepSeek-API-Unofficial Badge">

  <img src="https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/logo.svg?raw=true" width="1000px" alt="DeepSeek-V2">

  <h1>DeepSeek-API 🤗🤗 - Unofficial Reverse Engineering 🚀</h1>
  <p>
    <a href="https://github.com/SreejanPersonal/DeepSeek-API-Unofficial/stargazers">
      <img alt="GitHub stars" src="https://img.shields.io/github/stars/SreejanPersonal/DeepSeek-API-Unofficial?style=social">
    </a>
    <a href="https://github.com/SreejanPersonal/DeepSeek-API-Unofficial/network/members">
      <img alt="GitHub forks" src="https://img.shields.io/github/forks/SreejanPersonal/DeepSeek-API-Unofficial?style=social">
    </a>
    <a href="https://github.com/SreejanPersonal/DeepSeek-API-Unofficial/issues">
      <img alt="GitHub issues" src="https://img.shields.io/github/issues/SreejanPersonal/DeepSeek-API-Unofficial?style=social">
    </a>
  </p>
</div>

<div align="center">
  <a href="https://youtube.com/@devsdocode"><img alt="YouTube" src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white"></a>
  <a href="https://t.me/devsdocode"><img alt="Telegram" src="https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white"></a>
  <a href="https://www.instagram.com/sree.shades_/"><img alt="Instagram" src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white"></a>
  <a href="https://www.linkedin.com/in/developer-sreejan/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a>
  <a href="https://buymeacoffee.com/devsdocode"><img alt="Buy Me A Coffee" src="https://img.shields.io/badge/Buy%20Me%20A%20Coffee-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black"></a>
</div>

## Table of Contents
- [Introduction](#introduction)
- [Repository Status Update](#repository-status-update)
- [Quick Start](#quick-start)
- [Installation](#installation)
- [DeepSeek-V2: A Strong, Economical, and Efficient Mixture-of-Experts Language Model](#deepseek-v2-a-strong-economical-and-efficient-mixture-of-experts-language-model)
  - [1. Introduction](#1-introduction)
  - [2. News](#2-news)
  - [3. Model Downloads](#3-model-downloads)
  - [4. Evaluation Results](#4-evaluation-results)
  - [5. Model Architecture](#5-model-architecture)
  - [6. Chat Website](#6-chat-website)
- [Contributing](#contributing)
- [License](#license)
- [Get in Touch](#get-in-touch)

## Crafted with ❤️ by Devs Do Code (Sree)

> **Disclaimer:** This project is not officially associated with DeepSeek AI. It is an independent reverse engineering effort to explore the DeepSeek Chat Website.

🚀 **Repository Status Update:**

🛑 **Important Notice:** 
This repository is no longer maintained by the owner `Devs Do Code (Sree)`. Any contribution in this repository is heartily welcomed 💝💝

## Quick Start

1. **Clone the Repository:**
   ```bash
   git clone https://github.com/SreejanPersonal/DeepSeek-API-Unofficial.git
   ```
2. **Access the DeepSeek Playground:**
   - Navigate to the [DeepSeek Playground](https://chat.deepseek.com/) and sign in with your account.
   - This platform allows you to interact with the available models and observe API requests.

3. **Access Developer Tools:**
   - Open the Developer Tools in your browser with `Ctrl + Shift + I` (Windows/Linux) or `Cmd + Option + I` (Mac).
   - Select the `Network` tab to monitor network activity.

4. **Initiate a New Conversation:**
   - Choose any available model (e.g., Coder v2 or Chat v2) on the DeepSeek Playground to start a conversation.
   - Enter a query in the chat interface, such as `Hi, Introduce yourself`.

5. **Locate the `completions` Request:**
   - In the `Network` tab, find the API request labeled `completions`.
   - Click on this request to inspect its details.

6. **Obtain the JWT Token:**
   - In the `Request Headers` section, locate the `Authorization` entry.
   - Copy the `JWT Token` value (it appears as a long string without the `Bearer` prefix). This token serves as your API key and must be kept confidential.
   - Example format: `eyJhbGciOiJIUzI1NiIsInR5cCI6IkpXVCJ9.eyJzc29faWQiOiI3OTg3ZTZmYS1kZDUzLTRlMzQtYjkxNC1lNWUzZWVlM2IwYjMiLCJpc19vYXV0aCI6MSwib2F1dGhfcHJvdmlkZXIiOiJ......`

## Installation

After cloning the repository and obtaining your `JWT Token`, follow these steps to set up and run the project:

1. **Navigate to the Project Directory:**
   ```bash
   cd DeepSeek-API-Unofficial
   ```

2. **Create a `.env` File:**
   - Inside the project directory, create a `.env` file.
   - Add your `JWT Token` to this file. You can use the provided [.env.example](.env.example) file as a reference.
   ```bash
   cp .env.example .env
   ```
   - Open the `.env` file and insert your token:
   ```
   DEEPSEEK=your_jwt_token_here
   ```

3. **Install Required Dependencies:**
   - Ensure you have `pip` installed and run:
   ```bash
   pip install -r requirements.txt
   ```

4. **Run the Application:**
   - Execute the main script to start interacting with the DeepSeek API:
   ```bash
   python main.py
   ```

By following these steps, you will set up the environment and be able to interact with the DeepSeek models using the unofficial API.

# DeepSeek-V2:  A Strong, Economical, and Efficient Mixture-of-Experts Language Model

## 1. Introduction
Today, we’re introducing DeepSeek-V2, a strong Mixture-of-Experts (MoE) language model characterized by economical training and efficient inference. It comprises 236B total parameters, of which 21B are activated for each token. Compared with DeepSeek 67B, DeepSeek-V2 achieves stronger performance, and meanwhile saves 42.5% of training costs, reduces the KV cache by 93.3%, and boosts the maximum generation throughput to 5.76 times. 

<p align="center">
<div style="display: flex; justify-content: center;">
    <img src="https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/activationparameters.png?raw=true" style="height:300px; width:auto; margin-right:10px">
    <img src="https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/trainingcost.png?raw=true" style="height:300px; width:auto; margin-left:10px">
</div>
</p>

We pretrained DeepSeek-V2 on a diverse and high-quality corpus comprising 8.1 trillion tokens. This comprehensive pretraining was followed by a process of Supervised Fine-Tuning (SFT) and Reinforcement Learning (RL) to fully unleash the model's capabilities. The evaluation results validate the effectiveness of our approach as DeepSeek-V2 achieves remarkable performance on both standard benchmarks and open-ended generation evaluation.

## 2. News

- 2024.05.16: We released the DeepSeek-V2-Lite.
- 2024.05.06: We released the DeepSeek-V2.

## 3. Model Downloads

<div align="center">

| **Model** | **#Total Params** | **#Activated Params** | **Context Length** | **Download** |
| :------------: | :------------: | :------------: | :------------: | :------------: |
| DeepSeek-V2-Lite | 16B | 2.4B | 32k   | [🤗 HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-V2-Lite)   |
| DeepSeek-V2-Lite-Chat (SFT)   | 16B | 2.4B | 32k   | [🤗 HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-V2-Lite-Chat)   |
| DeepSeek-V2   | 236B | 21B |  128k   | [🤗 HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-V2)   |
| DeepSeek-V2-Chat (RL)   | 236B | 21B |  128k   | [🤗 HuggingFace](https://huggingface.co/deepseek-ai/DeepSeek-V2-Chat)   |

</div>

Due to the constraints of HuggingFace, the open-source code currently experiences slower performance than our internal codebase when running on GPUs with Huggingface. To facilitate the efficient execution of our model, we offer a dedicated vllm solution that optimizes performance for running our model effectively.

## 4. Evaluation Results
### Base Model
#### Standard Benchmark (Models larger than 67B)

<div align="center">

| **Benchmark** | **Domain** | **LLaMA3 70B** | **Mixtral 8x22B** | **DeepSeek-V1 (Dense-67B)** | **DeepSeek-V2 (MoE-236B)** |
|:-----------:|:--------:|:------------:|:---------------:|:-------------------------:|:------------------------:|
| **MMLU** | English | 78.9 | 77.6 | 71.3 | 78.5 |
| **BBH** | English | 81.0 | 78.9 | 68.7 | 78.9 |
| **C-Eval** | Chinese | 67.5 | 58.6 | 66.1 | 81.7 |
| **CMMLU** | Chinese | 69.3 | 60.0 | 70.8 | 84.0 |
| **HumanEval** | Code | 48.2	| 53.1 | 45.1 | 48.8 |
| **MBPP** | Code | 68.6 | 64.2 | 57.4 | 66.6 |
| **GSM8K** | Math | 83.0 | 80.3 | 63.4 | 79.2 |
| **Math** | Math | 42.2 | 42.5 | 18.7 | 43.6 |

</div>

#### Standard Benchmark (Models smaller than 16B)
<div align="center">

| **Benchmark** | **Domain** | **DeepSeek 7B (Dense)** | **DeepSeekMoE 16B** | **DeepSeek-V2-Lite (MoE-16B)** |
|:-------------:|:----------:|:--------------:|:-----------------:|:--------------------------:|
| **Architecture**      | -    | MHA+Dense           | MHA+MoE              | MLA+MoE                       |
| **MMLU**      | English    | 48.2           | 45.0              | 58.3                       |
| **BBH**       | English    | 39.5           | 38.9              | 44.1                       |
| **C-Eval**    | Chinese    | 45.0           | 40.6              | 60.3                       |
| **CMMLU**     | Chinese    | 47.2           | 42.5              | 64.3                       |
| **HumanEval** | Code       | 26.2           | 26.8              | 29.9                       |
| **MBPP**      | Code       | 39.0           | 39.2              | 43.2                       |
| **GSM8K**     | Math       | 17.4           | 18.8              | 41.1                       |
| **Math**      | Math       | 3.3            | 4.3               | 17.1                       |

</div>
For more evaluation details, such as few-shot settings and prompts, please check our paper. 

#### Context Window
<p align="center">
  <img width="80%" src="https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/niah.png?raw=true">
</p>

Evaluation results on the ``Needle In A Haystack`` (NIAH) tests.  DeepSeek-V2 performs well across all context window lengths up to **128K**. 

### Chat Model
#### Standard Benchmark (Models larger than 67B)
<div align="center">

| Benchmark | Domain         | QWen1.5 72B Chat | Mixtral 8x22B | LLaMA3 70B Instruct | DeepSeek-V1 Chat (SFT) | DeepSeek-V2 Chat (SFT) | DeepSeek-V2 Chat (RL) |
|:-----------:|:----------------:|:------------------:|:---------------:|:---------------------:|:-------------:|:-----------------------:|:----------------------:|
| **MMLU**      | English        | 76.2             | 77.8          | 80.3                | 71.1        | 78.4                 | 77.8                 |
| **BBH**       | English        | 65.9             | 78.4          | 80.1                | 71.7        | 81.3                 | 79.7                 |
| **C-Eval**    | Chinese        | 82.2             | 60.0          | 67.9                | 65.2        | 80.9                 | 78.0                 |
| **CMMLU**     | Chinese        | 82.9             | 61.0          | 70.7                | 67.8        | 82.4                 | 81.6                 |
| **HumanEval** | Code           | 68.9             | 75.0          | 76.2                | 73.8        | 76.8                 | 81.1                 |
| **MBPP**      | Code           | 52.2             | 64.4          | 69.8                | 61.4        | 70.4                 | 72.0                 |
|   **LiveCodeBench  (0901-0401)**     | Code       | 18.8          | 25.0                | 30.5        | 18.3                 | 28.7                 | 32.5                 |
| **GSM8K**     | Math           | 81.9             | 87.9          | 93.2                | 84.1        | 90.8                 | 92.2                 |
| **Math**      | Math           | 40.6             | 49.8          | 48.5                | 32.6        | 52.7                 | 53.9                 |

</div>

#### Standard Benchmark (Models smaller than 16B)

<div align="center">

| Benchmark | Domain         | DeepSeek 7B Chat (SFT) | DeepSeekMoE 16B Chat (SFT) | DeepSeek-V2-Lite 16B Chat (SFT) |
|:-----------:|:----------------:|:------------------:|:---------------:|:---------------------:|
| **MMLU**      | English        | 49.7             | 47.2          | 55.7                |
| **BBH**       | English        | 43.1             | 42.2          | 48.1                |
| **C-Eval**    | Chinese        | 44.7             | 40.0          | 60.1                |
| **CMMLU**     | Chinese        | 51.2             | 49.3          | 62.5                |
| **HumanEval** | Code           | 45.1             | 45.7          | 57.3                |
| **MBPP**      | Code           | 39.0             | 46.2          | 45.8                |
| **GSM8K**     | Math           | 62.6             | 62.2          | 72.0                |
| **Math**      | Math           | 14.7             | 15.2          | 27.9                |

</div>

#### English Open Ended Generation Evaluation
We evaluate our model on AlpacaEval 2.0 and MTBench, showing the competitive performance of DeepSeek-V2-Chat-RL on English conversation generation. 
<p align="center">
  <img width="50%" src="https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/mtbench.png?raw=true" />
</p>

#### Chinese Open Ended Generation Evaluation
**Alignbench** (https://arxiv.org/abs/2311.18743)
<div align="center">

| **模型** | **开源/闭源** | **总分** | **中文推理** | **中文语言** |
| :---: | :---: | :---: | :---: | :---: |
| gpt-4-1106-preview | 闭源 | 8.01 | 7.73 | 8.29 |
| DeepSeek-V2 Chat (RL) | 开源 | 7.91 | 7.45 | 8.36 |
| erniebot-4.0-202404 (文心一言) | 闭源 | 7.89 | 7.61 | 8.17 |
| DeepSeek-V2 Chat (SFT) | 开源 | 7.74 | 7.30 | 8.17 |
| gpt-4-0613 | 闭源 | 7.53 | 7.47 | 7.59 |
| erniebot-4.0-202312 (文心一言) | 闭源 | 7.36 | 6.84 | 7.88 |
| moonshot-v1-32k-202404 (月之暗面) | 闭源 | 7.22 | 6.42 | 8.02 |
| Qwen1.5-72B-Chat (通义千问) | 开源 | 7.19 | 6.45 | 7.93 |
| DeepSeek-67B-Chat | 开源 | 6.43 | 5.75 | 7.11 |
| Yi-34B-Chat (零一万物) | 开源 | 6.12 | 4.86 | 7.38 |
| gpt-3.5-turbo-0613 | 闭源 | 6.08 | 5.35 | 6.71 |
| DeepSeek-V2-Lite 16B Chat | 开源 | 6.01 | 4.71 | 7.32 |

</div>

#### Coding Benchmarks
We evaluate our model on LiveCodeBench (0901-0401), a benchmark designed for live coding challenges. As illustrated, DeepSeek-V2 demonstrates considerable proficiency in LiveCodeBench, achieving a Pass@1 score that surpasses several other sophisticated models. This performance highlights the model's effectiveness in tackling live coding tasks.

<p align="center">
  <img width="50%" src="https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/code_benchmarks.png?raw=true">
</p>

## 5. Model Architecture
DeepSeek-V2 adopts innovative architectures to guarantee economical training and efficient inference： 
- For attention, we design MLA (Multi-head Latent Attention), which utilizes low-rank key-value union compression to eliminate the bottleneck of inference-time key-value cache, thus supporting efficient inference. 
- For Feed-Forward Networks (FFNs), we adopt DeepSeekMoE architecture, a high-performance MoE architecture that enables training stronger models at lower costs. 

<p align="center">
  <img width="90%" src="https://github.com/deepseek-ai/DeepSeek-V2/blob/main/figures/architecture.png?raw=true" />
</p>

## 6. Chat Website
You can chat with the DeepSeek-V2 on DeepSeek's official website: [chat.deepseek.com](https://chat.deepseek.com/sign_in)

### 🤝 Contributing

Your contributions are welcome! Please refer to our [CONTRIBUTING.md](CONTRIBUTING.md) for contribution guidelines.

### 📜 License

This project is licensed under the [MIT License](LICENSE). Full license text is available in the [LICENSE](LICENSE) file.

### 📬 Get in Touch

For inquiries or assistance, please open an issue or reach out through our social channels:

<div align="center">
  <!-- Replace `#` with your actual links -->
  <a href="https://youtube.com/@devsdocode"><img alt="YouTube" src="https://img.shields.io/badge/YouTube-FF0000?style=for-the-badge&logo=youtube&logoColor=white"></a>
  <a href="https://t.me/devsdocode"><img alt="Telegram" src="https://img.shields.io/badge/Telegram-2CA5E0?style=for-the-badge&logo=telegram&logoColor=white"></a>
  <a href="https://www.instagram.com/sree.shades_/"><img alt="Instagram" src="https://img.shields.io/badge/Instagram-E4405F?style=for-the-badge&logo=instagram&logoColor=white"></a>
  <a href="https://www.linkedin.com/in/developer-sreejan/"><img alt="LinkedIn" src="https://img.shields.io/badge/LinkedIn-0077B5?style=for-the-badge&logo=linkedin&logoColor=white"></a>
  <a href="https://buymeacoffee.com/devsdocode"><img alt="Buy Me A Coffee" src="https://img.shields.io/badge/Buy%20Me%20A%20Coffee-FFDD00?style=for-the-badge&logo=buymeacoffee&logoColor=black"></a>
</div>

We appreciate your interest in `DeepSeek-API-Unofficial`