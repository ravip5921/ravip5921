
# Hi, I'm Ravi Pandey 👋

🎓 **M.S. Computer Science** @ University of Nebraska Omaha (GPA: 4.0)  
🔬 **Graduate Research Assistant** | Neuro-Symbolic AI & Logic Programming  
🤖 **AI Engineer** | Agentic Development & LLM Systems  
💻 **Software Engineer** | Full-Stack Development, Systems & Cloud  
🌎 **Omaha, Nebraska**

---

## 🚀 About Me

I'm a Computer Engineer, researcher, and software engineer passionate about building **intelligent systems that combine strong theoretical foundations with practical engineering**.

My interests span artificial intelligence, programming languages, agentic systems, operating systems, and software engineering.

Currently, as a Graduate Research Assistant at the **University of Nebraska Omaha**, I work on research and development involving **Answer Set Programming (ASP), functional logic programming, and neuro-symbolic AI**.

My work includes developing **FUNASP**, a functional extension of ASP implemented through compiler transformations and Clingo integration, and exploring **NeurASP**, which combines neural-network predictions with symbolic reasoning and differentiable computation.

Beyond research, I enjoy building practical AI systems, particularly **agentic software development workflows, LLM-powered applications, computer vision pipelines, and full-stack platforms**.

### 🔍 Areas of Interest

- 🧠 **Neuro-Symbolic AI** — Integrating neural learning with symbolic knowledge representation and reasoning.
- ⚙️ **Programming Languages & Compilers** — AST transformations, language extensions, source-to-source compilation, and solver integration.
- 🤖 **Agentic AI & Software Engineering** — Multi-agent workflows, autonomous code generation, validation, and human-in-the-loop development.
- 🔎 **Explainable AI & LLMs** — Developing systems that make machine-learning predictions and reasoning processes understandable.
- 🖥️ **Operating Systems & Systems Research** — Memory management, virtualization, and performance analysis.
- ☁️ **Cloud, Data & Distributed Systems** — Backend services, ETL pipelines, containerization, and analytics.

---

## 🧪 Research & Featured Projects

### 🔬 FUNASP — Functional Answer Set Programming

📦 **Research:** [krr-uno-fasp](https://github.com/krr-uno-fasp)

**FUNASP** is an extension of Answer Set Programming (ASP) that introduces user-defined functions, functional assignments, and higher-level language constructs while retaining Clingo as its grounding and solving backend.

The project aims to make declarative logic programs more expressive by allowing relationships to be represented directly as functions rather than requiring conventional predicate-based encodings.

As part of my graduate research, I developed the language implementation and compilation pipeline using **Python, Clingo, and Abstract Syntax Tree (AST) transformations**.

**Key features and contributions:**

- Implemented functional assignment syntax using the `:=` operator.
- Developed parser extensions and AST representations for functional constructs.
- Implemented transformations for nested function expressions, introducing auxiliary variables and equations where necessary.
- Supported declarative partial functions, allowing function values to remain undefined when insufficient information is available.
- Implemented transformations for choice assignments and aggregate-based functional definitions.
- Developed source-to-source compilation from functional ASP syntax into ordinary ASP programs.
- Integrated Clingo as the underlying grounding and solving backend.
- Implemented translation of solver results back into functional notation.

**Example FUNASP syntax:**

```prolog
owner(ticket_1) := dana.
manager(dana) := lee.

escalation(T) := manager(owner(T)) :- ticket(T).
```

The compilation process follows the general architecture:

`FUNASP Source → Parsing → AST Normalization → Function Unnesting → ASP Translation → Clingo → Functional Answer Sets`

A central challenge is preserving the semantics of partial functions, nested expressions, negation, and aggregate operations throughout compilation.

The project connects **knowledge representation, formal logic, programming language design, and compiler engineering**.

**Technologies:** `Python` `Clingo` `ASP` `AST Transformations` `Tree-sitter` `Compiler Design` `Knowledge Representation`

---

### 🧠 NeurASP — Neural-Symbolic Learning with Program Splitting

**Research Area:** Neuro-Symbolic AI, Differentiable Logic Programming

NeurASP combines **neural-network predictions with Answer Set Programming**, enabling neural models to learn from symbolic constraints and task-level observations.

The research system explores compiling symbolic reasoning into reusable **PyTorch tensor operations**, separating logical compilation from numerical execution during neural-network training.

For example, in an MNIST addition task, a neural network predicts probability distributions over handwritten digits, while ASP rules describe their arithmetic relationships. Training can use the observed sum without directly supervising every individual digit prediction.

**Key implementation components:**

- **NeurASP parser:** Processes neural declarations and translates the program into standard ASP.
- **Grounding and compilation:** Uses Clingo to determine valid logical assignments and relationships.
- **Stable-model enumeration:** Constructs reusable mappings between neural input assignments and symbolic outcomes.
- **Tensor module generation:** Converts logical relationships into PyTorch-compatible probability computations.
- **Differentiable execution:** Uses tensor gathering, multiplication, and projection to calculate outcome probabilities while supporting gradient-based learning.
- **Program splitting:** Investigates reducing the combinatorial cost of reasoning by dividing programs into smaller dependency-based stages.
- **State projection and caching:** Reuses intermediate symbolic states and valid transitions during probabilistic computation.

**Architecture:**

`NeurASP Program → Parsing & Grounding → Symbolic Compilation → Tensor Representation → PyTorch Execution → Neural Learning`

The project currently explores two complementary implementation paths:

1. **Native Tensor Pipeline:** Compiles complete stable-model relationships into reusable PyTorch modules.
2. **Splitting-Based Pipeline:** Uses projected intermediate states and cached transitions to reduce redundant reasoning across stages.

The longer-term research direction is to integrate automatic program decomposition with differentiable module generation.

**Implemented research examples include:**

- MNIST digit addition
- Digit membership tasks
- Card arithmetic tasks
- Variable-length digit addition using splitting-based evaluation

Benchmarking infrastructure supports comparisons of compilation, training, evaluation, and overall runtime.

This work sits at the intersection of **deep learning, probabilistic reasoning, symbolic AI, compiler construction, and differentiable programming**.

**Technologies:** `Python` `PyTorch` `Clingo` `ASP` `Neural Networks` `Program Splitting` `Tensor Operations`

---

### 🤖 Agentic Harness — Multi-Agent Software Development Framework

📦 **Repository:** [Agentic_Harness](https://github.com/ravip5921/Agentic_Harness)

Agentic Harness is a Python-based software engineering framework that uses **LLM-powered agents and LangGraph orchestration** to transform natural-language development tasks into implemented, tested, and reviewable software artifacts.

The system organizes development into four specialized stages:

| Agent | Responsibility |
|---|---|
| 🔍 Research | Investigates requirements, repository context, and technical constraints to generate an engineering specification. |
| 💻 Developer | Implements the specification and stages generated or modified source files. |
| 🧪 QA | Executes isolated tests, evaluates requirements, and provides structured feedback. |
| 🚀 Release | Prepares validated release artifacts for human review and approval. |

**Key engineering features:**

- Implemented a multi-stage workflow using **LangGraph** with explicit state transitions and typed contracts.
- Integrated LLM-based research, code generation, and requirements assessment.
- Developed repository inspection and bounded file-generation tools.
- Built a **QA-to-Developer feedback loop** that supports iterative corrections with configurable retry limits.
- Integrated Docker-based execution for isolated Python validation and testing.
- Implemented structured run artifacts, including engineering specifications, file manifests, QA reports, and release candidates.
- Added human-in-the-loop release approval and support for draft GitHub pull requests.
- Supported multiple model-provider configurations, including Groq, Gemini, and compatible LLM endpoints.

**Workflow:**

`Natural Language Task → Research → Developer → QA → Release`

When QA detects an implementation failure, the workflow can return to the Developer agent for another revision rather than immediately terminating.

**Recorded demonstration — GitHub organization connector:**

The harness was used to implement a GitHub integration for retrieving organization members.

- Generated an engineering specification and connector implementation.
- Detected two failing tests during the initial QA attempt.
- Corrected the issues through one Developer revision.
- Completed the recorded demonstration with **14 passing tests**.
- Prepared a draft GitHub pull request following human approval.

The system emphasizes **structured agent collaboration, controlled tool execution, automated verification, traceability, and human oversight**.

**Technologies:** `Python` `LangGraph` `Pydantic` `LLMs` `Docker` `pytest` `Git` `GitHub CLI` `Agentic AI`

---

### 🌾 FarmAI — Intelligent Farm Record Digitization

**Project:** `FarmAI`

FarmAI is a document-processing platform designed to convert scanned or photographed agricultural record tables into structured, reviewable datasets.

The project combines **computer vision, optical character recognition (OCR), template-based validation, and a full-stack review application** to digitize farm records while preserving their underlying table structure.

Unlike general-purpose OCR scripts, FarmAI focuses on recognizing and reconstructing bordered tables before extracting text from individual cells.

**Core capabilities:**

- Processes scanned images and PDF documents.
- Applies grayscale conversion, adaptive binarization, denoising, and skew correction.
- Detects table borders, horizontal and vertical lines, and intersection points using OpenCV.
- Reconstructs table grids and extracts individual cell images.
- Supports template-guided grid refinement for known farm-record layouts.
- Integrates multiple OCR approaches:
  - Tesseract OCR
  - TrOCR for handwritten text
  - Vision-LLM-based recognition and verification
- Applies column-specific validation rules to recognized values.
- Exports structured results to CSV and JSON.

**Application architecture:**

The project includes:

- A reusable Python document-processing pipeline.
- A command-line interface for automated processing.
- A Streamlit-based interface for experimentation and manual review.
- A React/TypeScript frontend for reviewing recognized records.
- A FastAPI backend with SQLite-backed persistent processing jobs.
- Background workers for document-processing tasks.
- Ground-truth comparison utilities and automated tests.

**Evaluation:**

- Evaluated OCR results against **712 scored cells** across eight redacted farm-record result files.
- Implemented support for nine form templates.
- Developed tools for measuring exact and normalized cell-level recognition accuracy.

OCR performance remains an area of experimentation and refinement, particularly for challenging handwritten records and inconsistent document layouts.

FarmAI combines **computer vision research with practical backend engineering and human-in-the-loop data verification**.

**Technologies:** `Python` `OpenCV` `Tesseract` `TrOCR` `LLMs` `FastAPI` `React` `TypeScript` `SQLite` `Streamlit`

---

### 🧠 Explainable AI + LLM Integration Study (2025)

**Projects:** `Doctor-Speciality-Recommender` | `DoctorSpecialityRecommender-Quiz`

A web-based explainable AI platform designed to investigate how **LLM-powered interactive explanations affect user understanding of machine-learning predictions**.

The system combines classical machine learning with an interactive explanation interface.

**Key components:**

- Random Forest classifier for disease prediction based on reported symptoms.
- Multinomial Logistic Regression for specialist recommendations.
- LLM-based explanations for the model's predictions and recommendations.
- Interactive follow-up questions about probabilities, symptoms, and model decisions.
- Structured pre/post-study quizzes for assessing user understanding.
- Data logging for quantitative analysis of explanation effectiveness.

The study compares conventional model explanations against LLM-assisted interactive explanations.

**Technologies:** `Python` `Streamlit` `Scikit-learn` `LLM APIs` `Supabase` `Explainable AI`

---

### 🔬 Memory Pressure Analysis

**Project:** `Memory-Pressure-Analysis`

Research examining the effects of constrained memory resources on application performance in virtualized and containerized environments.

**Research areas:**

- Docker containers and Linux control groups (cgroups).
- KVM virtual machines.
- Memory pressure and resource contention.
- Tail latency and throughput under constrained memory.
- Performance behavior across different isolation mechanisms.

The project connects **operating systems, virtualization, memory management, and experimental performance analysis**.

**Technologies:** `Linux` `Docker` `KVM` `Systems Programming` `Performance Analysis`

---

### 📸 Smart Attendance System

**Project:** `SmartAttendanceSystem`

A real-time attendance management system based on facial recognition.

**Key features:**

- Face recognition for automated attendance.
- On-device facial feature extraction.
- Transmission of facial embeddings rather than complete image data.
- Reduced network overhead through edge-side processing.

The project explores **computer vision, edge computing, and practical biometric recognition systems**.

---

### 🔎 OCR & Accessibility Research

**Publication:** *Improved Pre-processing Techniques for Mobile-based OCR Systems*  
**Conference:** ICT-CEEL 2023

Research focused on improving OCR preprocessing techniques for mobile-based text recognition and accessibility.

**Contributions:**

- Image segmentation.
- Noise filtering and preprocessing.
- Skew detection and correction.
- OCR accuracy improvement of 50% in the reported research.

**Related repositories:** `OCR` `Segmentation` `SkewCorrection` `EasyRead`

This work established my early interest in **computer vision, document understanding, and accessible computing**.

---

## 💼 Professional Experience

### 🏛 Graduate Research Assistant
**University of Nebraska Omaha | Jan 2025 – Present**

Working on research at the intersection of knowledge representation, declarative programming, and neuro-symbolic artificial intelligence.

- Developed FUNASP, a functional extension of Answer Set Programming.
- Built language parsing and AST transformation pipelines.
- Implemented compiler transformations for functions, assignments, and aggregate expressions.
- Integrated extended language constructs with Clingo's grounding and solving infrastructure.
- Worked on neural-symbolic reasoning systems combining ASP and neural-network computation.
- Explored techniques for translating symbolic reasoning into differentiable tensor operations.

### 💻 Associate Software Engineer
**GrowByData Services**

- Developed data extraction and ETL pipelines using Python.
- Integrated Google Analytics, Google Ads, and Meta Ads APIs.
- Built and maintained data-processing components for analytics workflows.
- Contributed to business intelligence and e-commerce analytics solutions.
- Worked on API integrations, data transformation, and production software reliability.

### 🎮 Game Development Intern
**Avana Game Studios**

- Developed interactive applications using Unity and C#.
- Built a guitar simulation application incorporating MIDI-based input.
- Designed and worked with 3D assets using Blender.

---

## 🛠 Technical Stack

### Programming Languages

`Python` `C` `C++` `Java` `JavaScript` `TypeScript` `SQL` `C#`

### AI, Machine Learning & LLMs

`PyTorch` `Scikit-learn` `LLMs` `Computer Vision` `NLP` `Explainable AI` `Statistical Modeling` `Neural-Symbolic AI`

### Agentic AI & Development

`LangGraph` `LLM Agents` `Multi-Agent Workflows` `Tool Calling` `Agent Orchestration` `Automated Testing` `Human-in-the-Loop Systems`

### Logic Programming & Compiler Engineering

`Answer Set Programming` `FUNASP` `NeurASP` `Clingo` `Tree-sitter` `AST Transformations` `Parsing` `Source-to-Source Compilation`

### Backend, Web & APIs

`Django` `Flask` `FastAPI` `React` `Node.js` `Streamlit` `REST APIs`

### Systems, Cloud & DevOps

`Linux` `Docker` `KVM` `AWS` `Azure` `CI/CD` `Git` `GitHub Actions`

### Data Engineering & Analytics

`Pandas` `NumPy` `Matplotlib` `Snowflake` `Power BI` `ETL Pipelines` `SQLite` `Supabase`

### Computer Vision & Document Processing

`OpenCV` `Tesseract OCR` `TrOCR` `Image Preprocessing` `Table Recognition` `Document Understanding`

---

## 📊 Research & Engineering Highlights

### 🔬 Knowledge Representation & Compiler Development

Developing **FUNASP**, extending Answer Set Programming with functional constructs while maintaining compatibility with Clingo.

My work involves language parsing, AST rewriting, function unnesting, and transforming higher-level declarative constructs into solver-compatible programs.

Research organization: [krr-uno-fasp](https://github.com/krr-uno-fasp)

### 🧠 Neuro-Symbolic AI

Working on approaches that combine neural predictions and symbolic reasoning.

Research involving NeurASP explores compiling stable-model relationships into reusable PyTorch computations and reducing the cost of probabilistic reasoning through program splitting.

### 🤖 Agentic Software Engineering

Built an agentic development harness that coordinates specialized LLM agents for research, implementation, testing, and release.

My interest is in making AI-assisted software development more **structured, verifiable, reproducible, and controllable**, rather than relying exclusively on unconstrained code generation.

Project: [Agentic_Harness](https://github.com/ravip5921/Agentic_Harness)

### 🔎 Applied AI & Computer Vision

Developed applications combining machine learning, computer vision, LLMs, and human review.

Examples include:

- FarmAI document digitization and layout-aware OCR.
- LLM-assisted explainable medical recommendation systems.
- Face-recognition-based attendance management.
- OCR preprocessing and accessibility research.

### ⚙️ Systems & Performance Engineering

Interested in operating systems, resource management, virtualization, and performance evaluation.

Projects include `Memory-Pressure-Analysis`, `OS-Project`, and `distributed_rtos`.

### ☁️ Full-Stack & Data Engineering

Experience building backend services, API integrations, ETL pipelines, dashboards, and interactive web applications.

From low-level systems programming to high-level agentic AI systems, I enjoy **understanding how software works across abstraction layers and building tools that connect them**.

---

## 🏆 Honors & Achievements

- 💰 **$5,000 GRACA Research Grant** — University of Nebraska Omaha
- 🥇 **First Prize** — openIMIS-DRG Datathon 2022
- 🎓 **Batch Topper** — Multiple Semesters
- 📚 **GPA: 4.0/4.0** — M.S. Computer Science, University of Nebraska Omaha

---

## 📈 Current Focus (2026)

My current research and engineering interests include:

- **Functional Answer Set Programming:** Language design, semantic-preserving compilation, and solver integration.
- **Neuro-Symbolic Learning:** Connecting neural predictions with structured symbolic reasoning.
- **Agentic Development:** Building reliable, multi-agent software engineering workflows with automated validation and human oversight.
- **Differentiable Reasoning:** Translating symbolic computations into efficient neural-network training operations.
- **LLM-Powered Applications:** Combining language models with domain-specific data, tools, and traditional software systems.
- **Explainable AI:** Understanding how AI-generated explanations influence user comprehension.
- **Systems Research:** Memory pressure, containerization, virtualization, and performance evaluation.

I'm particularly interested in the intersection of **AI, formal reasoning, programming languages, and practical software systems**.

---

## 📄 Resume

📄 [View My Resume (PDF)](https://github.com/ravip5921/ravip5921/raw/main/Resume.pdf)

---

## 🌐 Connect With Me

- 💼 **LinkedIn:** [linkedin.com/in/ravip5921](https://linkedin.com/in/ravip5921)
- 💻 **GitHub:** [github.com/ravip5921](https://github.com/ravip5921)
- 📧 **Email:** [pandeyyravi7@gmail.com](mailto:pandeyyravi7@gmail.com)

---

## 🤝 Let's Collaborate

I'm always interested in connecting with researchers, engineers, and teams working on:

- Neuro-symbolic AI and knowledge representation.
- Agentic AI and autonomous software development.
- Programming languages, compilers, and developer tooling.
- LLM-based applications and explainable AI.
- Computer vision and intelligent document processing.
- Operating systems and performance engineering.

**If you're building intelligent systems that combine rigorous reasoning with practical engineering, I'd love to connect.** 🚀
