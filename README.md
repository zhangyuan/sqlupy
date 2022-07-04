# sqlupy

## Install

```
pip install sqlupy
```

## Example

```
>>> import sqlupy
>>> sqlupy.parse("pg", "select * from users")
[{'Query': {'body': {'Select': {'cluster_by': [], 'distinct': False, 'distribute_by': [], 'from': [{'joins': [], 'relation': {'Table': {'alias': None, 'args': None, 'name': [{'quote_style': None, 'value': 'users'}], 'with_hints': []}}}], 'group_by': [], 'having': None, 'into': None, 'lateral_views': [], 'projection': ['Wildcard'], 'qualify': None, 'selection': None, 'sort_by': [], 'top': None}}, 'fetch': None, 'limit': None, 'lock': None, 'offset': None, 'order_by': [], 'with': None}}]
>>> sqlupy.parse("pg", "SELECT depname, empno, salary, rank() OVER (PARTITION BY depname ORDER BY salary DESC) from empsalary")
[{'Query': {'body': {'Select': {'cluster_by': [], 'distinct': False, 'distribute_by': [], 'from': [{'joins': [], 'relation': {'Table': {'alias': None, 'args': None, 'name': [{'quote_style': None, 'value': 'empsalary'}], 'with_hints': []}}}], 'group_by': [], 'having': None, 'into': None, 'lateral_views': [], 'projection': [{'UnnamedExpr': {'Identifier': {'quote_style': None, 'value': 'depname'}}}, {'UnnamedExpr': {'Identifier': {'quote_style': None, 'value': 'empno'}}}, {'UnnamedExpr': {'Identifier': {'quote_style': None, 'value': 'salary'}}}, {'UnnamedExpr': {'Function': {'args': [], 'distinct': False, 'name': [{'quote_style': None, 'value': 'rank'}], 'over': {'order_by': [{'asc': False, 'expr': {'Identifier': {'quote_style': None, 'value': 'salary'}}, 'nulls_first': None}], 'partition_by': [{'Identifier': {'quote_style': None, 'value': 'depname'}}], 'window_frame': None}}}}], 'qualify': None, 'selection': None, 'sort_by': [], 'top': None}}, 'fetch': None, 'limit': None, 'lock': None, 'offset': None, 'order_by': [], 'with': None}}]
```
