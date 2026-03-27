# HuggingFace Model Cache — nomic-embed-text-v1.5

Model files for HybridRAG3 CUDA embedding. Split into parts due to GitHub 100MB limit.

## To reassemble on work machine

```powershell
git clone https://github.com/jeremysmission/hf-model-cache.git
cd hf-model-cache

# Reassemble the zip from parts:
cmd /c "copy /b hf_model_cache.zip.part_aa+hf_model_cache.zip.part_ab+hf_model_cache.zip.part_ac+hf_model_cache.zip.part_ad+hf_model_cache.zip.part_ae+hf_model_cache.zip.part_af hf_model_cache.zip"

# Extract to HF_HOME cache:
Expand-Archive -Path hf_model_cache.zip -DestinationPath "C:\hybridrag_cache\huggingface\hub\" -Force

# Verify the model folder exists:
dir C:\hybridrag_cache\huggingface\hub\models--nomic-ai--nomic-embed-text-v1.5

# Remove FORCE_OLLAMA if set:
Remove-Item Env:HYBRIDRAG_FORCE_OLLAMA_EMBED -ErrorAction SilentlyContinue

# Relaunch HybridRAG GUI — should show "embedder_direct_cuda_ready" and "mode: direct CUDA"
```

## Source
- Model: nomic-ai/nomic-embed-text-v1.5
- License: Apache 2.0
- Publisher: Nomic AI / USA
- Size: ~523MB uncompressed, ~506MB zipped
- Cached from Beast on 2026-03-27
