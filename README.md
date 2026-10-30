# Nearkeep

**让重要的，始终在身边。 · Keep what matters close.**

[中文](#中文) · [English](#english) · [下载 / Download](https://github.com/jayueseven/nearkeep-releases/releases/tag/v1.0.0-preview.2) · [版本记录 / Releases](https://github.com/jayueseven/nearkeep-releases/releases)

## 中文

Nearkeep 是一个本地优先的文件工作空间。把值得留下的文件收进口袋，按自己的方式整理，再通过文件名、关键词或内容描述找回来。桌面伴侣 **Nicole** 陪你完成收取和查找，让资料更容易回到手边。

当前预览版聚焦 **收集 → 整理 → 查找 → 使用**。它已经具备真实文件夹管理和本地语义检索；个人 AI 空间、持续理解上下文等属于长期方向，不代表本版提供聊天、生成式摘要或云同步。

### 下载与系统要求

**[下载 Nearkeep 1.0.0 Preview 2](https://github.com/jayueseven/nearkeep-releases/releases/tag/v1.0.0-preview.2)** · 免费、未公证的 macOS 体验版

| 项目 | 当前支持 |
| --- | --- |
| 平台 | Apple Silicon（M 系列）Mac；暂不提供 Intel 或 Windows 安装包 |
| 系统 | 构建最低目标 macOS 14；当前实测 macOS 27.0.1，尚未验收所有中间系统版本 |
| 安装包 | ZIP，内含 Nearkeep.app 和本地检索模型，约 618.5 MB；需额外解压空间 |
| 签名 | 临时签名（ad hoc），没有 Developer ID 签名或 Apple 公证 |
| 状态 | 公开预览版；兼容性与完整安装生命周期验收仍在持续进行 |

### 可以做什么

- **收进来**：点击上传，或拖入资料库、桌面 Nicole；支持文件、文件夹和混合批量，保留嵌套结构及空文件夹。
- **自己决定存法**：复制保存独立副本并保留原件；移动在安全保存成功后移出原位置；确认前可取消。
- **真实目录整理**：在自己选择的保存位置创建、重命名和移动文件夹，资料库与访达中的目录层级对应。收藏、常用文件夹和排序帮助快速访问。
- **统一查找**：文件名和关键词检索先返回结果，需要时由本地 Qwen 语义检索补充；支持搜索历史及单条删除。
- **找到后使用**：在资料库定位并查看详情，预览文件，或在访达中显示保存的副本。
- **随手唤出**：录制快速搜索快捷键，在 Nearkeep 运行时从其他应用唤出搜索；支持中英文、浅深色主题及 Nicole 桌面显示设置。

### 安装与首次使用

1. 从版本页下载 `Nearkeep-1.0.0-preview.2-macOS-arm64.zip` 和 `SHA256SUMS.txt`，放在同一目录，执行：

   ```sh
   shasum -a 256 -c SHA256SUMS.txt
   ```

   应显示 ZIP 文件名后带 `OK`。校验和验证下载一致性，不等同于公证或全面安全审计。
2. 解压，将 **Nearkeep.app** 放入“应用程序”。已有版本请先正常退出，只替换应用，不删除资料库保存目录。
3. 本版未公证，macOS 可能阻止首次打开。确认来源可信、校验一致后，按 [Apple 官方说明](https://support.apple.com/en-us/102445) 处理该应用的提示。不要关闭系统整体保护；如提示会损害电脑或文件已损坏，请停止并反馈。
4. **全新资料状态**首次打开会显示空资料库，并引导选择专用保存文件夹；不会预填开发者路径或示例文件。取消选择不会开始导入。
5. **已有用户**更新后继续使用原资料和保存位置，不会因重新下载应用而清空。请勿同时运行多个版本。
6. 导入时选择复制或移动。完成后点“查看”定位本批内容，或“完成”关闭提示。

### 本地检索的能力与边界

随包提供 **Qwen3-Embedding-0.6B Q8_0**，通过本地 llama.cpp 运行时参与语义检索。它是检索模型，**不是聊天模型**。例如，带有付款条款的文本可通过“客户拖着不付款会有什么责任”检索，并展示命中片段；效果取决于正文提取与相关性，需核对原文。

当前支持有文字层的 PDF，以及 TXT、Markdown、CSV、TSV、JSON、LOG 等文本。扫描 PDF 没有完整 OCR，Office 等其他格式不承诺正文检索。长文、大文件或处理时限可能只覆盖部分正文；冷启动可能需要数十秒，模型忙或不可用时普通检索仍可用。

当前文件管理、索引与模型检索在本机处理，不将文件正文发送给云端 AI。系统安全检查、邮件反馈及用户主动打开的外部内容可能联网；尚未完成所有场景的断网和流量审计，不承诺任何情况下完全离线或绝对安全。

线上账号、云同步、Windows 客户端和生成式问答/摘要尚未提供。本地资料库不能替代独立备份。

### 更新、版本与反馈

目前通过 [Releases](https://github.com/jayueseven/nearkeep-releases/releases) 手动更新，尚无自动更新。更新前正常退出、备份资料并保留原保存位置；所有历史版本的升级与回退组合尚未全面验证。

- `v1.0.0-preview.N`：1.0 的预览迭代；Preview 2 接续 Preview 1，旧 Tag 与包保留。
- `v1.0.0`：完成对应发布验收后的首个稳定版，不以预览版替代。
- `v1.0.1`：兼容性修复；`v1.1.0`：兼容的新功能；`v2.0.0`：不兼容变更，须说明迁移影响。
- 发布标题统一为 `Nearkeep 1.0.0 Preview 2` 等；每版提供独立包、说明与 SHA-256，不悄悄替换旧包。

反馈：[jayyueseven@gmail.com](mailto:jayyueseven@gmail.com)。请提供版本、系统和复现步骤，不发送私人文件、密码或令牌。

---

## English

Nearkeep is a local-first workspace for files worth keeping. Collect them with **Nicole**, your desktop companion, organize them in folders you control, and find them again by name, keywords or a description of their content.

This preview focuses on **Collect → Organize → Find → Use**. Real folder management and local semantic retrieval are available today. A broader personal AI space is a product direction—not a claim that chat, generated summaries, persistent contextual understanding or cloud sync are included.

### Download and requirements

**[Download Nearkeep 1.0.0 Preview 2](https://github.com/jayueseven/nearkeep-releases/releases/tag/v1.0.0-preview.2)** · Free, unnotarized macOS preview

| Item | Current support |
| --- | --- |
| Hardware | Apple Silicon Macs; no Intel or Windows package yet |
| System | Deployment target macOS 14; tested on macOS 27.0.1, not every intervening version |
| Package | ZIP containing Nearkeep.app and a local retrieval model, approximately 618.5 MB; additional extraction space required |
| Signing | Ad-hoc signed; no Developer ID signature or Apple notarization |
| Status | Public preview; broader compatibility and installation lifecycle validation remain in progress |

### What you can do

- Import files, folders or mixed batches through Upload, Library drag-and-drop or desktop Nicole. Nested and empty folders are preserved.
- Choose **Copy** to keep the original and save a separate copy, or **Move** to remove it from its original location after a successful safe save. Cancel before import begins.
- Create, rename and move real folders under your chosen storage location. Library folders correspond to Finder directories; favorites, pinned folders and sorting provide shortcuts.
- Search by name or keywords, with local Qwen semantic retrieval supplementing results when needed. Search history supports individual deletion.
- Locate results in the Library, inspect details, preview files or reveal the saved copy in Finder.
- Record a custom quick-search shortcut for use while Nearkeep is running. Chinese/English, light/dark themes and Nicole desktop preferences are supported.

### Install and get started

1. Download `Nearkeep-1.0.0-preview.2-macOS-arm64.zip` and `SHA256SUMS.txt` from the release page into one folder. Run:

   ```sh
   shasum -a 256 -c SHA256SUMS.txt
   ```

   The ZIP should report `OK`. This checks download integrity; it is not notarization or a comprehensive security audit.
2. Extract **Nearkeep.app** and move it to Applications. Quit an older version normally before replacing the app. Keep your Library storage folder.
3. macOS may block the first launch because this preview is not notarized. After checking the source and checksum, follow [Apple’s guidance](https://support.apple.com/en-us/102445) for that app. Do not disable system-wide protections. Stop and report any warning about malware, damage or corruption.
4. A **fresh profile** opens an empty Library and asks you to choose a dedicated storage folder. No developer location or sample files are prefilled. Cancelling does not import anything.
5. **Existing users** retain their Library and storage location. Downloading the app again does not reset local data. Avoid running multiple versions simultaneously.
6. Confirm Copy or Move when importing, then choose View to locate the imported items or Done to dismiss the receipt.

### Local retrieval and privacy boundaries

The package includes **Qwen3-Embedding-0.6B Q8_0**, used through a local llama.cpp runtime. This is a retrieval model, **not a conversational language model**. A question about late-payment liability can retrieve relevant payment clauses with an excerpt when their text is available. Relevance is not guaranteed; verify results against the original.

Text extraction supports text-layer PDFs and TXT, Markdown, CSV, TSV, JSON and LOG files. Full OCR for scanned PDFs and Office document body search are not provided. Large or long files and processing limits can produce partial coverage. A cold model start may take tens of seconds; ordinary search remains available if the model is busy or unavailable.

Current file management, indexing and model retrieval run locally without sending document text to cloud AI. OS security checks, email feedback and external content you choose to open may use the network. Comprehensive offline and traffic audits are not complete, so this is not a promise of absolute security or offline operation in every scenario.

Online accounts, cloud sync, a Windows client, and generative Q&A or summaries are not available. Keep an independent backup of important files.

### Updates, versions and feedback

Updates are manual through [Releases](https://github.com/jayueseven/nearkeep-releases/releases); automatic updates are not implemented. Quit normally and back up your data before updating. Keep the existing storage location. Every historical upgrade and downgrade combination has not been validated.

- `v1.0.0-preview.N` identifies successive previews. Preview 2 follows Preview 1; old tags and packages remain available.
- `v1.0.0` will identify the first stable release after its release checks are complete.
- Patch versions such as `v1.0.1` cover compatible fixes; minor versions such as `v1.1.0` add compatible features; major versions such as `v2.0.0` require explicit migration notes for incompatible changes.
- Titles follow `Nearkeep 1.0.0 Preview 2`. Each release has a distinct package, notes and SHA-256; published packages are not silently replaced.

Feedback: [jayyueseven@gmail.com](mailto:jayyueseven@gmail.com). Include the app version, OS and reproduction steps. Do not send private documents, passwords or tokens.

---

This repository contains product information, release notes and download packages only—not the private Nearkeep application source project. Runtime web resources, images and model files remain inspectable; no client application can promise complete protection against reverse engineering. Third-party license notices are retained in the app.

本仓库只提供产品说明、版本记录与下载包，不公开 Nearkeep 私有工程源码。运行所需的网页资源、图片和模型仍可被检查或逆向；应用保留第三方许可说明。
