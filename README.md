📊 LLM-Driven Video Feed Intelligence System

This project implements an AI-powered analytics engine for camera/video feed datasets.
It combines data engineering, metric computation, and LLM tool-calling to enable fully natural-language querying of technical video feed metadata.

Built as part of a Software Engineer Intern Technical Assessment, this system demonstrates practical skills in Python, data processing, OpenAI tool integration, and LLM-based agent design.

🚀 Key Features
🔹 1. Data Ingestion & Normalization

Loads feed metadata (CSV/Excel)

Loads schema definitions and JSON encoder/decoder configs

Normalizes IDs, codecs, and region labels

Ensures a clean, ready-to-query dataset

🔹 2. Metric Engine for Video Feeds

Core metrics implemented:

Metric	Description
Clarity Score	Resolution × FPS × Codec weighting
Latency Ranking	Lowest-latency feeds per region
FPS Ranking	Highest frame-rate feeds
Resolution Filtering	Feeds above certain resolution thresholds

Also includes fast lookup tools for:

Encoder config parameters

Decoder config parameters

🔹 3. LLM Integration (Tool Calling)

The system exposes analysis functions as structured OpenAI tools, enabling the LLM to answer questions like:

“Which Pacific feeds have the best clarity?”

“Show the lowest latency feeds in CONUS.”

“List ME feeds with at least 1080p resolution.”

“What is the decoder’s max output latency?”

The LLM determines the correct tool, extracts arguments, and returns structured results (DataFrame or dict).

🔹 4. Natural Language Query Engine

A unified function llm_tool_ask() routes queries to:

The LLM (for translation)

The tool adapters

The DataFrame outputs

This enables seamless NL → Tools → Results execution.

🔹 5. Extra Credit: Visual Analytics

Three visualization modules illustrate feed distributions:

📈 Resolution Bucket Distribution

🚦 Median Latency by Region

🎨 Codec Distribution by Region (stacked bars)

All plots follow assessment rules:

Pure Matplotlib

One chart per cell

Default colors only

🔹 6. LangGraph Mini-Workflow (Agentic Orchestration)

A small LangGraph agent is implemented:

Router Node → chooses which tool to call

Executor Node → runs Python functions

Explain Node → deterministic summary of results

Includes top1_by_region_clarity tool for multi-region aggregation

This validates true agentic behavior beyond simple tool invocation.

📂 Repository Structure
LLM-Driven-Video-Feed-Intelligence-System/
│
├── CanyonCode_HW_Report.ipynb
├── Table_feeds_v2.csv          (optional dataset)
├── encoder_config.json         (if included)
├── decoder_config.json         (if included)
├── images/                     (optional visualizations)
└── README.md

🔧 Technologies Used

Python 3

Pandas

JSON configuration parsing

OpenAI API (tool calling)

Matplotlib

LangGraph (optional agent workflow)

🧠 Example Queries

Here are some natural-language prompts supported:

"Which Pacific feeds have the best clarity?"
"Show the lowest latency feeds in CONUS."
"Highest FPS feeds in EUR."
"List ME feeds 1920x1080 or higher."
"What encoder codec?"
"What encoder GOP size?"
"What is the decoder's max output latency?"
"What is the decoder's output format?"


All queries return factual DataFrames or deterministic answers.

🏗️ Engineering Summary

This project demonstrates the ability to:

Build robust data ingestion pipelines

Design reusable metric computation functions

Wrap functions as LLM-callable tools

Implement natural-language interfaces to structured data

Use LangGraph to construct lightweight agent workflows

Produce clean, well-documented, production-grade code

📌 Why This Project Matters

This solution simulates a real-world engineering challenge:
turning raw video feed metadata into an interactive AI-driven analysis system.

It showcases strong skills in:

Data engineering

API design

LLM orchestration

Metric modeling

System thinking

Developer-friendly architecture

🤝 Contributions

Contributions, ideas, and improvements are welcome!
Feel free to submit PRs or open issues.
