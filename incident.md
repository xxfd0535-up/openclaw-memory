# incident.md - 故障知识库

## 记录格式

### 问题编号：INC-XXX

**日期：** YYYY-MM-DD
**问题现象：**
> 描述

**原因：**
> 根因

**修复动作：**
> 解决步骤

**验证方法：**
> 确认修复的方式

**教训：**
> 下次如何避免

---

## 已记录问题

### INC-001：jiangtao-zs agent工作区不完整

**日期：** 2026-05-29

**问题现象：**
> jiangtao-zs agent工作区缺少BOOTSTRAP.md、models.json和完整配置文件，无法正常使用飞书技能

**原因：**
> 创建agent工作区时未完整初始化，只有基础文件

**修复动作：**
1. 从xiajie-zs agent复制完整文件：AGENTS.md、BOOTSTRAP.md、SOUL.md
2. 初始化git仓库并配置用户信息
3. 复制models.json到agent工作区
4. 验证文件完整性

**验证方法：**
- 检查目录包含10个文件（AGENTS.md, BOOTSTRAP.md, SOUL.md等）
- git仓库已初始化
- models.json存在

**教训：**
- 创建新agent工作区时必须确保完整初始化
- 共享技能在 `/home/administrator/.openclaw/workspace/.agents/skills/`，但agent需要自己的配置文件

---

### INC-002：OpenClaw API端口18791不存在

**日期：** 2026-05-29

**问题现象：**
> 测试API时发现18791端口不存在，HTTP请求返回404

**原因：**
> OpenClaw gateway只监听18789（HTTP控制面板），API使用WebSocket而非HTTP REST

**修复动作：**
1. 通过 `openclaw gateway status` 确认端口配置
2. 验证18789是WebSocket端口
3. 理解架构：HTTP服务器用于Control UI，API通过WebSocket调用

**验证方法：**
- `ss -tlnp | grep openclaw` 显示只监听18789
- `openclaw gateway status` 显示 "port=18789 (service args)"

**教训：**
- OpenClaw API不是REST API，是通过WebSocket调用的
- 测试API需要使用WebSocket客户端，而非HTTP REST工具

---

## 待填充内容

（持续积累）