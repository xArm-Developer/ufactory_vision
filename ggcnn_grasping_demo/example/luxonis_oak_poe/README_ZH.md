# 基于 Luxonis OAK-D-Pro-PoE 相机的配置

## 硬件要求
- **机械臂**: [UFACTORY 850、xArm系列、Lite6](https://www.ufactory.cc/ufactory-850/) 
- **末端执行器**: [UFACTORY xArm 机械爪](https://www.ufactory.cc/product-page/ufactory-xarm-gripper/) 或 [Lite6 真空吸头](https://www.ufactory.cc/product-page/ufactory-lite-6-kit/)
- **摄像头**: [OAK-D Pro PoE](https://shop.luxonis.com/products/oak-d-pro-poe?variant=42469208883423)
- **POE供电器**: Tenda POE30G-AT, 1000M, 30W (或其他品牌)
- **摄像头支架**: UFACTORY 提供 (使用 3D 文件进行 3D 打印或 CNC 加工)
  - 3D 文件下载: [OAK_Camera_Stand.STEP](http://www.ufactory.cc/wp-content/uploads/2025/12/oak_camera_stand.zip)


## 软件

### 支持的 Python 版本

支持的 Python 版本：3.8-3.11 (推荐：3.11)。

## 安装

### 1. 克隆仓库

```bash
git clone https://github.com/xArm-Developer/ufactory_vision.git
cd ufactory_vision
```

### 2. 创建 Python 虚拟环境

建议使用虚拟环境运行此项目。

#### **Windows (使用 Anaconda)**

```bash
conda create --name ufactory_vision python=3.11
conda activate ufactory_vision
```

#### **Linux (使用 venv)**

```bash
python3.11 -m venv ufactory_vision
source ufactory_vision/bin/activate
```

### 3. 安装依赖与运行示例

请根据您使用的相机型号，执行相应的安装和运行步骤。
首先，确保您已进入 `luxonis_oak_poe` 目录:

```bash
cd ggcnn_grasping_demo/example/luxonis_oak_poe
```

#### 3.1 安装依赖
```bash
pip install -r requirements_depthai.txt
```

#### 3.2 运行示例
将 `192.168.1.xxx` 替换为您的机械臂控制器的实际 IP 地址。

*   **UFACTORY 850 或 xArm 5/6/7 系列机械臂**
    ```bash
    python run_oak_poe_grasp.py 192.168.1.xxx
    ```
*   **UFACTORY Lite 6 机械臂**
     ```bash
    python run_oak_poe_grasp_lite6.py 192.168.1.xxx
     ```


## 重要提示

* **TCP/坐标系偏移**: 请勿设置 TCP 偏移或坐标系偏移，否则可能需要调整代码。
* **TCP 负载**: 请设置 TCP 负载以避免错误的碰撞检测。
* **碰撞检测**: 运行示例前，请确保已启用碰撞检测，建议将碰撞灵敏度设置为 3 或更高。
