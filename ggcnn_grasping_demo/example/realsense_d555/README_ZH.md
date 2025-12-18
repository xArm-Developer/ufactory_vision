# 基于 Intel Realsense D555 

## 硬件要求 

- **机械臂**: [UFACTORY 850、xArm系列](https://www.ufactory.cc/ufactory-850/) 
- **末端执行器**: [UFACTORY xArm 机械爪G1/G2](https://www.ufactory.cc/product-page/ufactory-xarm-gripper/)
- **摄像头**: [Intel RealSense D555](https://realsenseai.com/products/d555-poe/)
- **POE供电器**: Tenda POE30G-AT, 1000M, 30W (或其他品牌)
- **摄像头支架**: UFACTORY 提供 (使用 3D 文件进行 3D 打印或 CNC 加工)
  - 3D 文件下载: [D555_Camera_Stand.STEP](https://www.ufactory.cc/wp-content/uploads/2025/12/D555_Camera_Stand.zip)


## 850末端网口定义
标准850机械臂内部由一根100M支持标准CAT5的以太网，从机械臂底座连接到末端。若需要内部走线，可以使用此网口。   

D555相机测试时使用定制版本的850（推荐），内部是一根1000M的网线，以获得稳定的相机数据。  
如需定制版本的850，M8航空接头-网口 转接线，请联系技术支持<support@ufactory.cc>。
![](user_ethernet.jpg)

定制850（1000M网线）末端网口定义：
| PIN | Signal   |
| --- | -------- |
| 1   | MX2-/DC- |
| 2   | MX3+/DD+ |
| 3   | MX3-/DD- |
| 4   | MX0-/DA- |
| 5   | MX1+/DB+ |
| 6   | MX0+/DA+ |
| 7   | MX0+/DC+ |
| 8   | MX1-/DB- |


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
首先，确保您已进入 `realsense_d555` 目录:

```bash
cd ggcnn_grasping_demo/example/realsense_d555
```

#### 3.1 安装依赖
```bash
pip install -r requirements_rs.txt
```

#### 3.2 运行示例
将 `192.168.1.xxx` 替换为您的机械臂控制器的实际 IP 地址。

*   **UFACTORY 850 或 xArm 5/6/7 系列机械臂**
    ```bash
    python run_rs_d555_grasp.py 192.168.1.xxx
    ```

注意：技术上D555和Lite6可以兼容，但其和真空吸头的重量超过Lite6负载范围，不建议在Lite6上使用。

## 重要提示

* **TCP/坐标系偏移**: 请勿设置 TCP 偏移或坐标系偏移，否则可能需要调整代码。
* **TCP 负载**: 请设置 TCP 负载以避免错误的碰撞检测。
* **碰撞检测**: 运行示例前，请确保已启用碰撞检测，建议将碰撞灵敏度设置为 3 或更高。
