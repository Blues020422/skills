# Destin Skills

OpenCode 技能库，存放可复用的 AI 技能模块。

## 可用技能

### BDC-PRD

**金融交易系统需求规格说明书标准化撰写**

- 全模块细粒度 + 固定版式
- 每个功能点强制包含五大核心板块（功能说明、业务规则、界面展示、输入项、输出项）
- 可直接指导开发、测试与项目落地

**触发关键词**：`BDC-PRD`、`PRD`、`需求规格说明书`、`金融交易系统`、`信用拆借`、`额度管理`、`风控管理`

**依赖**：`docx` skill

---

## 安装方法

### 方法一：手动复制

1. 克隆本仓库：
   ```bash
   git clone https://github.com/jinwandalaohu622-cloud/Destin-Skills.git
   ```

2. 复制所需技能到 OpenCode skills 目录：

   **Windows (PowerShell)**：
   ```powershell
   Copy-Item -Recurse -Force ".\Destin-Skills\skills\BDC-PRD" "$env:USERPROFILE\.config\opencode\skills\"
   ```

   **macOS / Linux**：
   ```bash
   cp -r Destin-Skills/skills/BDC-PRD ~/.config/opencode/skills/
   ```

### 方法二：一键安装脚本

**Windows (PowerShell)**：
```powershell
# 下载并安装 BDC-PRD skill
$skillDir = "$env:USERPROFILE\.config\opencode\skills\BDC-PRD"
$tempZip = "$env:TEMP\Destin-Skills.zip"

# 下载仓库
Invoke-WebRequest -Uri "https://github.com/jinwandalaohu622-cloud/Destin-Skills/archive/refs/heads/main.zip" -OutFile $tempZip

# 解压并复制
Expand-Archive -Path $tempZip -DestinationPath "$env:TEMP\Destin-Skills-temp" -Force
New-Item -ItemType Directory -Force -Path $skillDir | Out-Null
Copy-Item -Recurse -Force "$env:TEMP\Destin-Skills-temp\Destin-Skills-main\skills\BDC-PRD\*" $skillDir

# 清理临时文件
Remove-Item -Recurse -Force "$env:TEMP\Destin-Skills-temp"
Remove-Item -Force $tempZip

Write-Host "BDC-PRD skill installed successfully!" -ForegroundColor Green
```

**macOS / Linux**：
```bash
# 下载并安装 BDC-PRD skill
curl -L https://github.com/jinwandalaohu622-cloud/Destin-Skills/archive/refs/heads/main.tar.gz | tar xz -C /tmp
mkdir -p ~/.config/opencode/skills/BDC-PRD
cp -r /tmp/Destin-Skills-main/skills/BDC-PRD/* ~/.config/opencode/skills/BDC-PRD/
rm -rf /tmp/Destin-Skills-main
echo "BDC-PRD skill installed successfully!"
```

---

## 使用方法

安装完成后，在 OpenCode 中提及相关关键词即可自动触发技能。

**示例**：
- "帮我生成一个信用拆借的PRD"
- "写一个额度管理的需求规格说明书"

---

## 技能贡献

欢迎提交新的技能或改进现有技能：

1. Fork 本仓库
2. 在 `skills/` 目录下创建新技能文件夹
3. 添加 `SKILL.md` 文件
4. 提交 Pull Request

---

## 技能文件结构

```
skills/
└── [skill-name]/
    └── SKILL.md          # 技能定义文件（必需）
```

### SKILL.md 格式

```markdown
---
name: 技能名称
description: "技能描述"
triggers: 触发关键词
dependencies: 依赖的其他技能（可选）
---

# 技能详细说明
...
```

---

## License

MIT License
