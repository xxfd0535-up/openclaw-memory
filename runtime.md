# runtime.md - 实际运行结构

## 目录结构

```
WSL: /home/administrator/
├── .openclaw/              # OpenClaw 主目录
│   ├── openclaw.json      # 配置文件
│   ├── agents/            # Agent 工作区
│   │   ├── xiajie-zs/
│   │   ├── jiangtao-zs/
│   │   └── main/
│   ├── workspace/         # 默认工作区
│   └── logs/              # 日志目录
├── .npm-global/           # 全局 npm 包
│   └── bin/openclaw       # OpenClaw CLI
└── temp/                  # 临时文件

Windows: C:\Users\Administrator\
├── .openclaw-memory/      # 运维记忆系统 (Git已同步)
├── temp_openclaw.json    # 配置备份
└── .wslconfig            # WSL 配置
```

---

## 进程信息

- 进程名：openclaw
- PID：3125 (当前运行)
- 端口：18789 (HTTP Control UI)
- API端口：**18791 (当前未监听 - 待排查)**
- 运行方式：后台进程
- 启动命令：`cd /home/administrator && .npm-global/bin/openclaw gateway run`

---

## 已安装工具

### 飞书 CLI
- 版本：1.0.43
- 安装命令：`npm install -g @larksuite/cli`
- 配置状态：✅ 已配置 App ID
- App ID：cli_aa92cb078838dbcf
- 用途：让AI直接操作飞书

---

## 网络布局

- WSL IP：172.18.233.207
- localhostForwarding：启用
- DNS：通过 Windows 解析

---

## 当前状态

### 已确认
- Gateway HTTP服务就绪 (18789)
- 3个Feishu WebSocket已连接
- 配置已正确加载
- 飞书CLI已安装并配置

### 待排查
- API端点 (18791) 未监听
- HTTP API请求返回404
- 可能是配置问题或端口配置变更

---

## Git仓库

- 远程：https://github.com/xxfd0535-up/openclaw-memory
- 本地：C:\Users\Administrator\.openclaw-memory
- 状态：已同步