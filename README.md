# 2024-2026年全球 AI 芯片产业深度调研与行业研究报告项目

本项目是一份详尽、专业且经过深度交叉验证的全球 AI 芯片产业（2024-2026年）研究白皮书。报告内容覆盖了全球高性能 GPU、定制化 ASIC 算力先锋以及中国本土代际突围势力等 14 家核心科技厂商，配备了完整的原始关系型数据库（CSV 格式）、可视化架构/数据图表、地缘博弈下的规格冲突深度论证，以及未来五年的技术趋势预测。

## 项目目录结构

```
AI-Chip-Industry-Research-2024-2026/
├── README.md                      # 项目说明书与指引（本文件）
├── sources/                       # 引用数据与交叉验证冲突报告
│   ├── references.bib             # 标准 BibTeX 学术引用数据库
│   ├── reference_list.csv         # 扁平化文献引用清单（附带URL和详细描述）
│   └── source_conflicts.md        # 地缘冲突及多渠道规格参数矛盾的深度解析报告
├── database/                      # 核心原始关系数据库（CSV 文件）
│   ├── companies.csv              # 14 家研究厂商的基本面数据
│   ├── chips.csv                  # 36 颗核心 AI 芯片的技术规格参数
│   ├── performance.csv            # 芯片的各精度（FP16/BF16/FP8/FP4/INT8）浮点稠密/稀疏算力
│   ├── customers.csv              # 典型客户、部署案例与应用规模
│   ├── process_nodes.csv          # 晶圆制造代工节点的物理密度及产业瓶颈
│   ├── timeline.csv               # 2021-2026年芯片发布/流片/政策限制等关键历史时间线
│   └── conflict_records.csv       # 系统性记录冲突数据的具体参数及官方/民间原因解释
├── charts/                        # 高清矢量图表（SVG 格式）
│   ├── fp16_compare.svg           # 主流芯片 FP16/BF16 稠密算力横向对比柱状图
│   ├── memory_compare.svg         # 显存容量 (GB) 与显存物理带宽 (TB/s) 的双维度对比图
│   ├── power_compare.svg          # 芯片物理功耗（TDP 瓦特）柱状对比图
│   ├── market_share.svg           # 全球数据中心 AI 算力市场份额估算环形图
│   ├── timeline.svg               # 2021-2026年全球 AI 芯片发展重要事件时间线图
│   ├── roadmap.svg                # 2026-2031年未来五年先进工艺、存储与封装技术路线图
│   ├── ecosystem.svg              # 算力生态四层技术架构（硬件、编译器、框架、部署服务）
│   └── supply_chain.svg           # 半导体产业链全景链条图（EDA/IP、HBM、代工、封测、云服务）
├── report/                        # 深度行业研究报告交付件
│   ├── report.md                  # 详实的长篇 Markdown 行业报告（不少于1.5万字）
│   ├── report.docx                # 带有精美排版和标准样式的 MS Word 格式报告
│   ├── report.pdf                 # 配备 Noto Sans 中文字体的标准 A4 PDF 报告
│   └── appendix.pdf               # 附带技术名词及核心指标解释的附录 PDF 文档
└── assets/                        # 额外资产（预留）
    ├── logo/
    └── figures/
```

---

## 1. 核心研究对象 (14 家领军厂商)
本项目对以下 14 家全球 AI 半导体中坚力量进行了无死角的公开数据采集与多重验证：
1.  **NVIDIA (英伟达)：** 垄断性生态的定义者（Hopper 与 Blackwell 架构）。
2.  **AMD (超威半导体)：** 硬件参数的极限挑战者（MI300/MI325/MI350系列）。
3.  **Intel (英特尔)：** 专用 ASIC 性价比捍卫者（Gaudi 3 芯片）。
4.  **Google (谷歌)：** 自研 ASIC 历史最悠久的云巨头（TPU v6e/v7）。
5.  **Amazon (亚马逊 AWS)：** 弹性算力低成本底座（Trainium 2/3, Inferentia 2）。
6.  **Microsoft (微软)：** 垂直支撑 OpenAI 推理的幕后新势力（Maia 200）。
7.  **Meta：** 高能效比、适配自身推荐与排序广告算法的 MTIA v2 芯片。
8.  **Tesla (特斯拉)：** 数据中心 Dojo D1 与边缘自动驾驶 FSD / 机器人 AI5 核心。
9.  **Groq：** 大规模板载 SRAM 极速时延推理 LPU 架构。
10. **Cerebras Systems：** 极限晶圆级巨型单芯片 WSE-3。
11. **华为 (Huawei)：** 国产突围领头羊，以昇腾 910B/910C 打破 CUDA 独霸。
12. **寒武纪 (Cambricon)：** 拥有独立 MLU 开发体系与国产代工突围的先锋。
13. **壁仞科技 (Biren)：** 高性能通用算力 GPU 的本土代表（BR100系列）。
14. **沐曦集成电路 (Muxi)：** 自研通用 GPU 架构、具备良好 CUDA 转译能力的曦云/曦思系列。

---

## 2. 关系型数据库结构 (CSV 模式)
在 `database/` 目录下，我们设计了严格规范、互相引用的关系型表格：
*   `companies.csv`：记录厂商 ID、起源国、主攻方向、市值量级、受制裁状态及技术优势。
*   `chips.csv`：涵盖 36 款芯片的架构代号、流片工艺制程、显存容量(GB)、显存介质（HBM3e/LPDDR5/SRAM）、物理带宽、功耗瓦特及流片时间。
*   `performance.csv`：全面收录各芯片在 FP16, BF16, FP8, FP4, INT8 精度下的稠密/稀疏（Sparsity）实测算力（TFLOPS / TOPS）。
*   `customers.csv`：展现大客户名录、部署规模与典型 AI 应用场景（如大模型训练、在线高吞吐推理）。
*   `process_nodes.csv`：对比台积电（3nm-7nm）、三星（4nm-2nm）、中芯国际（7nm N+2）及物理晶体管密度和代工瓶颈。
*   `timeline.csv`：精确串联近五年（2021-2026年）高端芯片重大节点。
*   `conflict_records.csv`：汇总 6 条最具代表性的规格冲突，标明不同渠道数据（如华为 910C 显存是 96G 还是 128G、特斯拉 AI5 是 TSMC N3E 还是三星 2nm），并给出了专业且合理的成因解释。

---

## 3. 技术路线预测与不确定性区分 (2026-2031)
白皮书在第 7 章节重点对未来五年的 AI 芯片演进做出了客观分析，并采用严谨的态度，明确区分了三类信息：
1.  **确凿事实 (Facts)：** 晶圆代工物理成本继续狂飙、JEDEC HBM4 物理 2048-bit 宽接口规范、1000W 功耗红线下数据中心强制部署直接液体冷却（DLC）。
2.  **合理推测 (Speculations)：** 硅光共封装光学（CPO）物理替代传统铜网互联、大模型推理 FP4 窄精度微架构实现 100% 普及、云巨头自研 ASIC 吞噬 30% 云推理市场。
3.  **重大不确定性 (Uncertainties)：** 中国本土晶圆厂在无 EUV 光刻机和化学耗材限制下向 5nm/更先进制程突围的商业良率瓶颈、存算一体新型非易失存储（RRAM/MRAM）堆叠工艺良率、量子与超导算力商业化落地可行性（五年内商用概率极低）。

---

## 4. 交付件格式
所有文档均为中文字体精心渲染，支持多重场景阅览：
*   **Markdown 版本：** 位于 `report/report.md`，配有标准锚点链接和完整的排版格式，适合在线快速阅读及跨平台查阅。
*   **Word 版本：** 位于 `report/report.docx`，使用 Microsoft YaHei（微软雅黑）字体、专业蓝色系标题（Heading 1 为深蓝、Heading 2 为青色）、1.15倍行距，配有精美封皮与完整的参数对比大表，符合大厂商业投研标准。
*   **PDF 交付件：** 位于 `report/report.pdf` 与 `report/appendix.pdf`，依托 Noto Sans CJK 中文字库直接矢量编译而成，具备精美的版面、跨页页眉页脚及精准的页码标注。
*   **矢量图表：** 位于 `charts/` 目录，所有 SVG 图片均支持无级缩放，可在浏览器中直接极速预览。

---

## 项目运行与重生成脚本

如果您希望重新生成数据库、矢量图表、Word 报告或 PDF 文件，可以在沙箱终端中直接运行：
```bash
# 1. 重新生成 CSV 数据库文件
python3 generate_db.py

# 2. 重新生成 bib 和冲突 md 引用源
python3 generate_sources.py

# 3. 重新生成 8 张漂亮的 SVG 矢量图表
python3 generate_charts.py

# 4. 重新写入长篇 Markdown 报告
python3 generate_report.py

# 5. 重新编译生成精美排版的 Word 文档
python3 generate_docx.py

# 6. 重新编译生成 Noto Sans SC 矢量的 PDF 交付件和附录
python3 generate_pdf.py
```
所有生成代码完全自包含且不依赖外部闭源依赖，安全、高效、精准。
