# Awesome Agent Skills

> 一个关于构建自主 AI Agent 所需的核心技能、工具集成和认知能力的精选列表。

**Agent Skills** 指的是 AI Agent 为了完成复杂任务所必须具备的能力。本项目不仅收集理论资源，更提供了一系列**可直接使用的 Skill 实现**，涵盖内容创作、图像生成、数据处理等多个领域。

---

## 📖 目录 (Contents)

- [Awesome Agent Skills](#awesome-agent-skills)
  - [📖 目录 (Contents)](#-目录-contents)
  - [📦 技能库 (Skills Library)](#-技能库-skills-library)
    - [🎨 图像与视觉 (Image \& Visuals)](#-图像与视觉-image--visuals)
    - [� 内容与数据处理 (Content \& Data Processing)](#-内容与数据处理-content--data-processing)
    - [🛠️ 工具与实用程序 (Tools \& Utilities)](#️-工具与实用程序-tools--utilities)
  - [📂 目录结构 (Directories)](#-目录结构-directories)
  - [🧠 核心概念 (Core Concepts)](#-核心概念-core-concepts)
    - [规划与推理 (Planning \& Reasoning)](#规划与推理-planning--reasoning)
    - [记忆管理 (Memory Management)](#记忆管理-memory-management)
    - [工具使用 (Tool Use)](#工具使用-tool-use)
  - [📚 学习资源 (Resources)](#-学习资源-resources)
  - [🤝 贡献 (Contributing)](#-贡献-contributing)
  - [📄 License](#-license)

---

## 📦 技能库 (Skills Library)

本项目包含以下开箱即用的 Agent Skills：

### 🎨 图像与视觉 (Image & Visuals)

| Skill Name                 | Description                                                                                       | Source                                                         |
| -------------------------- | ------------------------------------------------------------------------------------------------- | -------------------------------------------------------------- |
| **Article Illustrator**    | 分析文章结构，识别配图位置，并生成风格统一的插图。支持 Infographic, Scene, Flowchart 等多种类型。 | [`baoyu-article-illustrator`](baoyu/baoyu-article-illustrator) |
| **Comic Creator**          | 创建知识科普类漫画，支持多种艺术风格（如 Manga, Line Art）和分镜布局。                            | [`baoyu-comic`](baoyu/baoyu-comic)                             |
| **Cover Image Generator**  | 生成高质量的文章封面图，支持 5 维度定制（类型、色板、渲染风格、文本、情绪）。                     | [`baoyu-cover-image`](baoyu/baoyu-cover-image)                 |
| **Infographic Generator**  | 生成专业的信息图表，提供 21 种布局和 20 种视觉风格的自由组合。                                    | [`baoyu-infographic`](baoyu/baoyu-infographic)                 |
| **Image Generation (SDK)** | 集成 OpenAI, Google, DashScope, Replicate 等多源 API 的通用图像生成工具。                         | [`baoyu-image-gen`](baoyu/baoyu-image-gen)                     |
| **Image Compressor**       | 智能图片压缩工具，自动选择最佳工具（WebP/PNG）优化图片体积。                                      | [`baoyu-compress-image`](baoyu/baoyu-compress-image)           |

### � 内容与数据处理 (Content & Data Processing)

| Skill Name             | Description                                                                       | Source                                                           |
| ---------------------- | --------------------------------------------------------------------------------- | ---------------------------------------------------------------- |
| **X to Markdown**      | 将 X (Twitter) 推文、Thread 或文章转换为带有 YAML Front Matter 的 Markdown 格式。 | [`baoyu-danger-x-to-markdown`](baoyu/baoyu-danger-x-to-markdown) |
| **Markdown Formatter** | 自动格式化 Markdown 文档，优化排版、标题、列表及代码块样式。                      | [`baoyu-format-markdown`](baoyu/baoyu-format-markdown)           |

### 🛠️ 工具与实用程序 (Tools & Utilities)

| Skill Name            | Description                                                  | Source                                                     |
| --------------------- | ------------------------------------------------------------ | ---------------------------------------------------------- |
| **Gemini Web Client** | 逆向工程的 Gemini Web API 客户端，支持多轮对话及多模态生成。 | [`baoyu-danger-gemini-web`](baoyu/baoyu-danger-gemini-web) |
| **SymCLI**            | Deterministic symbolic computation engine and C# code analyzer. | [`Wowo51/SymCLI`](https://github.com/Wowo51/Sym)           |

---

## 📂 目录结构 (Directories)

- **[baoyu/](baoyu/)**: 由 Baoyu 贡献的技能集合，专注于内容创作与图像处理工作流。
- **[cheval/](cheval/)**: (Coming Soon) 更多技能正在构建中。

---

## 🧠 核心概念 (Core Concepts)

构建 Agent 所需的理论基础：

### 规划与推理 (Planning & Reasoning)

- **Chain of Thought (CoT)**: 通过中间推理步骤提升逻辑能力。
- **ReAct (Reason + Act)**: 结合推理和行动，动态调整计划。

### 记忆管理 (Memory Management)

- **RAG (Retrieval-Augmented Generation)**: 基于向量数据库的外部知识检索。
- **Context Management**: 优化上下文窗口的使用。

### 工具使用 (Tool Use)

- **Function Calling**: 结构化输出以调用外部 API。
- **Code Interpreter**: 执行代码以进行复杂计算或数据分析。

---

## 📚 学习资源 (Resources)

- [Lilian Weng: LLM Powered Autonomous Agents](https://lilianweng.github.io/posts/2023-06-23-agent/)
- [LangChain Documentation](https://python.langchain.com/docs/get_started/introduction)
- [AutoGPT](https://github.com/Significant-Gravitas/AutoGPT)

---

## 🤝 贡献 (Contributing)

欢迎提交 PR 贡献新的 Skill！请确保包含 `SKILL.md` 描述文件。

## 📄 License

[MIT License](LICENSE)
