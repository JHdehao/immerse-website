# Immerse - AI 沉浸式双语阅读助手 🚀

<p align="center">
  <img src="assets/icons/icon-128.png" width="128" height="128" alt="Immerse Logo">
</p>

<p align="center">
  <strong>将每一次网页浏览转化成自然的语言习得体验</strong>
</p>

<p align="center">
  <a href="https://github.com/JHdehao/immerse-website/releases"><img src="https://img.shields.io/badge/version-v0.1.0-blue.svg?style=flat-square" alt="Version"></a>
  <a href="LICENSE"><img src="https://img.shields.io/badge/license-MIT-green.svg?style=flat-square" alt="License"></a>
  <a href="https://chrome.google.com/webstore"><img src="https://img.shields.io/badge/platform-Chrome%20%7C%20Edge%20%7C%20Safari-orange.svg?style=flat-square" alt="Platforms"></a>
</p>

---

## 💡 什么是 Immerse？

**Immerse** 是一款次世代的浏览器插件，它彻底改变了传统的“背单词”模式。通过独创的 **Smart Immersion (智能沉浸)** 算法，它能根据你目前的语言水平（CEFR 等级），在你不经意间将网页中的部分母语词汇替换为目标外语。

你不需要专门抽出时间复习，只需像往常一样阅读新闻、博客或技术文档。在真实的语境中，“悟”懂单词的含义。

## ✨ 核心特性

### 1. 智能语境替换 (Smart Contextual Replacement)
*   **分级控制**：支持 A1 (初级) 到 C2 (母语级) 的全等级覆盖。只有在你能力范围内的关键词才会被替换。
*   **智能融合**：不只是简单的单词替换，而是结合 AI 确保句子语法正确、语境自然。
*   **兴趣偏向**：可订阅科技、金融、法律等专业词库，让你的学习与职业需求完美契合。

### 2. AI 深度解析 (AI Deep Insight)
*   **一键拆解**：对于生僻词，内置 AI 助手提供词根、词缀拆解，揭示单词背后的逻辑。
*   **语境例句**：自动抓取当前网页句子，生成地道的双语对比与讲解。
*   **页面洞察**：快速总结网页核心摘要 (TL;DR)，并在阅读前提取本页重点词汇。

### 3. 科学记忆引擎 (Adaptive Learning)
*   **SuperMemo-2 算法**：基于科学的间隔重复系统（SRS），在遗忘临界点提醒复习。
*   **无感掌握判定**：系统会自动追踪你的点击与忽略行为。如果你对一个词多次曝光却未点击查看，系统判定你已通过环境习得该词，并自动降低其出现频率。

### 4. 全平台同步 (Multi-device Sync)
*   **多端打通**：无论是在 Chrome (桌面端) 还是 Safari (iOS/macOS 端)，你的生词本、学习进度实时同步。
*   **离线处理**：强大的 Trie 算法支持离线扫描，弱网环境下依然能提供基础的沉浸体验。

## 🚀 快速开始

### 1. 安装插件
*   **Chrome / Edge / Arc**: 前往 [Chrome Web Store](https://chrome.google.com/webstore) 点击“添加至浏览器”。
*   **Safari (macOS)**: 下载本应用后在扩展程序中开启。
*   **Safari (iOS)**: 通过 App Store 或 TestFlight 获取安装。

### 2. 配置水平
安装后，通过 **Onboarding** 引导选择你的英语等级（如 B1 - Intermediate）以及你感兴趣的领域。

### 3. 正常浏览
打开任何中文网页（如虎嗅、知乎、CSDN），你会发现部分词汇已悄然变成了英语。

## 🛠️ 技术内幕

本项目的技术架构追求极速与稳定：
-   **核心驱动**: 基于 Trie 树的高性能文本匹配引擎（O(m) 复杂度）。
-   **存储架构**: 使用 `Supabase` 实现云端 LWW (Last-Write-Wins) 多端同步冲突解决。
-   **AI 模型**: 适配 OpenAI (GPT-4o), Anthropic (Claude 3.5), Google (Gemini 1.5 Pro) 及 DeepSeek。
-   **前端框架**: 采用原生 JS 组件化开发，确保超低内存占用与闪电般的加载速度。

## 🌐 官方网站
了解更多详情及获取最新版安装包：[https://jhdehao.github.io/immerse-website/](https://jhdehao.github.io/immerse-website/)

## 📄 开源协议
本项目采用 [MIT License](LICENSE) 协议。

---

<p align="center">
  由 <b>Immerse Team</b> 用 ❤️ 打造，让学习像呼吸一样自然。
</p>
