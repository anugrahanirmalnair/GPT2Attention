# GPT2Attention
GPT-2 Transformer Components

1. Goal of the Project
→ Understand how a decoder-only Transformer (GPT-2) processes tokens
→ Break down core building blocks instead of using high-level libraries
→ Implement attention mechanisms from scratch to understand data flow

2. Control Flow Understanding
→ Input tokens are converted into embeddings
→ Positional information is added so the model knows token order
→ Tokens pass through attention layers to understand context
→ Output embeddings are used to predict the next token

A hand-drawn control flow diagram was created to visualize this process.

3. Positional Encoding
→ Transformers do not process tokens sequentially
→ Positional encoding injects order information into token embeddings
→ Used sinusoidal functions as described in the paper
→ Added positional encodings directly to token embeddings

This allows the model to distinguish between different token positions.

5. Single-Head Self-Attention

→ Each token compares itself with all other tokens
→ The model learns which tokens matter more for a given token

Steps implemented:
→ Linear projection into Query, Key, Value
→ Scaled dot-product attention
→ Softmax normalization
→ Weighted aggregation of values

This helped build intuition before moving to multi-head attention.

5. Multi-Head Attention

→ Instead of one attention mechanism, multiple heads run in parallel
→ Each head learns different relationships (syntax, context, dependency)

Implementation steps:
→ Split embeddings across multiple heads
→ Apply attention independently per head
→ Concatenate all head outputs
→ Project back to original embedding dimension

This shows how Transformers capture multiple views of context simultaneously.

6. Key Learnings

→ Attention allows tokens to dynamically focus on relevant context
→ Positional encoding is required since Transformers have no inherent order
→ Multi-head attention improves expressiveness without increasing sequence depth
→ GPT-2 is built by stacking these components repeatedly


Files in this Repository
→ positional_encoding.py — Positional encoding implementation
→ self_attention.py — Single-head attention module
→ multihead_attention.py — Multi-head attention module
→ README.md — Explanation of approach
