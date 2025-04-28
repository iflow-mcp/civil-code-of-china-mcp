# 民法典 MCP Server (Civil Code MCP Server)

## English Description

### Overview

The Civil Code MCP Server is a Model Context Protocol (MCP) server that provides structured access to the content and organization of the Chinese Civil Code. This implementation allows AI models to efficiently retrieve, navigate, and search through the Civil Code's hierarchical structure and specific articles.

### Features

- **Hierarchical Navigation**: Browse through the Civil Code's structure from the top level (分编) down to specific articles (条)
- **Structured Data**: Access the logical structure of the Civil Code, organized by sections, chapters, and articles
- **Content Retrieval**: Fetch the precise content of any specific article by its full path

### Technical Implementation

The server is built using the Model Context Protocol SDK and implements two main tools:

1. **get_structure**: Retrieve the child nodes of a specified parent node in the Civil Code hierarchy
   - Input: Optional `parent_node` (string) - The path of the parent node
   - Output: A JSON object containing the list of child nodes

2. **get_article_content**: Retrieve the content of a specific article
   - Input: `article_path` (string) - The full path to the article
   - Output: The text content of the specified article

### Technical Architecture

The server maintains two key data structures:
- `StructData`: A mapping from node paths to their child nodes
- `ContentData`: A mapping from article paths to their textual content

### Usage

The server runs on standard input/output and can be connected to any MCP-compatible client. It provides a structured interface for accessing the Chinese Civil Code, enabling AI models to reference specific legal articles and navigate through the code's structure.

#### Command Line Usage

You can start the server directly using npx:

```bash
npx -y @jjfather/civil-code-of-china-mcp
```

This command will download and run the MCP server without needing to install it globally.

---

## 中文说明

### 概述

民法典 MCP 服务器是一个基于模型上下文协议(Model Context Protocol)的服务器，提供对中国民法典内容和结构的结构化访问。该实现允许AI模型高效地检索、导航和搜索民法典的层次结构和具体条款。

### 功能特点

- **层次化导航**：从顶层（分编）浏览到具体条款（条）的民法典结构
- **结构化数据**：访问民法典的逻辑结构，按编、章、节、条组织
- **内容检索**：通过完整路径获取任何特定条款的精确内容

### 技术实现

服务器使用Model Context Protocol SDK构建，实现了两个主要工具：

1. **get_structure**：获取民法典层次结构中指定父节点的子节点
   - 输入：可选的`parent_node`（字符串）- 父节点的路径
   - 输出：包含子节点列表的JSON对象

2. **get_article_content**：获取特定条款的内容
   - 输入：`article_path`（字符串）- 条款的完整路径
   - 输出：指定条款的文本内容

### 技术架构

服务器维护两个关键数据结构：
- `StructData`：从节点路径到其子节点的映射
- `ContentData`：从条款路径到其文本内容的映射

### 使用方法

服务器运行在标准输入/输出上，可以连接到任何兼容MCP的客户端。它为访问中国民法典提供了结构化的接口，使AI模型能够引用特定的法律条款并浏览民法典的结构。

#### 命令行使用方法

您可以使用npx直接启动服务器：

```bash
npx -y @jjfather/civil-code-of-china-mcp
```

这个命令会下载并运行MCP服务器，无需全局安装。 