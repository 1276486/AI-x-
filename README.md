# 📈 AI 期货分析工具 x 策略回测系统

基于 Streamlit 的 AI 驱动期货市场分析、实时看盘与策略回测系统。集成了 DeepSeek 大语言模型，提供从开盘前深度分析到盘中实时验证的完整交易决策支持工作流。

## ✨ 主要功能

### 🔍 市场分析

多维度技术分析、AI 深度推理、多周期共振、分时图分析与相关品种联动。

![行情K线预览](<img width="2560" height="1600" alt="行情k线预览" src="https://github.com/user-attachments/assets/f42d1feb-b558-43a5-b8b9-099ed66afea8" />
)

- **多维度技术分析** — MACD、RSI、布林带、均线系统、成交量分析等 20+ 技术指标
- **AI 深度推理** — 调用 DeepSeek 大模型生成市场形势判断、趋势预测与操作建议
- **多周期共振分析** — 日线/周线/月线/分钟线多周期联动，识别周期共振信号
- **分时图分析** — 盘中分时走势形态识别与量价关系解读
- **相关品种联动** — 分组管理相关品种，联动分析产业链上下游

### 📊 实时看盘

实时行情 + AI 即时解读，交互式 K 线图表 + 自动刷新。

![实时看盘xAI分析](<img width="2560" height="1430" alt="实时看盘分析xAI分析" src="https://github.com/user-attachments/assets/dccaf22e-d2e2-44c3-bd4d-c1afedfea279" />
)

- **实时数据获取** — 通过 Tushare / AkShare 获取期货实时行情
- **AI 实时解读** — 对当前盘面进行即时分析，给出操作建议
- **专业 K 线图表** — 交互式 Plotly 图表，支持多副图指标叠加
- **自动刷新** — 可配置自动刷新间隔，实时追踪行情变化

### 🎯 策略跟踪

策略管理、持仓追踪与操作日志，全流程闭环。

| 策略管理 | K线持仓 |
|:---:|:---:|
| ![策略管理](<img width="2560" height="1430" alt="策略管理" src="https://github.com/user-attachments/assets/74b0f536-b2e2-469c-b2ed-0b904f44aec6" />
) | ![K线持仓](<img width="2560" height="1430" alt="k线持仓" src="https://github.com/user-attachments/assets/41bf24da-51aa-4787-87f6-ec4aa78611a7" />
) |

![策略日志](<img width="2560" height="1430" alt="策略日志" src="https://github.com/user-attachments/assets/9d61f045-9f93-43fd-ab41-39df66611929" />
)

- **策略采用与管理** — 一键采用 AI 建议的策略，记录入场/止损/目标价位
- **AI 持续跟踪** — 每次分析自动对比策略状态，给出持有/调整/止损建议
- **震荡容忍优化** — 智能区分正常震荡回调与趋势反转，避免频繁止损
- **策略持久化** — 本地 JSON 存储，重启后自动恢复

### 📝 报告验证（开盘前分析 → 盘中验证）
- **报告保存** — 开盘前生成的深度分析报告一键保存
- **盘中对比验证** — 实时看盘时自动加载盘前报告，AI 对比预测与实际走势
- **偏差识别** — 识别震荡 vs 趋势反转，给出修正建议
- **历史报告管理** — 按品种存储，支持回顾和分析总结

## 🏗️ 项目结构

```
main1/
├── test/                           # 🚀 主程序目录（最新版本 v2.5）
│   ├── TMv2.5.py                   #   主入口 — Streamlit 应用
│   ├── realtime_market.py          #   实时行情模块
│   ├── realtime_ai_analyzer.py     #   实时 AI 分析模块
│   ├── market_situation_analyzer.py #   市场形势判断引擎
│   ├── market_microstructure.py    #   市场微观结构分析
│   ├── intraday_chart.py           #   分时图分析
│   ├── multi_timeframe_analyzer.py #   多周期共振分析
│   ├── chart_layout.py             #   专业图表布局
│   ├── akshare_kline.py            #   AkShare K 线数据获取
│   ├── strategy_tracker.py         #   策略跟踪模块
│   ├── report_validator.py         #   报告验证模块
│   ├── correlated_futures_manager.py # 相关品种管理
│   └── main/                       #   历史版本存档
│
├── main/                           # 主程序（v2.4）
│   └── TMv2.4.py                   #   v2.4 版本主入口
│
├── desktop_futures_app/            # 🖥️ 桌面应用封装
│   ├── run_desktop.py              #   桌面应用入口
│   ├── app/                        #   桌面应用模块
│   │   ├── main_window.py          #     PyQt6 主窗口
│   │   ├── backend.py              #     Streamlit 后端管理
│   │   ├── settings_dialog.py      #     桌面设置界面
│   │   └── config.py               #     配置管理
│   ├── launch_desktop.bat          #   Windows 一键启动
│   └── build_desktop.ps1           #   PyInstaller 打包脚本
│
├── future-data-openclaw/           # 📡 数据提取工具
│   ├── data_extractor.py           #   Tushare 数据批量提取
│   └── skills/                     #   技能配置
│
├── new/                            # 🖱️ 鼠标宏工具（独立工具）
│   ├── 鼠标宏工具.pyw              #   可视化 GUI 版（推荐）
│   └── mouse_macro.py              #   命令行版
│
├── strategy_data/                  # 💾 策略数据存储（本地）
├── config.json                     # ⚙️ 全局配置文件
├── requirements.txt                # Python 依赖清单
└── .gitignore
```

## 🚀 快速开始

### 环境要求

- Python 3.11+
- Windows / macOS / Linux

### 安装

```bash
# 1. 克隆仓库
git clone https://github.com/your-username/ai-futures-analyzer.git
cd ai-futures-analyzer

# 2. 安装依赖
pip install -r requirements.txt
```

### 配置

在项目根目录创建 `config.json`：

```json
{
  "ai_token": "your-deepseek-api-key",
  "tushare_token": "your-tushare-token",
  "selected_model": "deepseek-v4-pro",
  "system_name": "AI期货分析工具 x 策略回测系统",
  "custom_prompts": []
}
```

> ⚠️ **安全提醒：** 请勿将包含真实 API Key 的 `config.json` 提交到公开仓库！建议将其加入 `.gitignore`。

### 运行

**方式一：Web 应用（推荐）**

```bash
streamlit run test/TMv2.5.py
```

**方式二：桌面应用**

```bash
# 安装桌面依赖
pip install PyQt6 PyQt6-WebEngine

# 启动桌面版
python desktop_futures_app/run_desktop.py
```

**方式三：Windows 一键启动**

双击 `run_no_test_streamlit_app.bat`（启动 v2.5）或 `1.bat`（启动 v2.4）。

## 📋 完整工作流

```
开盘前（08:30）                    盘中（09:30+）                     盘后
─────────────────                  ─────────────────                 ─────────
┌──────────────┐                  ┌──────────────┐                ┌──────────┐
│ 1. 市场分析   │                  │ 4. 实时看盘   │                │ 7. 总结   │
│  - 选品种     │     ──────>      │  - AI 分析    │    ──────>     │  - 回顾   │
│  - AI 深度分析 │                  │  - 报告验证   │                │  - 改进   │
│  - 多周期共振  │                  │  - 策略跟踪   │                └──────────┘
│ 2. 保存报告   │                  │ 5. 震荡识别   │
│ 3. 制定计划   │                  │ 6. 修正建议   │
└──────────────┘                  └──────────────┘
```

## 🛠️ 技术栈

| 类别 | 技术 |
|------|------|
| **Web 框架** | Streamlit |
| **数据分析** | Pandas, NumPy, SciPy, StatsModels |
| **可视化** | Plotly, Matplotlib, mplfinance, Seaborn |
| **AI 模型** | DeepSeek (via OpenAI-compatible API) |
| **数据源** | Tushare Pro, AkShare |
| **桌面封装** | PyQt6 + PyQt6-WebEngine |
| **打包** | PyInstaller |

## 📦 其他工具

### 🖱️ 鼠标宏工具 (`new/`)

一个独立的鼠标宏录制/回放工具，仿罗技鼠标宏体验：

- **可视化 GUI 版** — `python 鼠标宏工具.pyw`（无命令行窗口）
- **命令行版** — `python mouse_macro.py`
- 录制鼠标操作（移动、点击、滚轮）
- 循环播放，支持指定次数或无限循环
- 一键急停（ESC / 鼠标中键），永不卡死

### 📡 数据提取工具 (`future-data-openclaw/`)

批量提取期货历史数据，支持通过 Tushare API 获取全市场期货合约的日线数据。

## ⚠️ 注意事项

- **AI 是辅助工具，不是绝对真理** — AI 分析结果仅供参考，请结合自己的判断做出交易决策
- **API 配额** — Tushare 和 DeepSeek API 均有调用频率限制，请注意使用频率
- **数据延迟** — 实时数据存在一定延迟，不建议用于高频交易
- **风险控制** — 期货交易具有高风险，请严格执行止损纪律
- **安全性** — 请妥善保管 API Key，不要提交到公开仓库

## 📄 License

MIT License — 仅供学习和研究使用。

---

**⚠️ 免责声明：** 本工具仅供学习和研究目的，不构成任何投资建议。期货交易风险极高，过去的表现不代表未来的结果。使用本工具进行实盘交易的任何盈亏均由使用者自行承担。
