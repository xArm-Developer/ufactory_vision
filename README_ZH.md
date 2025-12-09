# ufactory_vision

## 项目概述

`ufactory_vision` 是一个基于 UFACTORY（深圳市众为创造科技有限公司） 机械臂的视觉抓取演示项目。用户可以通过本项目快速实现基于视觉的物体检测和抓取。

## 硬件要求

### 示例脚本的硬件配置

| 机械臂型号              | 相机型号                 | 末端执行器         |
| ----------------------- | ------------------------ | ------------------ |
| xArm 5/6/7或850 | Intel Realsense D435/D555 或 Luxonis OAK-D-Pro-PoE | UFACTORY 机械爪G1/G2   |
| Lite 6         | Intel Realsense D435 或 Luxonis OAK-D-Pro-PoE | Lite 6 真空吸头    |


* 基于 Intel Realsense D435 相机的配置：[Readme](/ggcnn_grasping_demo/example/realsense_d435/README_ZH.md)
* 基于 Intel Realsense D555 相机的配置：[Readme](/ggcnn_grasping_demo/example/realsense_d555/README_ZH.md)
* 基于 Luxonis OAK-D-Pro-PoE 相机的配置：[Readme](/ggcnn_grasping_demo/example/luxonis_oak_poe/README_ZH.md)

## 视频演示
* 定制850（1000M内置网线） + Realsense D555 + 内部网线走线 + UFACTORY 机械爪G2
  [![Watch the video](assets/realsense_d555.jpg)](https://www.bilibili.com/video/BV1PC2SBcEcr/?spm_id_from=333.1387.homepage.video_card.click&vd_source=9cdbfdb03a35ac858f97ba3ca89dc358)
* xArm6 + Realsense D435 + 外部USB走线 + UFACTORY 机械爪G1  
  [![Watch the video](assets/realsense_d435.jpg)](https://www.bilibili.com/video/BV1V9ABewE9Q/?spm_id_from=333.1387.upload.video_card.click&vd_source=9cdbfdb03a35ac858f97ba3ca89dc358)
* Lite6 + Luxonis OAK-D-Pro-PoE + 外部网线走线 + 真空吸头  
  [![Watch the video](assets/Luxonis_OAK_D_Pro_PoE.jpg)](https://www.bilibili.com/video/BV1PA2SBtEuJ/?spm_id_from=333.1387.homepage.video_card.click&vd_source=9cdbfdb03a35ac858f97ba3ca89dc358)

## 重要提示

* **TCP/坐标系偏移**: 请勿设置 TCP 偏移或坐标系偏移，否则可能需要调整代码。
* **TCP 负载**: 请设置 TCP 负载以避免错误的碰撞检测。
* **碰撞检测**: 运行示例前，请确保已启用碰撞检测，建议将碰撞灵敏度设置为 3 或更高。

## 许可证

本项目采用 **BSD 3-Clause 许可证**。详情请查看 [LICENSE](LICENSE) 文件。

## 致谢

我们的演示项目基于以下开源项目构建：

- [GGCNN](https://github.com/dougsm/ggcnn)
- [ggcnn_kinova_grasping](https://github.com/dougsm/ggcnn_kinova_grasping)