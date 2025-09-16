---
title: 'NKUWiki 知识图谱构建 (LLM驱动校园问答应用)'
summary: 基于RAG检索增强生成的南开大学校园知识共享平台，处理数据量10GB+，构建50万+token知识库，问答准确率达到82%。
tags:
  - 数据采集
  - RAG系统
  - 知识图谱
  - 反爬虫技术
  - ETL
date: '2024-10-01T00:00:00Z'

# Optional external URL for project (replaces project detail page).
external_link: ''

# Featured image
# To use, add an image named `featured.jpg/png` to your page's folder.
image:
  caption: 'NKUWiki 系统架构'
  focal_point: Smart

links:
  - icon: github
    icon_pack: brands
    name: 查看代码
    url: https://github.com/Frederick2313072/nkuwiki
  - type: code
    url: 'https://github.com/Frederick2313072/nkuwiki'
url_pdf: ''
url_slides: ''
url_video: ''

# Slides (optional).
slides: ""
---

## 项目描述

一个基于RAG检索增强生成的南开大学校园知识共享平台，采用"开源·共治·普惠"理念构建南开知识共同体。项目处理数据量10GB+，覆盖小红书、知乎、校园集市3000+帖子，数据清洗准确率96%，结构化处理效率提升60%。

## 技术成果

- 基于LangChain优化RAG问答，构建50万+token知识库
- HuggingFace嵌入模型检索召回率91%
- 问答响应时间优化至1.2s，准确率达到82%
- 爬虫稳定运行率达99.5%，单日数据采集量突破10万条

## 个人贡献

### 多路爬虫系统架构设计
独立设计并实现了支持异构数据源的分布式爬虫系统，采用Playwright + Selenium双引擎混合架构，覆盖现代SPA与传统网页场景，Playwright处理复杂DOM性能提升40%。

### 逆向工程与反反爬技术
- 针对小红书、知乎、校园集市等平台实施深度逆向分析
- 破解API签名算法（HMAC-MD5、时间戳验证）
- 设计JavaScript反检测脚本，覆盖WebDriver隐藏、浏览器指纹伪造、Canvas指纹混淆等30+检测点
- 成功绕过Cloudflare、阿里云盾等WAF防护

### 安全防护与对抗策略
- 实现动态User-Agent轮换、IP代理池管理、请求频率控制等反反爬机制
- 通过Browserless集群实现浏览器指纹混淆
- 设计Cookie管理与会话保持策略

### ETL数据处理管道
设计异步数据处理流程，集成Qdrant向量数据库、Elasticsearch全文索引、MySQL关系存储，实现增量数据同步与索引构建，数据处理延迟控制在100ms以内。

## 核心技术突破

### 校园集市API逆向
通过流量分析发现X-Sc-Ah签名机制，逆向JavaScript加密算法，实现动态签名生成（university_m_td_secret_key的MD5哈希），突破API访问限制，数据获取成功率提升至95%。

### 知乎反爬对抗
分析z_c0 cookie认证机制，实现基于时间戳的动态请求头构造，通过WebGL渲染器信息伪造、音频上下文混淆等技术绕过浏览器指纹检测。

### 小红书数据采集
破解小红书搜索API的参数加密，实现批量内容抓取，通过请求去重与异常重试机制保证数据完整性。

### 安全合规设计
遵循robots.txt协议，实现请求频率自适应控制，设计数据脱敏与隐私保护机制，确保合规采集。
