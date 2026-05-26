# GX-008 scene_037 合成 GPR 配对诊断结果说明

## 1. 场景目的
scene_037 用于验证 MyGPR 的 gprMax raw/background 配对、Ey 分量转换、target_response 计算、可视化和 Evidence 导出链路。

## 2. 模型设置
- air/sand interface
- GSSI-like 1.5 GHz antenna
- Ey receiver component
- dry sand half-space
- air/free-space layer
- PEC cylinder target
- n80 scan
- target_response = raw_with_target - background_only

## 3. 几何参数
- domain: 1.0 x 0.15 x 0.40 m
- grid: 0.002 x 0.002 x 0.002 m
- dry sand: z=0.000..0.260 m
- air/free-space: z=0.260..0.400 m
- soil surface: z=0.260 m
- antenna skid bottom z=0.310 m
- antenna standoff=0.050 m
- target center x=0.50 m, z=0.180 m
- target radius=0.03 m
- target cover depth=0.05 m
- target center trace=41
- traces=80

## 4. 结果摘要
- raw_shape: [3636, 80]
- background_shape: [3636, 80]
- target_response_shape: [3636, 80]
- target_response_energy: 3554.8169202461177
- target_to_raw_energy_ratio: 0.03057964057539346
- target_to_background_energy_ratio: 0.03146837378283868
- raw_background_psnr: 33.08998897357791
- roi_energy_ratio: 0.9979606645548237
- ROI energy ratio 仅为诊断性集中度指标，不代表检测准确率。

## 5. 图像解释
target_response_crop_best_candidate.png 显示了以设计目标中心 trace 附近为中心的双曲线状响应。paired_preview_panel.png 展示 raw、background 与 target_response 的配对流程。A-scan overlay 支撑中心 trace 附近响应最强。

## 6. 可主张内容
允许主张：
- MyGPR 完成了 scene_037 合成 raw/background 配对仿真结果整理。
- target_response 中出现与设计目标位置一致的双曲线状响应。
- 该结果支持 MyGPR 的 synthetic paired diagnostic 链路。

## 7. 不可主张内容
禁止主张：
- 精确复刻 CLT-GPR 数据集。
- 完成最终 paper benchmark。
- 真实场地验证。
- AutoTune 有效性证明。
- ROI energy ratio 证明检测正确率。
- 该图等价于真实 GPR field data。

## 8. Claim boundary
- Synthetic paired diagnostic result only.
- Not exact CLT-GPR replication.
- Not finalized paper benchmark.
- Not field validation.
- Not AutoTune evaluation.
- Not a target correctness claim without ROI/ground-truth review.
