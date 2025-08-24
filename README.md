#### Overview
R-Detector is a research/teaching repo for detecting whether text was AI-generated (label=1) or human-written (label=0) using pre-computed token embeddings from a Large Language Model (LLM).
Instead of training on raw text, the models consume fixed-length sentence-level tensors of shape (100, 768) (sequence length = 100 tokens, embedding dim = 768).
At inference, predictions are made per paragraph: each paragraph contains m sentences → a bag of sentence tensors with shape (m, 100, 768). Sentence-level scores are aggregated to a single paragraph label. 
This setup emphasizes model design, optimization, and evaluation on high-dimensional sequential features, without the complexity of text tokenization or end-to-end LM fine-tuning.

### Reference from https://github.com/xLearn-AU/R-Detect.  
Song, Y. et al. (2025) ‘DEEP KERNEL RELATIVE TEST FOR MACHINE-GENERATED TEXT DETECTION’, in 13th International Conference on Learning Representations Iclr 2025.
