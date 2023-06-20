---
title: venv
date: 2023-06-13 13:28:18
tags:
---

# venv 常用命令

在 Python 的虚拟环境（venv）中，有一些常用的命令可以帮助您管理和使用虚拟环境。以下是一些常见的 venv 命令：

1. 创建虚拟环境：
   ```
   python3 -m venv myenv
   ```

   上述命令将创建一个名为 "myenv" 的虚拟环境。

2. 激活虚拟环境：
   ```
   source myenv/bin/activate
   ```

   通过上述命令，您可以激活名为 "myenv" 的虚拟环境。一旦激活，您在终端中执行的 Python 命令和安装的包都将与该虚拟环境关联。

3. 退出虚拟环境：
   ```
   deactivate
   ```

   使用上述命令，您可以退出当前激活的虚拟环境。

4. 查看已安装的包：
   ```
   pip list
   ```

   该命令将显示当前虚拟环境中安装的所有包的列表。

5. 安装包：
   ```
   pip install package_name
   ```

   使用上述命令，您可以在虚拟环境中安装指定的包。

6. 卸载包：
   ```
   pip uninstall package_name
   ```

   通过上述命令，您可以从虚拟环境中卸载指定的包。

7. 删除虚拟环境

   ```
   rm -r venv
   ```

   
