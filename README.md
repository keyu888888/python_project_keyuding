# python_project_keyuding
Python课程项目代码部分

项目使用 NumPy 实现 OpenCLIP ViT-B/32 图像编码器。默认输入课程提供的 10 张图像，输出每张图像的 512 维单位长度特征。

## 安装依赖

在仓库根目录执行以下命令。实验使用 Python 3.14。

```powershell
python -m pip install -r requirements.txt
```

## 运行小型示例

课程提供的 `transformer_steps.py` 使用三条标记和一组示例参数演示注意力、MLP 和残差连接。安装依赖后即可运行。

```powershell
python transformer_steps.py
```

## 运行完整图像编码器

从课程发放的 `project1-numpy-student` 中复制 `weights/` 和 `assets/` 两个目录到仓库根目录，保留里面的文件及路径。`weights/` 包含模型权重及其清单，`assets/` 包含测试图像、清单及参考输出。

```powershell
python -u check.py --stage all
python run.py --output output_tokens.npz
```

`check.py` 对照参考数据做分阶段检查。`run.py` 将图像 ID 和形状为 `[10, 512]` 的特征数组保存到 `output_tokens.npz`。也可以用 `python run.py --images path/to/photo.jpg --output output_tokens.npz` 编码自己的图片。
