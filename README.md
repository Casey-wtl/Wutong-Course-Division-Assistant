# 梧桐分课助手 / Wutong Course Grouping Assistant

一个基于Python和Tkinter开发的智能分课系统，专为音乐小组课教学场景设计，支持自动分组、教师分配和拖拽操作。

A Python and Tkinter-based intelligent course grouping system designed specifically for group music teaching scenarios, supporting automatic grouping, teacher assignment, and drag-and-drop operations.

## 功能特点 / Features

### 🎯 核心功能 / Core Features
- **智能分组**: 自动将学生按性别、班级进行分组，支持尖子生单独分组
  **Smart Grouping**: Automatically groups students by gender and class, supporting individual grouping for top students
- **教师分配**: 基于历史数据智能分配教师，平衡工作量
  **Teacher Assignment**: Intelligently assigns teachers based on historical data, balancing workload
- **拖拽操作**: 支持Excel文件拖拽导入，操作便捷
  **Drag & Drop**: Supports Excel file drag-and-drop import for convenient operation
- **多视图**: 提供学生名单、分组结果、教师分配、最终名单等多个视图
  **Multi-View**: Provides multiple views including student list, grouping results, teacher assignment, and final list

### 🔧 技术特性 / Technical Features
- **Python + Tkinter**: 跨平台桌面应用
  **Python + Tkinter**: Cross-platform desktop application
- **Pandas数据处理**: 高效的数据分析和处理
  **Pandas Data Processing**: Efficient data analysis and processing
- **拖拽支持**: 集成tkinterdnd2库，支持文件拖拽
  **Drag Support**: Integrated tkinterdnd2 library for file drag-and-drop
- **Excel导入导出**: 完整的Excel文件支持
  **Excel Import/Export**: Complete Excel file support

## 系统要求 / System Requirements

- Python 3.7+
- Windows 10/11 (推荐/Recommended)
- 支持macOS和Linux / Supports macOS and Linux

## 安装依赖 / Installation Dependencies

```bash
pip install -r requirements.txt
```

### 主要依赖包 / Main Dependencies
- `tkinter` - GUI界面 / GUI interface
- `pandas` - 数据处理 / Data processing
- `numpy` - 数值计算 / Numerical computation
- `tkinterdnd2` - 拖拽功能 / Drag and drop functionality
- `openpyxl` - Excel文件处理 / Excel file processing

## 使用方法 / Usage

### 1. 启动程序 / Launch Program
```bash
python 分课助手.py
```

### 2. 导入数据 / Import Data

#### 学生名单格式要求 / Student List Format Requirements
Excel文件必须包含以下列 / Excel file must contain the following columns:
- **学号**: 学生学号（用于自动提取班级信息）
  **Student ID**: Student ID (used to automatically extract class information)
- **姓名**: 学生姓名
  **Name**: Student name
- **性别**: 学生性别（男/女）
  **Gender**: Student gender (Male/Female)

#### 教师历史数据格式要求 / Teacher History Data Format Requirements
Excel文件必须包含以下列 / Excel file must contain the following columns:
- **教师姓名**: 教师姓名
  **Teacher Name**: Teacher's name
- **尖子生**: 指定给该教师的尖子生姓名
  **Top Student**: Name of the top student assigned to this teacher
- **普通生**: 指定给该教师的普通生姓名（用顿号、逗号或空格分隔）
  **Regular Students**: Names of regular students assigned to this teacher (separated by commas, spaces, or Chinese punctuation)
- **应分总组数**: 该教师应分配的总组数（该组数不包含尖子生）
  **Total Groups to Assign**: Total number of groups this teacher should be assigned (excluding top students)

### 3. 操作流程 / Operation Process

1. **导入学生名单**: 拖拽或点击导入学生名单Excel文件
   **Import Student List**: Drag and drop or click to import student list Excel file
2. **导入教师历史数据**: 拖拽或点击导入教师历史分组数据
   **Import Teacher History Data**: Drag and drop or click to import teacher history grouping data
3. **自动分组**: 点击"自动分组"按钮，系统自动完成分组
   **Auto Grouping**: Click "Auto Grouping" button, system automatically completes grouping
4. **分配教师**: 点击"分配教师"按钮，系统智能分配教师
   **Assign Teachers**: Click "Assign Teachers" button, system intelligently assigns teachers
5. **导出结果**: 导出分组结果、教师分配结果或最终学生名单
   **Export Results**: Export grouping results, teacher assignment results, or final student list

### 4. 分组规则 / Grouping Rules

- **尖子生**: 每人单独一组
  **Top Students**: Each person in a separate group
- **普通生**: 3人一组，优先同班分组
  **Regular Students**: 3 people per group, prioritizing same-class grouping
- **剩余学生**: 组成2人组或与其他组合并
  **Remaining Students**: Form 2-person groups or merge with other groups

### 5. 教师分配策略 / Teacher Assignment Strategy

- **优先分配**: 尖子生和指定学生优先分配给指定教师
  **Priority Assignment**: Top students and designated students are prioritized for designated teachers
- **均衡分配**: 考虑班级分布、性别平衡等因素
  **Balanced Assignment**: Considers factors such as class distribution and gender balance
- **工作量控制**: 确保教师分配组数不超过应分总组数
  **Workload Control**: Ensures the number of groups assigned to teachers does not exceed the total groups to assign

## 界面说明 / Interface Description

### 主要标签页 / Main Tabs
- **学生名单**: 显示导入的学生信息，包括尖子生标记
  **Student List**: Displays imported student information, including top student markers
- **分组结果**: 显示自动分组的结果
  **Grouping Results**: Shows automatic grouping results
- **教师分配**: 显示教师分配情况
  **Teacher Assignment**: Shows teacher assignment status
- **最终学生名单**: 显示包含分配教师的完整学生名单
  **Final Student List**: Shows complete student list with assigned teachers

### 功能按钮 / Function Buttons
- **数据导入**: 导入学生名单、导入教师历史数据
  **Data Import**: Import student list, import teacher history data
- **处理操作**: 自动分组、分配教师
  **Processing Operations**: Auto grouping, assign teachers
- **导出**: 导出分组、分配、最终名单
  **Export**: Export grouping, assignment, final list

## 文件结构 / File Structure

```
分课助手.py          # 主程序文件 / Main program file
requirements.txt     # 依赖包列表 / Dependency package list
README.md           # 说明文档 / Documentation
```

## 注意事项 / Important Notes

1. **文件格式**: 仅支持.xlsx和.xls格式的Excel文件
   **File Format**: Only supports .xlsx and .xls format Excel files
2. **数据完整性**: 确保Excel文件包含必要的列和数据
   **Data Integrity**: Ensure Excel file contains necessary columns and data
3. **学号格式**: 学号倒数第三位用于自动提取班级信息
   **Student ID Format**: The third-to-last digit of student ID is used to automatically extract class information
4. **备份数据**: 建议在操作前备份原始数据
   **Data Backup**: It's recommended to backup original data before operation

## 常见问题 / FAQ

### Q: 程序无法启动 / Q: Program cannot start
A: 检查Python版本和依赖包是否正确安装
   A: Check if Python version and dependency packages are correctly installed

### Q: 拖拽功能不工作 / Q: Drag and drop function not working
A: 确保安装了tkinterdnd2库，且文件格式正确
   A: Ensure tkinterdnd2 library is installed and file format is correct

### Q: 分组结果不理想 / Q: Grouping results are not ideal
A: 检查学生名单数据完整性，确保性别、班级信息正确
   A: Check student list data integrity, ensure gender and class information is correct

### Q: 教师分配失败 / Q: Teacher assignment failed
A: 检查教师历史数据格式，确保"应分总组数"列存在且为数字
   A: Check teacher history data format, ensure "Total Groups to Assign" column exists and is numeric

## 更新日志 / Update Log

### v1.0.0 (2025-06-26)
- 初始版本发布 / Initial version release
- 支持基本的分组和教师分配功能 / Support basic grouping and teacher assignment functions
- 集成拖拽操作 / Integrated drag and drop operations
- 多视图界面设计 / Multi-view interface design

## 技术支持 / Technical Support

如有问题或建议，请联系开发团队。
If you have any questions or suggestions, please contact the development team.

---

**梧桐分课助手 © 2025 Dr.WTL All rights reserved.**
**Wutong Course Grouping Assistant © 2025 Dr.WTL All rights reserved.**
