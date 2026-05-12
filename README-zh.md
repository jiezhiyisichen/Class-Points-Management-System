
---

**README-zh.md** (Chinese)

# 班级积分管理系统（Web版）

[![Python 版本](https://img.shields.io/badge/python-3.8%2B-blue)](https://www.python.org/downloads/)
[![Flask](https://img.shields.io/badge/Flask-3.0.0-green)](https://flask.palletsprojects.com/)
[![许可证](https://img.shields.io/badge/license-MIT-lightgrey)](LICENSE)

> 为中小学教师设计的班级积分管理 Web 应用，支持多用户数据隔离、多维排名、基于累计正分的等级系统、数据导入导出、操作日志等功能。

👉 [English Version](README.md)

## ✨ 功能特点

### 👥 用户系统
- 用户注册 / 登录 – 每位教师独立管理自己的班级数据。
- 角色区分：普通用户和管理员（管理员可管理用户）。

### 🧑‍🎓 学生管理
- 增删改查学生（姓名、学号、正分/负分）。
- 每个学生可添加注释，支持删除注释。
- 数据导入导出（JSON 格式，保留注释信息）。

### 🎯 积分与等级系统
- **积分调整**：增加正分/负分、支付（扣除正分）。
- **等级系统** – 基于 `accrued_exp`（累计获得的正分）。
  - 每获得 10 正分自动升 1 级。
  - 清零操作不影响累计经验与等级。

### 📊 排名与可视化
- 多维度排名：总排名、正分排名、负分榜、按学号排序。
- 总排名前三名显示金银铜牌图标。
- 积分分布柱状图（滚动显示，同时展示 5 名学生）。
- 班级统计：总人数、正分人数、负分人数、平均总分。

### 📢 公告系统
- **全局公告**（管理员可编辑 Markdown，右下角按钮仅展示）。
- **班级公告**（支持 Markdown，每个班级独立编辑）。

### 📝 日志与安全
- 完整操作日志 – 记录所有积分变动和学生修改。
- 支持导出日志 / 清空日志。
- 锁定/解锁机制 – 防止公共大屏上的误操作。

### 🎲 其他实用功能
- 随机抽取一名学生。
- 响应式设计 – 完美适配 4K 显示器，也支持移动设备。

## 🛠️ 技术栈

| 后端 | 前端 | 数据存储 |
|------|------|----------|
| Python 3.8+<br>Flask 3.0.0 | HTML5 / CSS3 / JavaScript<br>Tailwind CSS<br>Chart.js<br>Font Awesome | JSON 文件（无需数据库） |

## 📦 安装说明

### 环境要求
- Python 3.8 或更高版本
- pip（Python 包管理器）

### 安装步骤
1. **克隆仓库**  
   ```bash
   git clone https://github.com/yourusername/class-points-system.git
   cd class-points-system
   ```

2. **安装依赖**  
   ```bash
   pip install -r requirements.txt
   ```

   *示例 `requirements.txt` 内容：*
   ```
   Flask==3.0.0
   ```

3. **运行程序**  
   ```bash
   python app.py
   ```

4. **访问系统**  
   打开浏览器，访问 `http://localhost:5000`

### （可选）内网穿透
使用 `ngrok` 或 `frp` 将本地服务暴露到公网：
```bash
ngrok http 5000
```

## 🚀 使用指南

### 首次运行？
- 注册一个新账号 – 第一个注册的用户为**普通用户**。
- 如需管理员权限，请联系现有管理员（管理员可在后台提升其他用户）或使用默认超级管理员 `ysc`（密码：`admin123` – **首次登录后请立即修改**）。

### 核心操作说明

| 操作 | 说明 |
|------|------|
| **添加学生** | 填写姓名、学号、初始正/负分 |
| **积分调整** | 增加正分/负分，或支付（扣正分） – 等级会自动更新 |
| **查看排名** | 点击标签页切换总分/正分/负分/学号排名 |
| **学生注释** | 点击学生行旁的注释图标，可添加或删除注释 |
| **公告** | 右下角浮动按钮展示全局公告；班级公告在设置页编辑 |
| **导入/导出** | 导出全部学生+注释为 JSON，也可导入之前导出的文件 |
| **日志** | 在日志面板查看、导出或清空操作记录 |
| **锁定/解锁** | 开启后禁止所有修改操作，适合在公共大屏展示时使用 |

## 📁 数据存储
- 所有数据保存在 `data/` 文件夹下的 JSON 文件中：
  - `students.json` – 学生列表及积分
  - `users.json` – 用户账号、角色
  - `logs.json` – 操作日志
  - `config.json` – 系统设置（公告、锁定状态等）
- 备份整个 `data/` 文件夹即可保存全部数据。

## 🔧 配置修改
- 默认端口：`5000` – 可在 `app.py` 中修改
- 积分调整**无需专用密码** – 已改为登录会话认证
- 等级升级阈值（每 10 正分一级）可在源码中自定义


## 🗺️ 未来计划
- [ ] CSV 导入/导出
- [ ] 可自定义等级计算公式
- [ ] 学生端（仅查看自己的积分）
- [ ] Docker 一键部署

## 🤝 贡献
欢迎提交 Issue 和 Pull Request！  
重大变更请先开 Issue 讨论。

## 📄 许可证
[MIT](LICENSE) © 班级积分开发团队

## 🙏 致谢
- [Flask](https://flask.palletsprojects.com/)
- [Tailwind CSS](https://tailwindcss.com/)
- [Chart.js](https://www.chartjs.org/)
- [Font Awesome](https://fontawesome.com/)
- [Marked.js](https://marked.js.org/)

---

**开始轻松管理班级积分吧！** ⭐
```
