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
├── .openclaw-memory/      # 运维记忆系统
├── temp_openclaw.json    # 配置备份
└── .wslconfig            # WSL 配置
```

---

## 进程信息

- 进程名：openclaw
- 端口：18789 (HTTP), 18791 (API)
- 运行方式：后台进程
- 启动命令：`cd /home/administrator && .npm-global/bin/openclaw gateway run`

---

## 网络布局

- WSL IP：172.18.233.207
- localhostForwarding：启用
- DNS：通过 Windows 解析

---

## 待填充内容

（根据实际环境持续更新）