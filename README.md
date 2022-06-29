# sqlupy

## Install

```
pip install sqlupy
```

## Example

```
>>> import sqlupy
>>> sqlupy.parse("pg", "select * from users")
'[{"Query":{"body":{"Select":{"cluster_by":[],"distinct":false,"distribute_by":[],"from":[{"joins":[],"relation":{"Table":{"alias":null,"args":null,"name":[{"quote_style":null,"value":"users"}],"with_hints":[]}}}],"group_by":[],"having":null,"into":null,"lateral_views":[],"projection":["Wildcard"],"qualify":null,"selection":null,"sort_by":[],"top":null}},"fetch":null,"limit":null,"lock":null,"offset":null,"order_by":[],"with":null}}]'
>>> import json
>>> json.loads(sqlupy.parse("pg", "select * from users"))
[{'Query': {'body': {'Select': {'cluster_by': [], 'distinct': False, 'distribute_by': [], 'from': [{'joins': [], 'relation': {'Table': {'alias': None, 'args': None, 'name': [{'quote_style': None, 'value': 'users'}], 'with_hints': []}}}], 'group_by': [], 'having': None, 'into': None, 'lateral_views': [], 'projection': ['Wildcard'], 'qualify': None, 'selection': None, 'sort_by': [], 'top': None}}, 'fetch': None, 'limit': None, 'lock': None, 'offset': None, 'order_by': [], 'with': None}}]
```
