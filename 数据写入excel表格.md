## 1、创建文件
```python
from openpyxl import Workbook
wb = Workbook()
# 获取当前actice的sheet
ws = wb.active
ws.title = "salary"
wb.save("文件名")
```
## 2、打开已有文件
```python
from openpyxl import load_workbook
wb = load_workbook('文件名')
```
## 3、获取目前最大行数、列数
```python
# 最大列
ws.max_col
# 最大行
ws.max_row
```
## 4、写入数据
```python
ws.cell(row,col,calue)
```
## 5、按行遍历
```python
# 第一种方法，按行遍历每一个单元格的值
for row in ws:      # 循环获取表数据
    for cell in row:   #循环获取每个单元格数据
        print(cell.value,end='')
# 第二种方法，遍历指定的行和列
#遍历第2行到第5行的前10列
for row in ws.iter_rows(min_row=2, max_row=5, max_col=10):
    for cell in row:
        print(cell.value, end=",")
    print()
```
## 6、按列遍历
```python
# 遍历顺序，大概就像是A1,A2,A3这样的顺序
for column in sheet.columns:
    for cell in column:
        print(cell.value, end=",")
```