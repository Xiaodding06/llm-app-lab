# llm-app-lab

大模型应用开发求职主线的**代码仓库**，2026-11-19（W1 Day 6）建立。

## 这个仓库是干什么的

从 W3 开始，所有跟求职主线相关的代码都放这里：

| 阶段 | 内容 |
|---|---|
| W3 | FastAPI 图书管理 API |
| W5 | 调用 DeepSeek / 通义 API，`.env` 管理密钥 |
| W7-W12 | 第一个 RAG 项目、Agent 实验 |
| W13+ | 简历上可讲的项目逐步在这里长出来 |

与课程作业项目 `D:\学习资料\pythonProject`（MNIST 手写数字识别）**完全分开**——
那属于课程，不进这条线，也不动它。

## 环境

- 系统 Python 3.9.2 只当"裸机工具"，本项目用**独立 venv**：`.venv/`（不进 git）
- 依赖清单：`requirements.txt`
- 当前已装：`requests`（调 HTTP API）、`python-dotenv`（读 `.env` 里的 key）
  其余 4 行是它俩的间接依赖，pip 自动带进来的

### 换台机器还原环境

```bash
cd /d/llm-app-lab
"C:/Users/小丁/AppData/Local/Programs/Python/Python39/python.exe" -m venv .venv
./.venv/Scripts/python.exe -m pip install -r requirements.txt -i https://pypi.tuna.tsinghua.edu.cn/simple
```

### 装了新包之后更新清单

```bash
./.venv/Scripts/python.exe -m pip freeze > requirements.txt
```

## 约定

1. 一个项目一个 venv，装包一律指定本项目 venv 的 pip（系统 Python 装了不算数）
2. `.env` 放 API key，权限 600，**绝不进 git**（已在 .gitignore 里挡住）
3. 装包走清华源：`-i https://pypi.tuna.tsinghua.edu.cn/simple`
4. commit 消息写清楚"改了什么、为什么"，用 `feat / fix / docs / refactor / test` 前缀
