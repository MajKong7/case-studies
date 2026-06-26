Engineering Case Studies — James Finn
Write-ups of systems I've designed and built end to end — spanning core
financial-infrastructure engineering in modern C++ and private, local AI
platforms. Two threads, one engineer.

The production source for these systems is private. These case studies cover the
architecture, the engineering decisions and trade-offs, and measured
results, with diagrams and short illustrative fragments rather than full code.
The goal is to show how I think about building.

🌐 veniceinference.com

Contents
Core systems engineering
Case study	What it is
ExchangeSimulator	A full-stack financial exchange in C++20 — FIX 5.0 SP2 order entry, a matching engine, drop-copy distribution, and departmental SQL Server persistence. The low-level systems work my trading-systems career was built on.
Applied AI systems
Case study	What it is
BDS — Batch Document Search	A private RAG + knowledge-graph platform for researching large document sets. Hybrid retrieval, honest trust signals, and an Obsidian knowledge-graph output.
OSINT Enrichment Subsystem	An orchestrator that discovers identifiers in a corpus, fans them across 10+ specialist tools, executes the leads they generate, and LLM-validates the findings.
Inference Backends: vLLM vs. llama.cpp	Benchmarking two backends for sustained local serving, and the topology decision that eliminated a model-swap failure class.
Agentic orchestration is an active line of work (evaluating the Hermes
Agent framework with a local model for build/workflow orchestration). I'll
add a write-up here once the results are settled enough to document honestly.

A thread that runs through all of it
Correctness as a first-class concern. Whether it's an exchange matching
engine tested under AddressSanitizer and ThreadSanitizer or a retrieval system
that flags when it can't actually answer a question, I build systems that are
honest about their own correctness rather than just producing output. It's the
same prove-it-twice discipline I carried out of two decades of systematic
trading-systems work, where independent re-implementation and cross-checking
were non-negotiable.

Stack at a glance
Systems: C++20 · FIX 5.0 SP2 / Fix8 · Poco · Boost · OpenSSL · SQL Server /
ODBC · Make

AI: Python · PySide6 · FastAPI · ChromaDB · vLLM · llama.cpp · GGUF
quantization · GLiNER · LangChain · BGE embeddings

Platform: systemd · Docker · WSL2 · uv · Obsidian · Git
