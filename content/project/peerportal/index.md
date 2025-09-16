---
title: 'PeerPortal - 去中介化留学双边信息平台'
summary: 集成了智能对话、实时消息、论坛交流、文件管理和精准匹配的去中介化留学双边信息平台，采用现代化全栈架构。
tags:
  - 全栈开发
  - Next.js
  - FastAPI
  - PostgreSQL
  - WebSocket
date: '2025-07-01T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'PeerPortal 平台架构'
  focal_point: Smart

links:
  - icon: github
    icon_pack: brands
    name: 查看代码
    url: https://github.com/PeerPortal/web
  - type: code
    url: 'https://github.com/PeerPortal/web'
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
#   Associate this project with Markdown slides.
#   Simply enter your slide deck's filename without extension.
#   E.g. `slides = "example-slides"` references `content/slides/example-slides.md`.
#   Otherwise, set `slides = ""`.
slides: ""
---

## 项目描述

一个集成了智能对话、实时消息、论坛交流、文件管理和精准匹配的去中介化留学双边信息平台。项目采用现代化全栈架构，为申请者和引路人提供全方位、个性化的留学申请指导服务，打破传统信息壁垒。

## 技术架构

- **前端**：基于 Next.js 15 + React 19 + TypeScript 构建现代化SPA，采用 Tailwind CSS + Radix UI 组件库实现响应式设计，使用 Zustand 进行状态管理
- **后端**：采用 FastAPI + Python 构建高性能异步API服务，集成 Supabase(PostgreSQL) 作为主数据库，支持 WebSocket 实时通信
- **基础设施**：Docker 容器化部署，支持文件上传存储、用户认证、数据库优化等企业级功能

## 个人贡献

- **全栈系统架构设计**：独立负责整个系统的前后端架构设计，构建了包含用户管理、论坛系统、实时消息、文件上传、智能匹配等9个核心业务模块的完整平台
- **前端开发**：使用 Next.js 15 App Router 构建现代化前端应用，实现了用户认证、个人资料管理、论坛交流、实时聊天等核心功能页面，组件复用率达到60%
- **后端API开发**：基于 FastAPI 构建了包含50+个API端点的完整RESTful服务，涵盖用户管理、论坛CRUD、消息系统、文件上传等核心功能，API响应时间控制在100ms以内
- **数据库设计与优化**：设计了包含21个数据表的完整数据库架构，优化了复杂查询性能，通过索引策略和查询优化将数据库响应时间提升30%
- **实时通信系统**：基于 WebSocket 实现了导师-学生一对一实时聊天功能，支持消息状态管理、在线状态显示，消息延迟控制在50ms以内

## 项目挑战与解决方案

### 挑战：复杂权限系统设计
如何设计一个支持多种用户角色（学生、导师、管理员）的复杂权限系统，确保数据安全和用户隐私。

**解决方案**：基于JWT实现无状态认证，设计了角色-权限-资源的三层权限模型，通过中间件实现细粒度的API权限控制，确保不同角色只能访问相应的数据和功能。

### 挑战：高并发实时消息系统
如何在高并发场景下保证实时消息系统的稳定性和性能。

**解决方案**：采用异步编程模式，实现了连接池管理和消息队列机制，通过负载均衡和连接复用，支持1000+并发连接，消息投递成功率达99.9%。
