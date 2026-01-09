 

# SnapShrink
- 工具部署（可以直接使用）：https://guyuesnapshrink.netlify.app/ （基于Google Build构建）
- 一个使用 Pillow(PIL) 的图片压缩示例与工具集，演示如何通过无损与有损方法减小 PNG 文件大小。

## 主要内容
- 无损优化：使用 `optimize=True` 与 `compress_level` 来减少 PNG 的编码冗余。
- 有损方法示例：调色板化（将 RGB 转为 P 模式）、调整分辨率、移除元数据（EXIF）等。
- 提供了一个交互式 Jupyter Notebook `pic_compression.ipynb`，包含示例代码和说明，方便试验不同策略。

## 快速开始
1. 克隆或下载仓库到本地。
2. 建议使用虚拟环境（可选）：

	powershell:

	python -m venv .venv; .\.venv\Scripts\Activate.ps1

3. 安装依赖（仅需 Pillow）：

	powershell:

	pip install --upgrade pip; pip install pillow

4. 打开并运行 Notebook：

	- 使用 VS Code 或 Jupyter Notebook 打开 `pic_compression.ipynb`。
	- 按单元格顺序运行示例（每个函数下方都示范了如何调用并保存输出文件）。

## 示例函数（Notebook 中的核心）
- compress_png_pillow: 无损优化（optimize + compress_level）
- compress_png_color: 将真彩色转换为 256 色调色板，显著减小文件（有损）
- compress_png_size: 通过缩放分辨率进行压缩（有损）
- compress_png_Metadata: 通过重建像素数据来移除元数据（轻微减小）

## 注意事项
- 有损方法会改变图像的视觉质量，请在保留原始文件的前提下操作。
- 不同图片对各策略敏感度不同，建议在少量样本上先做对比。

## 贡献与问题
欢迎提交 issue 或 pull request。若需联系作者，请在仓库中留言。

---
（该 README 为简洁说明，详细用法请参阅 `pic_compression.ipynb`）

