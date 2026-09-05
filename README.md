GK001
Edge-AI SoC for fully-offline voice assistants and on-device LLM inference.

This repository is the public engineering hub for adapting neural-network models to the GK001 SoC — model support, porting guides, reproducible benchmarks, and adaptation discussions with the community.

Repo policy — read first
GK001 ships with a production NPU runtime. We publish parameters, tools, and results — we do not publish operator / kernel source code. Every model card and guide in this organization follows the same rule. See Why isn't operator source code public? for the rationale and what we do make available.

1. What is GK001
[TBD — 2–4 sentence public summary, e.g.: GK001 is a single-chip edge-AI SoC designed around one job: running real-time voice pipelines (wake word → ASR → LLM → TTS) entirely on-device, with no cloud dependency, no microphone audio leaving the device, and deterministic millisecond-scale latency.]

Target applications (non-exhaustive):

Fully-offline voice assistants and voice UI terminals

On-device LLM chat / domain Q&A appliances

Industrial and commercial voice interaction equipment

Privacy-constrained environments (medical, legal, defense-adjacent, home)

2. Key public parameters
All figures below are from the Public Parameter Checklist — the single source of truth for what this organization publishes about the silicon. Any number you see elsewhere in this org traces back to this table.

Module	Public parameter	Value
NPU	Peak compute INT8 INT16 FP16	[TBD]
NPU	Supported quantization	[TBD] (e.g., INT8 INT4 FP16 / BF16)
NPU	Supported operator coverage	[TBD] (published as a capability list only — no implementation details)
CPU	Architecture cores frequency	[TBD]
Memory	DDR type max capacity bandwidth	[TBD]
Memory	On-chip SRAM	[TBD]
Storage	eMMC UFS NOR	[TBD]
Audio	Audio front-end capability	[TBD] (mic arrays, codec, AEC/NS support at feature level)
Video	Encode / decode	[TBD]
Camera	MIPI-CSI / ISP	[TBD]
Display	Interfaces	[TBD]
I/O	USB PCIe Ethernet SDIO UART I²C SPI / GPIO	[TBD]
Security	Secure boot crypto engines TRNG	[TBD]
Power	Typical run / standby	[TBD]
Package	Package size operating temperature / lifetime	[TBD]
Software	OS & BSP runtime toolchain	[TBD] (see §3)
3. Software stack (public summary)
[TBD — one paragraph per layer once approved, e.g.: Linux BSP · NPU runtime with C/Python API · ONNX conversion & quantization toolchain · model zoo of pre-adapted models …]

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
[TBD — e.g.: Q4 2026 — first verified model pack …]

7. Contact & community
Discussions: GK001/Discussions

Contact email: [TBD — decide public vs. private]

Commercial / NDA inquiries (samples, datasheet, evaluation kit): [TBD]

8. License
Documentation in this repository is licensed under CC-BY-4.0 unless stated otherwise; sample code (where present) is licensed under Apache-2.0. Model files retain their upstream licenses. Operator source code is not part of this organization by design.

GK001 is a semiconductor product name. This organization is its public engineering and community hub.
