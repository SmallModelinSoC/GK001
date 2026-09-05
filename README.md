GK001
Edge-AI SoC for fully-offline voice assistants and on-device LLM inference.

This repository is the public engineering hub for adapting neural-network models to the GK001 SoC — model support, porting guides, reproducible benchmarks, and adaptation discussions with the community.

Repo policy — read first
GK001 ships with a production NPU runtime. We publish parameters, tools, and results — we do not publish operator / kernel source code. Every model card and guide in this organization follows the same rule. See Why isn't operator source code public? for the rationale and what we do make available.

1. What is GK001
GK001 is a single-chip edge-AI SoC designed around one job: running real-time voice pipelines (wake word → ASR → LLM → TTS) entirely on-device, with no cloud dependency, no microphone audio leaving the device, and deterministic millisecond-scale latency.

Target applications (non-exhaustive):

Fully-offline voice assistants and voice UI terminals

On-device LLM chat / domain Q&A appliances

Industrial and commercial voice interaction equipment

Privacy-constrained environments (medical, legal, defense-adjacent, home)

2. Key public parameters
All figures below are from the Public Parameter Checklist — the single source of truth for what this organization publishes about the silicon. Any number you see elsewhere in this org traces back to this table.

Module	Public parameter	Value
NPU	Peak compute INT8&FP16
NPU	Supported quantization	INT8 INT4 FP16
NPU	Supported operator coverage	 (published as a capability list only — no implementation details)
CPU	Architecture cores frequency	200MHz
Memory	DDR type max capacity bandwidth	
Memory	On-chip SRAM	512MByte
Audio	Audio front-end capability	 (mic arrays, codec, AEC/NS support at feature level)
I/O	USB PCIe Ethernet SDIO UART I²C SPI / GPIO	
Power	Typical run / standby	
3. Software stack (public summary)
Linux BSP · NPU runtime with C/Python API · ONNX conversion & quantization toolchain · model zoo of pre-adapted models

4. What this repository is for — model adaptation
This is the "chip adaptation" discussion hub. You can:

Request a model adaptation — open a Model Adaptation Request. Each request is triaged and appears on the model zoo roadmap.

Check what is already adapted — browse the GK001 model zoo for model cards with real measured numbers (memory, latency, throughput, accuracy delta) — never unverified marketing figures.

Understand how numbers are produced — every published figure follows the Benchmark Methodology, so results are reproducible and comparable.

Discuss adaptation approaches — technical Q&A on porting, quantization, memory planning, and operator fallbacks lives in Discussions.

Report your own measurements — community benchmark reports are welcome via the Benchmark Report template.

What a published model card contains
For every adapted model we publish: model name & upstream source, license, task, quantization config, peak RAM, latency / throughput numbers, toolchain version, and measurement conditions. We do not publish: operator implementations, internal graph rewrite tricks, or anything beyond the approved public parameter list.

5. Quick links
Document	Purpose
SoC Overview	Concise technical introduction to GK001
Model Adaptation Guide	Step-by-step porting workflow for this NPU
Benchmark Methodology	How every published number is measured
Public Parameter Checklist	The approved public parameter source of truth
FAQ	Common questions, including disclosure policy
Contributing	How to contribute (reports, docs, requests)
Security	Reporting vulnerabilities
6. Roadmap (public view)
Update soon.
7. Contact & community
Discussions: GK001/Discussions

Contact email: Gkslm2016@gmail.com

Commercial / NDA inquiries (samples, datasheet, evaluation kit): yes

8. License
Documentation in this repository is licensed under CC-BY-4.0 unless stated otherwise; sample code (where present) is licensed under Apache-2.0. Model files retain their upstream licenses. Operator source code is not part of this organization by design.

GK001 is a semiconductor product name. This organization is its public engineering and community hub.
