# Awesome-RNN-Transformer-Architectures

# Awesome-RNN-Transformer-Architectures

## Top RNN & Transformer Architectures Ecosystem

**Curated List of SaaS Products & Open-Source GitHub Projects**  
*Focused on Attention-Free Recurrence, Hybrid MoE Designs & Long-Context Generalization*  
**Last updated: March 2026**

This repository tracks notable **SaaS platforms** and **open-source projects** for **RNN & Transformer Architectures**. These tools provide the model architectures that power language generation, reasoning, and sequence modeling — from the dominant attention-based Transformer family to linear-time recurrent and hybrid alternatives that offer constant memory and inference time per token.

**Examples** include Hugging Face Transformers, OpenAI GPT-4, Google Gemini, Anthropic Claude, Meta Llama, Mistral AI, Cohere Command, AI21 Jamba, DeepSeek, Falcon LLM, and RWKV (the category leaders).

**Open-source emphasis**: This section is heavily expanded with every major active project for self-hosting, architecture research, and transparent model weights — ideal for researchers exploring alternatives to quadratic attention, developers building long-context applications, and organizations prioritizing open-weight access.

Contributions welcome! Open a PR to add/update entries. Keep descriptions factual and link to official sites.

## Table of Contents
- [SaaS/Hosted Platforms](#saas-hosted-platforms)
- [Open-Source GitHub Projects](#open-source-github-projects)
- [How to Contribute](#how-to-contribute)
- [Disclaimer](#disclaimer)

## SaaS/Hosted Platforms

- **OpenAI GPT-4 / GPT-5** — Proprietary decoder-only Transformer with massive scale and reinforcement learning from human feedback. API-based access only.

- **Google Gemini** — Multimodal Transformer with native vision, audio, and text capabilities. Available via Vertex AI and consumer apps.

- **Anthropic Claude** — Constitutional AI alignment with strong reasoning and long-context capabilities. API and consumer access.

- **Cohere Command** — Enterprise-focused decoder-only models with RAG and tool-use capabilities. API-based access.

- **Meta Llama (Hosted)** — Open-weight decoder-only Transformer models ranging from 1B to 405B parameters, available via hosted inference providers. Llama 4 Scout (17B with 16 experts) and Maverick (17B with 128 experts) use MoE architecture [citation:10].

- **Mistral AI (La Plateforme)** — Hosted access to Mistral's models. Most open models are released under **Apache 2.0**; some use a modified MIT license requiring commercial licensing for companies with monthly revenue over $20M [citation:3].

- **AI21 Jamba (Hosted)** — Hybrid Mamba-Transformer MoE architecture with **256K context window**. Jamba's KV cache is **8x smaller** than a vanilla Transformer at 256K context (4GB vs 32GB), and throughput is **3x that of Mixtral-8x7B** for long contexts [citation:6].

## Open-Source GitHub Projects

- **[RWKV-LM](https://github.com/BlinkDL/RWKV-LM)**  
  **The leading attention-free RNN architecture with Transformer-level performance** — Apache 2.0 licensed, **14,700+ GitHub stars** [citation:7]. **RWKV-7 "Goose"** combines the best of RNN and Transformer: **linear time, constant space (no KV-cache), fast training like a GPT (parallelizable), indefinite context length, and free sentence embedding** [citation:7]. **Key innovation**: a generalized delta rule with vector-valued gating and in-context learning rates, allowing each key channel in the state to vary independently [citation:7]. **Runtime performance**: RWKV-7 7.2B fp16 achieves **145+ token/s single-batch decoding and 10,250+ token/s at batch size 960 on RTX 5090**, with constant speed and VRAM regardless of context length [citation:7]. **Linux Foundation AI project** — RWKV runtime is already in Windows and Office [citation:7]. Models available on Hugging Face from **0.19B to 7.2B parameters**.

- **[Hugging Face Transformers](https://github.com/huggingface/transformers)**  
  **The reference library for state-of-the-art Transformers** — Apache 2.0 licensed, **100,000+ GitHub stars** [citation:1]. **Dozens of architectures with over 400,000 pretrained models** across text, vision, and audio [citation:1]. **Unified API** with Auto classes that abstract architecture details. **Pipeline API** for one-line inference across NLP, computer vision, and speech tasks [citation:1]. Supports **PyTorch, TensorFlow, and JAX** with seamless framework switching [citation:1]. **The foundation for nearly all open-source model development**.

- **[DeepSeek-V3](https://github.com/deepseek-ai/DeepSeek-V3)**  
  **Open-weight MoE model with 671B total parameters, 37B active** — MIT licensed code, with model weights under the DeepSeek Model License supporting **commercial use** [citation:4]. **Outperforms or matches frontier closed-source models** on many benchmarks while being open-weight [citation:4]. Supports **FP8 inference** natively, with deployment options across **SGLang, LMDeploy, TensorRT-LLM, vLLM, and LightLLM** [citation:4].

- **[Falcon-H1](https://github.com/tiiuae/falcon-H1)**  
  **TII's hybrid SSM-Attention architecture** — **Apache 2.0 licensed**, models from **500M to 34B parameters** [citation:5]. **Each block integrates both State Space Models (Mamba2) and Attention mechanisms in parallel**, with independently adjustable attention and Mamba head counts [citation:5]. **256K context support**, native training in **18 languages**, and scalability to 100+ languages [citation:5]. **Falcon-H1-34B achieves up to 4x improvement in input throughput and 8x speedup in output throughput** compared to similar-size Transformer models (Qwen2.5-32B) [citation:5]. **Falcon-H1-0.5B delivers performance on par with typical 7B models from 2024** [citation:5].

- **[Jamba (AI21)](https://huggingface.co/ai21labs/Jamba-v0.1)**  
  **Hybrid Transformer-Mamba MoE architecture** — **Apache 2.0 licensed**, 52B total parameters with **12B active** [citation:6]. **256K context window** with an **8x smaller KV cache** than vanilla Transformers at that context length [citation:6]. **3x throughput of Mixtral-8x7B for long contexts** [citation:6]. **Jamba-1.5** adds ExpertsInt8 quantization for efficient serving on A100 GPUs [citation:14].

- **[Llama (Meta)](https://huggingface.co/meta-llama)**  
  Meta's open-weight decoder-only Transformer family — **Llama 4 Scout (17B with 16 experts) and Maverick (17B with 128 experts)** use MoE architecture [citation:10]. **Llama 3.2** includes 1B and 3B on-device models; **Llama 3.1** ranges from 8B to 405B parameters [citation:10]. **Llama 4 models are natively multimodal** supporting text and image understanding [citation:10]. Access requires accepting license terms on Hugging Face.

- **[Mistral AI](https://huggingface.co/mistralai)**  
  Open-weight models including **Mistral, Mixtral (MoE), and Codestral Mamba** [citation:11]. Most models are **Apache 2.0 licensed**; some use a modified MIT license with a **$20M monthly revenue threshold** for commercial licensing [citation:3]. **Codestral Mamba** is a Mamba2 language model specialized in code generation under Apache 2.0 [citation:11].

### Additional Strong Open-Source Options

- **Qwen** — Alibaba's open-weight model family including dense and MoE variants with strong multilingual and coding performance.
- **Gemma** — Google's open-weight model family derived from Gemini research.
- **Mamba** — Selective State Space Model with linear-time inference as an alternative to attention.
- **Flash Linear Attention (FLA)** — Efficient implementations of linear attention and recurrent architectures including RWKV-7 [citation:7].
- **Avey** — Attention-free architecture achieving strong long-context generalization on S-NIAH benchmarks.

**Frameworks for building custom systems**: Combine **RWKV-LM** for constant-memory indefinite-context inference with RNN efficiency and Linux Foundation backing, **Hugging Face Transformers** for the broadest architecture support and standardized APIs, **DeepSeek-V3** for open-weight MoE performance matching closed models, **Falcon-H1** for hybrid SSM-Attention efficiency, and **Jamba** for hybrid MoE with small KV cache — to build a model stack tailored to your memory constraints, context length requirements, and inference latency targets.

## How to Contribute

1. Fork the repo.
2. Add/edit entries in `README.md` (follow existing format).
3. Include: name, link, 1–2 sentence description, and whether it's SaaS or open-source.
4. Submit PR with a short explanation.

Star the repo if you find it useful!

## Disclaimer

- This is a **community-curated** list — not exhaustive and not an endorsement.
- RNN and Transformer architectures differ significantly in memory profile, context generalization, and expressivity. **RWKV-7's constant memory and constant per-token inference time** make it uniquely suited for long-context and edge deployments [citation:7]. **Its "infinite context" claim is slightly overclaimed** — it can accept indefinite input but still suffers from forgetting beyond trained context windows. **Transformers remain dominant for short-to-medium context with strong associative recall** — they fail once haystack exceeds trained context window. **Hybrid architectures like Jamba and Falcon-H1** combine Mamba/SSM efficiency with Transformer recall, achieving 3-8x throughput improvements over pure Transformers [citation:5][citation:6]. **License terms vary**: Mistral's modified MIT requires commercial licensing above $20M monthly revenue [citation:3]; DeepSeek-V3 supports commercial use under its Model License [citation:4].
- Self-hosted open-source solutions require proper CUDA kernels for efficient recurrent inference, GPU memory planning for training, and validation against your specific context length and recall requirements.

---

**Made for ML engineers, architecture researchers, and developers building language models and long-context applications.**
Let's make RNN and Transformer architectures more open, efficient, and context-aware.
