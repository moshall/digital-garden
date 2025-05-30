---
{"dg-publish":true,"permalink":"/04.个人成长/开发/python工具/Python脚本：CSV 文件合并工具说明书/","title":"Python脚本：CSV 文件合并工具说明书","tags":["工具"]}
---


## 1. 简介

本工具是一个 Python 脚本，旨在帮助用户方便地将多个具有相同表头的 CSV (逗号分隔值) 文件合并成一个单一的 CSV 文件。它提供了一个交互式的界面，允许用户在运行时选择单个或多个 CSV 文件，或者选择一个包含多个 CSV 文件的文件夹进行合并。

**主要功能：**

* **交互式选择**：通过图形用户界面 (GUI) 选择源文件或文件夹。
* **表头一致性检查**：自动检查所有待合并文件的表头是否完全一致，确保数据完整性。若表头不一致，则合并失败并提示用户。
* **空文件处理**：能够识别并跳过空文件或仅有表头的文件，并给出相应提示。
* **行数统计**：报告每个源 CSV 文件的数据行数以及最终合并后文件的数据总行数。
* **自定义输出**：允许用户通过 GUI 对话框选择合并后文件的保存位置和文件名。

## 2. 系统要求

* **操作系统**：Windows, macOS, 或 Linux (任何支持 Tkinter 的系统)。
* **Python 版本**：Python 3.6 或更高版本。
* **所需库 (Python 标准库)**：
    * `csv`
    * `os`
    * `glob`
    * `pathlib`
    * `tkinter` (通常随 Python 标准安装包提供)

    这些都是 Python 的标准库，一般无需额外安装。

## 3. 开始之前

* **准备 CSV 文件**：
    * **表头一致性**：确保所有计划合并的 CSV 文件的第一行（即表头）是**完全相同**的。这包括列的数量、列的名称、列的顺序以及大小写。这是成功合并的关键。
    * **文件编码**：
        * 脚本在读取文件时会尝试使用 `utf-8-sig` 编码，这有助于正确处理带有字节顺序标记 (BOM) 的 UTF-8 文件（常见于某些 Windows 程序导出的 CSV）。
        * 合并后的输出文件将以 `utf-8` 编码保存。
* **备份数据**：虽然脚本本身不会修改原始文件，但在进行任何文件操作前，建议备份您的重要数据。

## 4. 如何使用

### 步骤 1: 保存脚本

1.  将提供的 Python 脚本代码复制到一个纯文本文件中。
2.  将该文件保存为以 `.py` 结尾的文件，例如：`interactive_merge_csv.py`。

### 步骤 2: 运行脚本

1.  打开您的操作系统终端（在 macOS 或 Linux 上是 Terminal，在 Windows 上是命令提示符(Command Prompt)或 PowerShell）。
2.  使用 `cd` 命令导航到您保存 `interactive_merge_csv.py` 脚本的目录。例如：
    ```bash
    cd /path/to/your/script_directory
    ```
    或者在 Windows 上：
    ```bash
    cd C:\path\to\your\script_directory
    ```
3.  执行脚本：
    ```bash
    python3 interactive_merge_csv.py
    ```
    (如果 `python3` 命令无效，请尝试使用 `python interactive_merge_csv.py`)

### 步骤 3: 选择输入方式

脚本运行后，终端会首先提示您选择输入文件的方式：

```
你想选择 (F)单个或多个CSV文件 还是 (D)一个包含CSV文件的文件夹? [F/D]:
```

* 输入 `F` (或 `f`) 然后按 Enter：如果您想手动选择一个或多个分散的 CSV 文件。
* 输入 `D` (或 `d`) 然后按 Enter：如果您想选择一个文件夹，脚本将自动处理该文件夹内所有的 `.csv` 文件。

### 步骤 4: 选择文件或文件夹

根据您在步骤 3 中的选择，会弹出一个图形对话框：

* **如果选择 'F' (文件模式)**：
    * 会弹出一个“选择要合并的CSV文件”对话框。
    * 您可以浏览文件系统，找到并选择一个或多个 CSV 文件。
    * **多选文件**：
        * 按住 `Ctrl` 键 (Windows/Linux) 或 `Command` 键 (macOS) 并逐个点击文件。
        * 或者，选择一个文件后，按住 `Shift` 键并点击另一个文件以选择一个范围内的所有文件。
    * 选择完毕后，点击“打开”或类似按钮。

* **如果选择 'D' (文件夹模式)**：
    * 会弹出一个“选择包含CSV文件的文件夹”对话框。
    * 浏览并选择包含您想要合并的 CSV 文件的文件夹。
    * 选择完毕后，点击“选择文件夹”或类似按钮。

如果您未选择任何文件/文件夹或关闭了对话框，脚本将在终端提示并退出。

### 步骤 5: 选择输出位置和文件名

如果成功选择了输入文件且文件初步检查（例如，文件夹模式下找到了 CSV 文件）通过，脚本会处理数据。在准备好写入合并数据之前，会弹出另一个对话框：

* **“保存合并后的CSV文件”对话框**：
    * 您可以浏览到希望保存合并后文件的位置。
    * 在“文件名”字段中，您可以修改默认的输出文件名（默认为 `merged_output.csv`）。
    * 确认后，点击“保存”。

如果您在此步骤取消或关闭对话框，合并后的文件将不会被保存，脚本会提示操作已取消。

### 步骤 6: 查看结果

* **终端输出**：
    * 脚本会在终端显示其操作进度，包括：
        * 它找到并尝试处理的文件列表。
        * 关于空文件或只有表头的文件的警告。
        * 表头检查的结果。
        * 每个源文件的数据行数统计。
        * 合并成功后，新文件的保存路径和总数据行数。
        * 任何发生的错误信息。
* **合并后的文件**：
    * 在您于步骤 5 中指定的位置，会找到生成的合并 CSV 文件。打开它检查内容是否符合预期。

## 5. 功能详解

* **表头一致性检查**：
    脚本会读取所选的第一个（非空）CSV 文件的表头，并将其作为基准。随后，它会检查所有其他选定 CSV 文件的表头是否与此基准表头完全一致。如果不一致，将中止合并并报告不匹配的文件及其表头。

* **行数统计**：
    统计的是每个源 CSV 文件中**数据行**的数量（即不包括表头行）。最终合并文件的行数统计也是指数据行的数量。

* **文件编码**：
    * 输入：尝试以 `utf-8-sig` 读取，能更好地兼容 Windows环境下Excel等软件导出的带有BOM的CSV文件。
    * 输出：合并后的文件以标准的 `utf-8` 编码保存，具有良好的跨平台兼容性。

## 6. 故障排除

* **脚本不运行 / `python3` (或 `python`) 命令未找到**：
    * 确保 Python 3 已正确安装并已添加到系统的 PATH 环境变量中。参考本文档的“系统要求”部分。

* **图形对话框未出现**：
    * 确保您的 Python 环境包含 `tkinter` 模块。这在标准的 Python 安装中通常是默认包含的。在某些极简的 Linux 环境下可能需要手动安装 (`sudo apt-get install python3-tk` 或类似命令)。

* **没有选择任何文件/文件夹，或在对话框中点击了“取消”**：
    * 脚本会在终端提示“没有选择任何文件/文件夹”或“操作已取消”，然后正常退出。这是预期的行为。

* **“在文件夹 '...' 中没有找到任何CSV文件。”** (当使用文件夹模式时)：
    * 检查您选择的文件夹中是否确实存在以 `.csv` 结尾的文件。
    * 确认文件名和扩展名无误。

* **“错误：CSV文件表头不一致，无法合并！”**：
    * 这是最常见的错误之一。您需要手动检查并修改提示中指出的文件，确保它们的表头（第一行）完全一致。注意检查空格、大小写、列顺序和列数量。

* **“警告：文件 ... 是空的，将跳过。”**：
    * 这表示某个 CSV 文件不包含任何数据行（可能只有表头，或完全是空的）。脚本会跳过这些文件的数据部分，但如果它们有表头，其表头仍会参与一致性检查。

* **权限错误 (例如，在保存文件时)**：
    * 如果您尝试将合并后的文件保存到您没有写入权限的目录（如系统目录），可能会遇到此错误。请尝试选择用户有权访问的目录（如“文档”、“桌面”或用户主目录下的其他位置）。

## 7. 注意事项

* **处理大量或大型文件**：合并非常多或非常大的 CSV 文件可能会消耗较多的时间和内存。请耐心等待脚本执行完成。
* **原始文件安全**：此脚本设计为不修改原始输入文件。它读取原始文件并在您指定的位置创建一个全新的合并文件。
* **CSV 格式复杂性**：标准的 CSV 格式可能很简单，但实际中的 CSV 文件可能包含复杂的引用、换行符等。此脚本使用 Python 的 `csv` 模块，能处理大多数标准情况。如果您的 CSV 文件结构非常特殊，请先用少量文件测试。



# 代码

```python
import csv
import os
import glob
from pathlib import Path
from tkinter import Tk, filedialog

def merge_csv_files(csv_file_paths):
    """
    合并用户选择的多个表头相同的CSV文件。

    Args:
        csv_file_paths (list): 包含所有待合并CSV文件绝对路径的列表。

    Returns:
        bool: 如果合并成功返回 True，否则返回 False。
    """
    if not csv_file_paths:
        print("错误：没有选择任何CSV文件进行合并。")
        return False

    print(f"准备合并以下CSV文件: {csv_file_paths}")

    headers_map = {}  # 用于存储每个文件的表头: {filepath: header_tuple}
    row_counts = {}   # 用于存储每个文件的数据行数: {basename(filepath): count}
    all_data_rows = [] # 用于存储所有文件的数据（不包括表头）
    unified_header = None

    # 第一次遍历：检查表头一致性并统计行数
    for file_path in csv_file_paths:
        try:
            with open(file_path, 'r', newline='', encoding='utf-8-sig') as csvfile:
                reader = csv.reader(csvfile)
                current_header = tuple(next(reader)) # 将表头转为元组以便比较和作为字典键
                headers_map[file_path] = current_header
                
                data_rows_count = 0
                for row in reader:
                    data_rows_count += 1
                row_counts[os.path.basename(file_path)] = data_rows_count
        except StopIteration: # 空文件处理
            print(f"警告：文件 {os.path.basename(file_path)} 是空的，将跳过。")
            row_counts[os.path.basename(file_path)] = 0
            headers_map[file_path] = tuple() # 添加一个空元组作为表头
            continue
        except Exception as e:
            print(f"读取文件 {os.path.basename(file_path)} 时发生错误: {e}")
            return False

    # 检查表头是否都一致
    if not headers_map: # 如果所有选择的文件都是空的或无法读取
        print("错误：未能从所选文件中读取任何有效的表头信息。")
        return False

    # 以第一个有效文件的表头为基准
    first_valid_header = None
    first_valid_file_path = None
    for file_path, header in headers_map.items():
        if header: # 找到第一个非空表头
            first_valid_header = header
            first_valid_file_path = file_path
            break
    
    if first_valid_header is None and any(headers_map.values()): # 所有文件都是空的但至少有一个被处理过
         print("警告：所有选择的CSV文件都是空的（只有表头或完全为空）。将尝试使用第一个文件的（空）表头。")
         # 在这种情况下，如果用户仍想合并（例如，合并多个空数据文件但有相同表头的文件），
         # 可以考虑允许，或者直接报错。目前，如果第一个文件是空的，下面的逻辑会取空表头。
         # 如果headers_map中所有表头都是空元组，它们会被视作一致。
         # 如果某些是空，某些非空，则会报错。

    if not first_valid_header and not any(h for h in headers_map.values() if h): # 如果所有文件都是空的
        print("错误：所有选择的CSV文件都是空的或没有表头。")
        return False


    for file_path, header in headers_map.items():
        if row_counts.get(os.path.basename(file_path), -1) == 0 and not header : # 跳过完全为空且没有记录表头的文件
            continue
        if header != first_valid_header:
            print("\n错误：CSV文件表头不一致，无法合并！")
            print(f"基准表头 (来自文件 '{os.path.basename(first_valid_file_path)}'): {list(first_valid_header) if first_valid_header else '无表头'}")
            print(f"文件 '{os.path.basename(file_path)}' 的表头: {list(header) if header else '无表头'}")
            return False
            
    unified_header = list(first_valid_header) if first_valid_header else []
    print("\n所有有效CSV文件的表头一致。")

    # 第二次遍历：读取数据行
    total_merged_rows = 0
    for file_path in csv_file_paths:
        if row_counts.get(os.path.basename(file_path), 0) == 0 and not headers_map.get(file_path): #再次跳过空文件
             continue
        try:
            with open(file_path, 'r', newline='', encoding='utf-8-sig') as csvfile:
                reader = csv.reader(csvfile)
                next(reader) # 跳过表头
                for row in reader:
                    all_data_rows.append(row)
                    total_merged_rows +=1
        except StopIteration: # 文件只有表头
            continue
        except Exception as e:
            print(f"合并文件 {os.path.basename(file_path)} 数据时发生错误: {e}")
            return False

    # 提示用户选择保存位置和文件名
    print("\n请选择合并后文件的保存位置和名称...")
    output_initial_dir = os.path.dirname(csv_file_paths[0]) if csv_file_paths else os.getcwd()
    output_path = filedialog.asksaveasfilename(
        title="保存合并后的CSV文件",
        initialdir=output_initial_dir,
        initialfile="merged_output.csv",
        defaultextension=".csv",
        filetypes=[("CSV files", "*.csv"), ("All files", "*.*")]
    )

    if not output_path:
        print("操作已取消：未选择保存位置。合并后的文件未保存。")
        return False

    # 写入合并后的CSV文件
    try:
        with open(output_path, 'w', newline='', encoding='utf-8') as csvfile:
            writer = csv.writer(csvfile)
            if unified_header: # 确保表头不是空的 (除非所有文件都没有表头)
                writer.writerow(unified_header)
            writer.writerows(all_data_rows)
    except Exception as e:
        print(f"写入合并文件 {os.path.basename(output_path)} 时发生错误: {e}")
        return False

    print("\n--- 文件行数统计 (数据行，不含表头) ---")
    for filename, count in row_counts.items():
        print(f"文件 '{filename}': {count} 行数据")

    print(f"\n成功合并 {len(csv_file_paths)} 个CSV文件到 '{output_path}'")
    print(f"最终合并后的CSV文件 '{os.path.basename(output_path)}' 包含表头和 {total_merged_rows} 行数据。")
    return True

if __name__ == "__main__":
    # 创建一个隐藏的Tkinter主窗口，因为我们只需要对话框
    root = Tk()
    root.withdraw()

    csv_files_to_process = []
    choice = input("你想选择 (F)单个或多个CSV文件 还是 (D)一个包含CSV文件的文件夹? [F/D]: ").strip().upper()

    if choice == 'F':
        print("请在弹出的对话框中选择一个或多个CSV文件...")
        # 使用 askopenfilenames允许多选
        selected_files = filedialog.askopenfilenames(
            title="选择要合并的CSV文件",
            filetypes=[("CSV files", "*.csv"), ("All files", "*.*")]
        )
        if selected_files: # askopenfilenames 返回一个元组
            csv_files_to_process = list(selected_files)
        else:
            print("没有选择任何文件。")
    elif choice == 'D':
        print("请在弹出的对话框中选择一个包含CSV文件的文件夹...")
        selected_folder = filedialog.askdirectory(
            title="选择包含CSV文件的文件夹"
        )
        if selected_folder:
            # 查找文件夹下所有的csv文件
            csv_files_to_process = glob.glob(os.path.join(selected_folder, "*.csv"))
            if not csv_files_to_process:
                print(f"在文件夹 '{selected_folder}' 中没有找到任何CSV文件。")
        else:
            print("没有选择任何文件夹。")
    else:
        print("无效的选择。程序将退出。")

    if csv_files_to_process:
        merge_csv_files(csv_files_to_process)
    else:
        print("没有要处理的CSV文件。程序退出。")

    # 显式销毁Tk根窗口（虽然通常在脚本结束时会自动处理）
    root.destroy()

```