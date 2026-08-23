# VeroRun Minimal Edition — Mini-Program Platform

**VeroRun 最小化版（小程序平台）** —— 激活后解锁 6 个内置插件。

本仓库为最小化版落地页，由 `sync-to-minipro` CI 流水线维护，**仅包含本说明文档**（不含任何代码）。最小化版内核从 `verorun-standard` 获取，插件通过内置插件商店安装。请勿手动推送本仓库。

---

## English

## Overview

The Minimal Edition keeps a single shared core with the Standard and Education editions, but activates only the built-in plugins needed to run the mini-program platform — installed on demand from the built-in plugin store, **never bundled in the distribution**.

Bundled plugin entitlements (MiniPro):

- `mini_app_builder` — natural-language & template mini-program generation, multi-platform output, publishing, developer-credential management
- `oauth_config` — OAuth login / token management
- `visitor_profile` — visitor analytics and profile dashboards
- `im_gateway` — message gateway for runtime chat
- `health_check` — service health inspection
- `_base` — shared base dependency

## Core Capabilities

- **Generate a mini-program from plain language** — `POST /admin/site-builder/mini-app/generate`, multi-round LLM pipeline (Parse → Brand → per-page), local knowledge injected via RAG.
- **Multi-platform output** — WeChat / Douyin / LINE / Telegram / WhatsApp from one project.
- **Publishing** — WeChat (miniprogram-ci) & Douyin upload / audit submit / status polling.
- **Local knowledge base (RAG)** — hybrid pgvector + pg_trgm + RRF, `scope='user'` isolated from admin knowledge.

## Getting Started

1. Deploy the core from `verorun-standard`.
2. Activate the MiniPro edition in the admin console.
3. Install the unlocked plugins from **Admin → Plugins → Store**.

---

## 中文

## 概述

最小化版与标准版、教育版共享同一内核，仅激活运行小程序平台所需的内置插件 —— 插件通过内置插件商店按需安装，**任何发行版均不捆绑插件**。

最小化版内置插件授权清单：

- `mini_app_builder`（小程序构建器：自然语言 & 模板生成、多平台产出、发布、开发者凭证管理）
- `oauth_config`（第三方登录）、`visitor_profile`（访客画像）、`im_gateway`（消息网关）、`health_check`（健康检查）、`_base`（基础依赖）

## 核心能力

- **自然语言生成小程序**：`POST /admin/site-builder/mini-app/generate`，多轮 LLM 流水线（Parse → Brand → 每页），RAG 注入本地知识。
- **多平台产出**：微信 / 抖音 / LINE / Telegram / WhatsApp 一套源码多端生成。
- **发布链路**：微信（miniprogram-ci）与抖音上传、提审提交、状态轮询。
- **本地知识库（RAG）**：混合检索（pgvector + pg_trgm + RRF），`scope='user'` 与管理端知识隔离。

## 快速开始

1. 从 `verorun-standard` 部署内核。
2. 在管理后台激活最小化版。
3. 在 **管理后台 → 插件 → 商店** 安装已解锁的插件。
