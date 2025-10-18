---
tilte: "First_Day:About Virtual Environments from PY"
date: 2025/10/18
---
# 关于常用的Python虚拟环境
- [py自带的venv环境和anaconda的虚拟环境]

## 为什么要用虚拟环境
### 依赖管理和版本冲突
- **依赖管理**：控制这些库的安装、版本、更新和隔离 ，不同的库所对应的版本可能不同，
- 所以一旦同时处于同一个环境中，就会发生版本冲突。
- 项目 A 需要 numpy==1.20.0
- 项目 B 需要 numpy==1.25.0
- 如果你全局能用一个numpy，这样的话就会出错。

## Python自带的venv环境
- 特点： 简单、轻便 py自带
- 主要用途： 纯 Python 项目依赖管理
- 包管理器： pip

## 关于如何使用venv环境
### 创建环境
- python -m venv myproject_env
### 激活（Windows）
- myproject_env\Scripts\activate
### 安装包
- pip install requests flask
### 导出依赖
- pip freeze > requirements.txt

## anaconda的虚拟环境
- 适用场景： 机器学习、深度学习、数据分析、科学计算
- 对比于venv： 能够安装预编译好的二进制包和也能用于除py的其他语言

## 关于如何使用conda
### 创建一个名为 myenv 的环境，指定 Python 版本 
- conda create -n myenv python=3.10
### 激活
- conda activate myenv
### 激活后
- (myenv) $ python --version
- Python 3.10.x
### 安装包（conda install）
- 安装 PyTorch
- conda install pytorch torchvision torchaudio pytorch-cuda=11.8 -c pytorch -c nvidia
### 导出环境
- conda env export > environment.yml

## Tip
- 有时候你可能会发现你pip install可能提示没有 WHY?^^
### 因为你安装的包和你运行的py不是同一个环境
-1.你可能没激活虚拟环境 这样你安装的包就是在系统文件里了
-2.系统有太多py版本了，包可能在别的地方而不是你现在的py
-3.在conda环境中用了pip
-4.错误解释器 和对应的py版本不符合

