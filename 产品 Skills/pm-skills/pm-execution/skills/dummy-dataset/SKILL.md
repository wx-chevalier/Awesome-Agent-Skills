---
name: dummy-dataset
description: "生成用于测试的逼真虚拟数据集，支持自定义列、约束条件及输出格式（CSV、JSON、SQL、Python 脚本）。适用于创建测试数据、构建模拟数据集，或为开发和演示生成示例数据。"
---
# 虚拟数据集生成

生成用于测试的逼真虚拟数据集，支持自定义列、约束条件及输出格式（CSV、JSON、SQL、Python 脚本）。生成可直接执行的脚本或数据文件，即开即用。

**适用场景：** 创建测试数据、生成示例数据集、为开发构建逼真的模拟数据，或填充测试环境。

**参数：**
- `$PRODUCT`：产品或系统名称
- `$DATASET_TYPE`：数据类型（如客户反馈、交易记录、用户画像）
- `$ROWS`：生成的行数（默认：100）
- `$COLUMNS`：需要包含的具体列或字段
- `$FORMAT`：输出格式（CSV、JSON、SQL、Python 脚本）
- `$CONSTRAINTS`：附加约束条件或业务规则

## Step-by-Step Process（分步流程）

1. **确定数据集类型** - 理解数据领域
2. **定义列规格** - 名称、数据类型和取值范围
3. **确定行数** - 需要多少条样本记录
4. **选择输出格式** - CSV、JSON、SQL INSERT 或 Python 脚本
5. **应用真实规律** - 确保数据看起来真实有效
6. **添加业务约束** - 遵守业务逻辑和关联关系
7. **生成或脚本化数据** - 创建可执行的输出
8. **验证输出** - 确保数据质量和完整性

## Template: Python Script Output（Python 脚本输出模板）

```python
import csv
import json
from datetime import datetime, timedelta
import random

# 配置
ROWS = $ROWS
FILENAME = "$DATASET_TYPE.csv"

# 列定义及逼真值生成器
columns = {
    "id": "auto-increment",
    "name": "first_last_name",
    "email": "email",
    "created_at": "timestamp",
    # 添加更多列...
}

def generate_dataset():
    """生成逼真的虚拟数据集"""
    data = []
    for i in range(1, ROWS + 1):
        record = {
            "id": f"U{i:06d}",
            # 根据列定义生成值
        }
        data.append(record)
    return data

def save_as_csv(data, filename):
    """将数据集保存为 CSV 格式"""
    with open(filename, 'w', newline='') as f:
        writer = csv.DictWriter(f, fieldnames=data[0].keys())
        writer.writeheader()
        writer.writerows(data)

if __name__ == "__main__":
    dataset = generate_dataset()
    save_as_csv(dataset, FILENAME)
    print(f"已在 {FILENAME} 中生成 {len(dataset)} 条记录")
```

## Example Dataset Specification（数据集规格示例）

**数据集类型：** 客户反馈

**列：**
- feedback_id（自增，U001、U002……）
- customer_name（真实姓名）
- email（有效邮箱格式）
- feedback_date（过去 90 天内的日期）
- rating（1-5 星）
- category（缺陷、功能请求、投诉、好评）
- text（真实的反馈内容）
- product（电子产品、服装、家居）

**约束条件：**
- 评分分布偏斜：40% 五星，30% 四星，20% 三星，10% 一二星
- 缺陷类别仅出现在 1-3 星评分中
- 功能请求仅出现在 3-5 星评分中
- 邮箱域名真实（gmail、yahoo、company.com）

## Output Deliverables（输出交付物）

- 可直接执行的 Python 脚本，或直接的数据文件
- 格式正确、带表头的 CSV 文件
- 结构有效、类型正确的 JSON 文件
- 可在数据库中直接执行的 SQL INSERT 语句
- 数据验证和约束条件合规
- 真实、符合业务实际的数据值
- 数据生成逻辑说明文档
- 快速上手使用指南

## Output Formats（输出格式）

**CSV：** 平面表格格式，易于导入电子表格和数据库

**JSON：** 嵌套结构，适用于 API 和 NoSQL 数据库

**SQL：** INSERT 语句，可直接在关系型数据库上执行

**Python 脚本：** 可执行的生成器，适用于自定义或大型数据集
