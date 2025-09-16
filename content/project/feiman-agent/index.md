---
title: 'AI学生费曼学习系统'
summary: 基于"费曼学习法"理念设计的AI智能体，通过"解释、简化、比喻、追问"等方式，模拟一位"AI学生"与用户一同学习。
tags:
  - AI Agent
  - LangChain
  - WebSocket
  - React
  - 教育科技
date: '2025-06-01T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'AI费曼学习系统'
  focal_point: Smart

links:
  - icon: github
    icon_pack: brands
    name: 查看代码
    url: https://github.com/Frederick2313072/feiman_agent
  - type: code
    url: 'https://github.com/Frederick2313072/feiman_agent'
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
slides: ""
---

## 项目描述

一个基于"费曼学习法"理念设计的AI智能体。它不直接给出答案，而是通过"解释、简化、比喻、追问"等方式，模拟一位"AI学生"与用户一同学习。项目旨在验证状态化AI Agent在复杂、长程交互学习场景下的应用潜力。

## 技术架构

- **前端**：采用 React 负责前端开发，使用 MUI 构建了美观、响应式的用户界面
- **状态管理**：使用 Zustand 进行轻量级的全局状态管理
- **AI Agent**：基于 LangChain 设计并实现了支持长程记忆的 ReAct Agent
- **实时通信**：利用 WebSocket 实现Agent思考过程的实时流式输出

## 个人贡献

### 前端架构与开发
- 使用 MUI 构建了美观、响应式的用户界面
- 通过提取可复用的UI组件，将组件复用率提升至40%
- 使用 Zustand 进行轻量级的全局状态管理

### 状态化Agent后端
- 基于 LangChain 设计并实现了支持长程记忆的 ReAct Agent
- 通过封装 AgentExecutor 与 RunnableWithMessageHistory，确保了多轮交互中会话状态的一致性与持久化

### 实时交互接口
- 负责后端整体架构，利用 WebSocket 实现Agent思考过程的实时流式输出
- 将首个词响应时间 (TTFT) 控制在 500ms 以内，显著提升了用户交互体验

## 项目挑战与解决方案

### 挑战：多用户状态管理
如何在 WebSocket 通信中，轻量级地管理和隔离多用户的会话状态与长期记忆，避免高并发下的内存溢出。

**解决方案**：为每个WebSocket连接创建独立的 AgentExecutor 实例，并动态注入基于用户ID的会话历史。相比为每个用户维持独立进程的方式，内存占用减少了20%，实现了高效、低延迟的多用户状态管理。

## 技术收获

- 掌握了 LangChain 中 AgentExecutor 与 Runnable协议 在构建复杂AI Agent中的应用
- 熟悉了 WebSocket 实时通信与 RESTful 请求响应在AI应用中的混合应用场景与最佳实践
- 深入理解了AI Agent的状态管理和长程记忆机制
