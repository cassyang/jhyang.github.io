### pymongoѧϰ

#### ����һ�����ݿ�
```python
#!/usr/bin/python3

import pymongo

myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["dbname"]
```
��monogodb�У�ֻ�������ݿ��в������ݺ󣬲Żᴴ�����ͻ��ˡ�����Ҫ����CollectionȻ�����һ��document�����ݿ�Ż�����������

#### �ж����ݿ��Ƿ����
```python
#!/usr/bin/python3

import pymongo

dblist = myclient.list_database_names()
# dblist = myclient.database_names() ��Python3.7+ʱ��������÷���
```

#### �ж�Collection�Ƿ����

```python
#!/usr/bin/python3

import pymongo

myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["dbname"]

collist = mydb.list_collection_names()
# collist = mydb.collection_names() ��Python3.7+ʱ��������÷���

if "testcollection" not in collist:
	mycol = mydb["testcollection"]
else:
	print("Collection is Exist!")
```

��������
---
- �����в����ĵ�ʹ��insert_one()������������dict(key, value).
```python
#!/usr/bin/python3

import pymongo

myclient = pymongo.MongoClient("mongodb://localhost:27017/")
mydb = myclient["mydb"]
mycol = mydb["mycol"]

mydict = {"name": "test", "score": 100}

x = mycol.insert_one(mydict)
# x��һ��InsertOneResult���󣬰���inserted_id���ԣ����ǲ����ĵ���idֵ
print(x.inserted_id) # �������_id,�������documentʱû��ָ��_id��MongoDB��Ϊÿ���ĵ����һ��Ψһ��id
```
- �������ĵ�ʹ��insert_many()�������÷����ĵ�һ������[{...}, {...}]
```python
x = mycol.insert_many(myList)
# �������������ĵ���Ӧ�� _id ֵ
print(x.inserted_ids)
```
- ��ʾ������_id
{"_id" : 1, "name" : balabala, ...}ֻ����dict�ж���"_id"���ɡ�

��ѯ����
---
- ��ѯһ������find_one()���������Բ�ѯcollection�еĵ�һ�����ݡ�
- find()�������Բ�ѯcollentcion�е��������ݣ�����SELECT *
- ָ���ֶβ�ѯ������Ҫ���ص�ֵ��Ϊ1.
	``mycol.find({}, {"_id": 0, "name": 1, "class": 1})``
	������ѯ���ؽ���᷵��name��class��������_id.
	* �ر��ֻ��_id֮�⣬������ͬһ��������ͬʱָ��0��1�����������һ���ֶ�Ϊ0����������Ϊ1��
- ָ��������ѯ����find�����ò��������ˡ�
	``mycol.find({"name" : "jhyang"})``
- �߼���ѯ�����ѯ����"H"��ֵ��{"$gt" : "H"}
- Ҳ��ʹ��������ʽ����ѯ������{"$regex" : "^H"}
- ���Ʒ�����Ŀ��ʹ��limit()������
	``mycol.find().limit(3)``

�޸�����
---
..

