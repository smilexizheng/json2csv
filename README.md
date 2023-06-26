# Json2Csv
js html 实现的一款通用型JSON数据提取工具，支持自动识别JSON数据节点并有序提取为CSV文件。  
Convenient JSON data extraction tool.

# 使用简介
1. 数据路径：设置Json中数据所处路径，如'root.topics.data'  'data.items' ...
   
2. 字段解析：为空则为全量解析，自动识别字段头。可自定义 排序、映射、按需导出csv文件。

   * 假设数据
        *  [{"id":1,"name":"张三","age":19},{"id":2,"name":"李四","age":20}]
   * 按需排序 字段名逗号隔开（支持,隔开的字符串/数组格式)
        * name,id,age / ["age","name","id"]
   * 字段映射csv头 排序+按需导出 ，移除id列
        * {name:"名字",age:'年龄'}
3. 添加csv头：选择框 csv第一行是否包含字段信息。  

## 支持以下常见JSON数据格式：
> 拖放json文件到上传框内，生成为同名csv文件，支持多文件。
### 2.*任意多级节点下的数组数据*
```json
{"data":{"items":[{"title":"one","price":23},{"title":"two","price":92},{"title":"three","price":5623}]}}
```
### 3.*兼容处理数据区域非数组结构而是一个对象的情况*
```json
{"data":{"items":{"1":{"title":"one","name":"test1"},"2":{"title":"two","name":"test2"},"3":{"title":"three","name":"test3"}}}}
```  
数据位于"data.items"多级节点下，则填写【数据路径】，如`data.items`
![img.png](img.png)

本地测试，秒级处理20M json文件，Chrome 版本 114.0.5735.134（正式版本） （64 位）
![img_1.png](img_1.png)


