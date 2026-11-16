# TheoryPhysicsBench-50

**50 个独立的理论物理 Harbor 0.24.0 任务包。** 本仓库保存已验收的完整发布包，解压后即可查看任务、源码、参考解、评分器、来源说明和实际开发验证证据。

## 下载与阅读

- [完整任务包：TheoryPhysicsBench-50.zip](TheoryPhysicsBench-50.zip)
- [四页项目报告](报告.pdf)
- [发布包验收记录](package-validation.json)

解压 ZIP 后，先阅读 `TheoryPhysicsBench-50/README.md`；其中提供依赖安装、单题复现、完整核验及正式测评入口。设计与来源见包内 `docs/design-and-provenance.md`，50 题索引见 `checks/benchmark-50-index.md`。

| 学科 | 题数 |
|---|---:|
| 理论力学 | 5 |
| 电动力学 | 5 |
| 统计物理 | 5 |
| 量子力学 | 5 |
| 量子场论 | 25 |
| 广义相对论 | 5 |
| **合计** | **50** |

## 验证状态

- 880 项 Docker Linux 数值校准检查通过。
- 50 题最终版本均有 Harbor 参考解通过（oracle=1）、空提交不通过（nop=0）的实际记录，证据与最终题包哈希绑定。
- 完整包共 3580 个文件；ZIP 解压往返、逐文件哈希和凭据扫描均通过，包含命令日志。
- 四页报告已渲染并逐页检查。

**课程指定 Codex 每题 3 次、共 150 次的正式学生测评尚未执行，待课程统一 CLI 版本后运行。** Oracle/nop 是题包与评分链路的开发检查，不代表被测 Codex 的成绩。Mac Harbor 兼容运行方式、Linux 网络隔离的验证范围和课程原版题数规则均在包内如实说明。

在解压后的 `TheoryPhysicsBench-50` 目录执行：

```bash
python3 -B tools/check_benchmark50.py --require-calibrated --require-harbor
python3 -B tools/collect_release_evidence.py --verify-saved
```

任务计算使用 CPU Docker Linux；每题上限 4 CPU、4 GiB 内存、4 GiB 磁盘、0 GPU。正式被测智能体的模型服务或认证按课程配置提供。

## 发布指纹与材料归属

`TheoryPhysicsBench-50.zip` SHA-256：

```text
593e9bdd0874b80e8749eba5b1a49c8b5876f9faaf49119b8ac7ff70b7b0b0f2
```

发布包保留逐题教材、题号、页码及改编边界；不包含教材 PDF、整本 OCR、截图、个人配置或凭据。材料归属及使用范围见包内 `NOTICE.md`。当前仓库为私有发布包仓库，完整源码位于 ZIP 内。
