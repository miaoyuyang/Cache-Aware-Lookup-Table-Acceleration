# Cache-Aware LUT-Based Attention Acceleration for CPU LLM Inference

*Note*: Due to the complexity of the implementation and the large size of the associated files, the codebase is being uploaded and updated continuously. We are updating towards a **fully "plug-and-play" version**. The final release will be a drop-in replacement, allowing users to directly enable LUT-based acceleration without complex manual configuration. The project will remain open source and fully usable for the community. Please stay tuned for the upcoming stable release.

 ## Introduction
This project provides a  C++ implementation of the paper *"Cache-Aware Lookup Table Acceleration for Attention in CPU LLM Inference"*. Built upon the `llama.cpp` and `ggml` frameworks, it aims to optimize the inference speed of Large Language Models (LLMs) on CPUs.
﻿
During the decode phase of Transformer models, computation is typically constrained by memory bandwidth rather than computational power. This project addresses this bottleneck by replacing traditional floating-point matrix multiplications with cache-aware lookup table (LUT) operations. This approach significantly reduces arithmetic intensity and boosts inference throughput while maintaining FP16-level precision.

Ensure your CPU supports the **AVX-512** instruction set (e.g., Intel Skylake-X, Cascade Lake, Sapphire Rapids, or newer architectures).


## Performance Benchmark
﻿Based on data from the paper, evaluated on the Intel Sapphire Rapids (SPR) platform:
﻿Speedup: Up to 2.40x improvement compared to the FP32 baseline.
Quality: Negligible increase in Perplexity (< 0.06), outperforming standard Int8 quantization.﻿
