---
sidebar_position: 3
sidebar_label: 'SSIS Amazon DynamoDB ExecuteSQL Task'
---

![DynamoDB](/img/ssis-amazon-dynamodb-executesql-task.png)

export const Highlight = ({children, color}) => (
  <span
    style={{
      backgroundColor: color,
      borderRadius: '2px',
      color: '#fff',
      padding: '0.2rem',
    }}>
    {children}
  </span>
);


Amazon DynamoDB ExecuteSQL Task can be used to execute ad-hoc commands for DynamoDB (e.g. DDL statements such as Create/Alter/Drop Table, DML statements such as Insert, Update, Delete records)

<a href="https://zappysys.com/products/ssis-powerpack/" ><Highlight color="#25c2a0">Download</Highlight></a>


## Content

- Video Tutorial
- Step-By-Step
- Properties
- Setting UI
- Examples
- See Also
- References

## Video Tutorial

Coming soon...

## Step-By-Step

In this tutorial you will learn how to Create Amazon DynamoDB Table with Indexes and read/write throughput rate using ZS Amazon DynamoDB ExecuteSql Task with few clicks.
1. Firstly, In order to connect to Amazon Storage for DynamoDb from SSIS you will need Credentials. Ask your SysAdmin or responsible person to provide that to you. Your keys will look something like this: (this is just example key which may differ in your case).

Read more for How to get your AccessKey and Secret Key [click here.](https://docs.aws.amazon.com/AWSSimpleQueueService/latest/SQSDeveloperGuide/sqs-getting-started.html)


```
AccessKey: AKIAIOSFODNN7EXAMPLE
SecretKey: wJalrXUtnFEMI/K7MDENG/bPxRfiCYEXAMPLEKEY
```

2. Now Download and Install SSIS ZappySys PowerPack.
3. Once you have Access Key and Secret Key, you may proceed to create new SSIS package. In BIDS/SSDT create new SSIS package Project
4. In Visual Studio, from SSIS Toolbox drag and drop the ZS Amazon DynamoDB ExecuteSql Task in the design pane and double click on the task to configure it:

![AMAZON](/img/drag-Amazon-DynamoDB-ExecuteSQL-Task.png)


**How to Create AWS-Storage Connection.**

1. Right click on Connection Managers Panel to Create New ZS-AWS-Storage, and Context Menu will appear, Select New Connection from the Context Menu.

![Connection](/img/ssis-new-connection.png)

2. Select ZS-AWS-Storage Connection Manager from the Connection Managers list and Click on Add Button.

![Red Shift](/img/amazon-redshift-connection-2.png)

3. On Connection Manager UI, Select DynamoDB in Storage Service and Enter your Amazon DynamoDB Access Key and Secret Key and leave all other properties as it is, and Click Test Connection, If test successful then hit OK to close the connection manager dialog box.

![Storage](/img/amazon-storage-dynamodb-create-connection.png)


**How to Create Table using Amazon DynamoDB ExecuteSQL Task.**

1. Double click on Amazon DynamoDb ExecuteSQL Task to configure it.
2. Select Connection, set SQL Source type to DirectValue and CommandType to CreateTable.
Note : Replace Table Name.

```console
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_CreateTable.html */
    TableName: 'Thread',
    Wait : true, /* Wait until table status is ACTIVE */ 
    AttributeDefinitions: [
        /*Below two columns used in Composite Primary Key */
        {
            AttributeName: 'ForumName',
            AttributeType: 'S'
        },
        {
            AttributeName: 'PostId',
            AttributeType: 'N'
        }
    ],
    KeySchema: [
        {
            AttributeName: 'ForumName',
            KeyType: 'HASH'
        },
        {
            AttributeName: 'PostId',
            KeyType: 'RANGE'
        }
    ],
    ProvisionedThroughput: {
        ReadCapacityUnits: 5,
        WriteCapacityUnits: 5
    }
}
```



![SSIS Amazon](/img/ssis-amazon-dynamodb-create-table-request.png)

3. Finally, you can run by press Test / Preview button or hit on OK button and Execute Package.

![SSIS Amazon](/img/run-amazon-dynamoDb-task.png)




## Properties
### Property Name
### ResultsetType

ResultSet Type. It can be None, FullResultset or SingleValue. When FullResultset is specified then you have to store result in Object type variable. Full result is ADO.net DataTable. SingleValue is Object datatype


<details>
  <summary>Available Options</summary>
  <div>
    <br/>
    <div>
        Use numeric value listed in bracket if you have to <a href="https://zappysys.com/links/?id=10099">define expression</a> on this property (for dynamic behavior).
      </div>
  </div>
</details>

| Option                           | Description    |
|----------------------------------|----------------|
| None [0](https://zappysys.com/links/?id=10099)          | None           |
| FullResultset [1](https://zappysys.com/links/?id=10099) | FullResultset  |
| SingleValue [2](https://zappysys.com/links/?id=10099)   | SingleValue    |
| RawResult [4](https://zappysys.com/links/?id=10099)     | RawResult      |


### CommandType

Source of SQL Statement. It can be DirectValue or Variable

<details>
  <summary>Available Options</summary>
  <div>
    <br/>
    <div>
        Use numeric value listed in bracket if you have to <a href="https://zappysys.com/links/?id=10099">define expression</a> on this property (for dynamic behavior).
      </div>
  </div>
</details>


| Option                                    | Description     |
|-------------------------------------------|-----------------|
| CreateTable [0](https://zappysys.com/links/?id=10099)          | CreateTable       |
| CreateTableSafe [1](https://zappysys.com/links/?id=10099)      | CreateTableSafe   |
| DeleteTable [2](https://zappysys.com/links/?id=10099)          | DeleteTable       |
| DeleteTableSafe [3](https://zappysys.com/links/?id=10099)      | DeleteTableSafe   |
| BatchInsert [4](https://zappysys.com/links/?id=10099)          | BatchInsert       |
| BatchDelete [5](https://zappysys.com/links/?id=10099)          | BatchDelete       |
| PutItem [7](https://zappysys.com/links/?id=10099)              | PutItem           |
| DeleteItem [8](https://zappysys.com/links/?id=10099)           | DeleteItem        |
| UpdateItem [9](https://zappysys.com/links/?id=10099)           | UpdateItem        |
| Query [10](https://zappysys.com/links/?id=10099)               | Query             |
| ListTables [11](https://zappysys.com/links/?id=10099)          | ListTables        |
| UpdateTable [12](https://zappysys.com/links/?id=10099)         | UpdateTable       |
| DescribeTable [13](https://zappysys.com/links/?id=10099)       | DescribeTable     |


### SqlStatementSourceType

Source of SQL Statement. It can be DirectValue or Variable

<details>
  <summary>Available Options</summary>
  <div>
    <br/>
    <div>
        Use numeric value listed in bracket if you have to <a href="https://zappysys.com/links/?id=10099">define expression</a> on this property (for dynamic behavior).
      </div>
  </div>
</details>

| Option                              | Description   |
|-------------------------------------|---------------|
| DirectValue [0](https://zappysys.com/links/?id=10099)  | DirectValue   |
| Variable [1](https://zappysys.com/links/?id=10099)     | Variable      |





### ResultsetVariable

Variable name which will store Full resultset (ADO.net DataTable) or single value of result. Variable type must be object datatype if storing full resultset

### Timeout	

Command timeout in second. 0 means no command timeout

### SqlStatementSource	

If SqlSourceType=DirectValue then this property holds SQL Statement.
### SqlStatementVariable	

If SqlSourceType=Variable then this property holds Variable name which where SQL statement is stored

### Connection	

Connection where you want to execute sql command

### LoggingMode

<details>
  <summary>Available Options</summary>
  <div>
    <br/>
    <div>
        Use numeric value listed in bracket if you have to <a href="https://zappysys.com/links/?id=10099">define expression</a> on this property (for dynamic behavior).
      </div>
  </div>
</details>

| Option                               | Description |
|--------------------------------------|-------------|
| Normal [0](https://zappysys.com/links/?id=10099)     | Normal      |
| Medium [1](https://zappysys.com/links/?id=10099)     | Medium      |
| Detailed [2](https://zappysys.com/links/?id=10099)   | Detailed    |
| Debugging [3](https://zappysys.com/links/?id=10099)  | Debugging   |



### PrefixTimestamp

When you enable this property it will prefix timestamp before Log messages.

## Setting UI

![Amazon DynamoDB](/img/amazon-dynamodb-executesql-settingui-1.png)

![Amazon DynamoDB](/img/amazon-dynamodb-executesql-settingui-2.png)

#### Examples

**`[CreateTable]`: Create new table**


This example shows how to create new DynamoDB table with minimum required options. Create table may take few seconds or minutes to provision resources on AWS cloud. See below link for more information on each parameter for CreateTable command http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_CreateTable.html

```html
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_CreateTable.html */
    TableName: 'Thread',
    Wait : true, /* Wait until table status is ACTIVE */ 
    AttributeDefinitions: [
        /*Below two columns used in Composite Primary Key */
        {
            AttributeName: 'ForumName',
            AttributeType: 'S'
        },
        {
            AttributeName: 'PostId',
            AttributeType: 'N'
        }
    ],
    KeySchema: [
        {
            AttributeName: 'ForumName',
            KeyType: 'HASH'
        },
        {
            AttributeName: 'PostId',
            KeyType: 'RANGE'
        }
    ],
    ProvisionedThroughput: {
        ReadCapacityUnits: 5,
        WriteCapacityUnits: 5
    }
}
```

**`[CreateTable]`: Create new table with Local secondary index**

This example shows how to create new DynamoDB table with minimum required options. Create table may take few seconds or minutes to provision resources on AWS cloud. See below link for more information on each parameter for CreateTable command http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_CreateTable.html

```html
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_CreateTable.html */
    TableName: 'Thread',
    Wait: true, /* Wait until table status is ACTIVE */ 
    AttributeDefinitions: [
        /*Below two columns used in Composite Primary Key */
        {
            AttributeName: 'ForumName',
            AttributeType: 'S'
        },
        {
            AttributeName: 'PostId',
            AttributeType: 'N'
        },
        /*Below used in Index*/
        {
            AttributeName: 'LastPostDateTime',
            AttributeType: 'S'
        }
    ],
    KeySchema: [
        {
            AttributeName: 'ForumName',
            KeyType: 'HASH'
        },
        {
            AttributeName: 'PostId',
            KeyType: 'RANGE'
        }
    ],
    LocalSecondaryIndexes: [
        {
            IndexName: 'LastPostIndex',
            KeySchema: [
                {
                    AttributeName: 'ForumName',
                    KeyType: 'HASH'
                },
                {
                    AttributeName: 'LastPostDateTime',
                    KeyType: 'RANGE'
                }
            ],
            Projection: {
                ProjectionType: 'KEYS_ONLY'
            }
        }
    ],
    ProvisionedThroughput: {
        ReadCapacityUnits: 5,
        WriteCapacityUnits: 5
    }
}
```

**`[CreateTableSafe]`: Create new table (If not exist)**

This example shows how to create new DynamoDB table only if table does not exist. If table is already found then command is ignored without throwing error. Create table may take few seconds or minute to provision resources on AWS cloud. See below link for more information on each parameter for CreateTable command http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_CreateTable.html


```html
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_CreateTable.html */
    TableName: 'Thread',
    Wait : true, /* Wait until table status is ACTIVE */ 
    AttributeDefinitions: [
        /*Below two columns used in Composite Primary Key */
        {
            AttributeName: 'ForumName',
            AttributeType: 'S'
        },
        {
            AttributeName: 'PostId',
            AttributeType: 'N'
        }
    ],
    KeySchema: [
        {
            AttributeName: 'ForumName',
            KeyType: 'HASH'
        },
        {
            AttributeName: 'PostId',
            KeyType: 'RANGE'
        }
    ],
    ProvisionedThroughput: {
        ReadCapacityUnits: 5,
        WriteCapacityUnits: 5
    }
}
```

**`[UpdateTable]`: Update table read/write throughput setting**

This example shows how to change table read/write throughput setting. See below link for more information on each parameter for CreateTable command http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_UpdateTable.html

```html
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_UpdateTable.html */
    /* Wait until table is back to ACTIVE status after you change something e.g. Index, Provision Throughput etc. */
    Wait: true,
    TableName: 'Thread',
    ProvisionedThroughput: {
        ReadCapacityUnits: 6,
        WriteCapacityUnits: 6
    }
}
```

**`[UpdateTable]`: Update/Delete/Add global secondary index**

This example shows how to update global secondary index of table. See below link for more information on each parameter for CreateTable command http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_UpdateTable.html


```html
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_UpdateTable.html */
    Wait: true, /* Wait until table status is ACTIVE */ 
    TableName: 'Thread',
    AttributeDefinitions: [
        {
            AttributeName: 'PostCategory',
            AttributeType: 'S'
        },
        {
            AttributeName: 'Author',
            AttributeType: 'S'
        }
    ],
    
    GlobalSecondaryIndexUpdates: [
        {
            Create:
            {
                IndexName: 'PostCategoryIndex',
                KeySchema: [
                    {
                        AttributeName: 'PostCategory',
                        KeyType: 'HASH'
                    },
                    {
                        AttributeName: 'Author',
                        KeyType: 'RANGE'
                    }
                ],
                Projection: {
                    ProjectionType: 'KEYS_ONLY'
                }
            }
        }
        /*
        ,
        {   
            Update:
            {
                IndexName: 'SomeExistingGSIndex',
                ProvisionedThroughput: {
                    ReadCapacityUnits: 6,
                    WriteCapacityUnits: 6
                }    
            }
        }
        */
    ]
}
```

**`[DeleteTable]`: Delete table**

This example shows how to delete DynamoDB table. Delete table may take few seconds or minutes if you running this against AWS cloud (not local emulator). See below link for more information on each parameter for CreateTable command http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DeleteTable.html

```html
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DeleteTable.html */
    TableName: 'Thread',
    Wait: true /* Use this option to wait until operation is done */
}
```

**`[DeleteTableSafe]`: Delete Table (If exists)**

This example shows how to delete DynamoDB table if exists. If table is not found then command is ignored without throwing error. Delete table may take few seconds or minutes if you running this against AWS cloud (not local emulator). See below link for more information on each parameter for CreateTable command http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DeleteTable.html

```html
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DeleteTable.html */
    TableName: 'Thread',
    Wait: true /* Use this option to wait until operation is done */
}
```

**`[ListTables]`: List tables**

This example shows how to get list of tables http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_ListTables.html

```html
{
    /*For more info visit : http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_ListTables.html */
}
```

**`[DescribeTable]`: Get table detail (DescribeTable)**

This example shows how to get table information (e.g. Row Count, Size) http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DescribeTable.html
/*For more info check: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DescribeTable.html */

```html
{
    TableName: 'Thread'
    /*Use below attribute to get only single attribute. For more information on how to write JSON Path filter check this link: http://goessner.net/articles/JsonPath/
    PropertyFilter: 'Table.ItemCount'
    */
}
```

**`[DescribeTable]`: Get table row count (DescribeTable)**

This example shows how to get table row count. Table row count may not be upto date sometime because DynamoDB may update this information periodically http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DescribeTable.html
/*For more info check: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DescribeTable.html */

```html
{
    TableName: 'Thread',
    /*For more information on how to write JSON Path filter check this link: http://goessner.net/articles/JsonPath/ */
    PropertyFilter: 'Table.ItemCount'
}
```

**`[DescribeTable]`: Get table size in bytes (DescribeTable)**

This example shows how to get table size in bytes. Table size may not be upto date sometime because DynamoDB may update this information periodically http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DescribeTable.html
/*For more info check: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DescribeTable.html */

```html
{
    TableName: 'Thread',
    /*For more information on how to write JSON Path filter check this link: http://goessner.net/articles/JsonPath/ */
    PropertyFilter: 'Table.TableSizeBytes'
}
```

**`[DescribeTable]`: Get index size in bytes (DescribeTable)**

This example shows how to get index size in bytes. This information may not be upto date sometime because DynamoDB may update this periodically http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DescribeTable.html
/*For more info check: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DescribeTable.html */

```html
{
    TableName: 'Thread',
    /*For more information on how to write JSON Path filter check this link: http://goessner.net/articles/JsonPath/ */
    PropertyFilter: '$.Table.LocalSecondaryIndexes[?(@IndexName=='LastPostIndex')].IndexSizeBytes'
}
```






**`[PutItem]`: PutItem (Insert with more options)**

This example shows how to insert single document into DynamoDB table. http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_PutItem.html
/*For more info check: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_PutItem.html */

```html
{
    "TableName": "Thread",
    "Item": {
        "LastPostDateTime": {
            "S": "201303190422"
        },
        "Tags": {
            "SS": ["Update","Multiple Items","HelpMe"]
        },
        "ForumName": {
            "S": "Amazon DynamoDB"
        },
        "PostId": {
            "N": 100
        },
        "Message": {
            "S": "I want to update multiple items in a single API call. What's the best way to do that?"
        },
        "Subject": {
            "S": "How do I update multiple items?"
        },
        "LastPostedBy": {
            "S": "fred@example.com"
        }
    },
    "ConditionExpression": "ForumName <> :f and Subject <> :s",
    "ExpressionAttributeValues": {
        ":f": {"S": "Amazon DynamoDB"},
        ":s": {"S": "How do I update multiple items?"}
    }
}
```


**`[DeleteItem]`: DeleteItem (Delete with more options)**

This example shows how to delete single document from DynamoDB table. http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DeleteItem.html
/*For more info check: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_DeleteItem.html */

```html
{
    "TableName": "Thread",
    "Key": {
        "ForumName": {
            "S": "Amazon DynamoDB"
        },
        "PostId": {
            "N": 100
        }
    },
    "ConditionExpression": "attribute_not_exists(Replies)",
    "ReturnValues": "ALL_OLD"
}
```



**`[UpdateItem]`: UpdateItem (Update document with more options)**

This example shows how to update single document. http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_UpdateItem.html
/*For more info check: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_UpdateItem.html */

```html
{
    "TableName": "Thread",
    "Key": {
        "ForumName": {
            "S": "Amazon DynamoDB"
        },
        "PostId": {
            "N": 100
        }
    },
    "UpdateExpression": "set LastPostedBy = :val1",
    "ConditionExpression": "LastPostedBy = :val2",
    "ExpressionAttributeValues": {
        ":val1": {"S": "alice@example.com"},
        ":val2": {"S": "fred@example.com"}
    },
    "ReturnValues": "ALL_NEW"
}
```

**`[UpdateItem]`: UpdateItem (When Column name is DynamoDB Reserved Word)**

This example shows how to update document when column name is one of the reserved words in DynamoDB. http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_UpdateItem.html
/*
For more info check: http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_UpdateItem.html 
List of reserved words: http://docs.aws.amazon.com/amazondynamodb/latest/developerguide/ReservedWords.html
*/

```html
{
    "TableName": "Thread",
    "Key": {
        "ForumName": {
            "S": "Amazon DynamoDB"
        },
        "PostId": {
            "N": 100
        }
    },
    "UpdateExpression": "set #P = :val1",
    "ConditionExpression": "LastPostedBy = :val2",
    "ExpressionAttributeNames": {
        "#P": {"S": "Status"}
    },
    "ExpressionAttributeValues": {
        ":val1": {"S": "Success"},
        ":val2": {"S": "fred@example.com"}
    },
    "ReturnValues": "ALL_NEW"
}
[BatchInsert]: Bulk Insert (Multiple documents)
This example shows how to insert multiple documents (If you need advanced option for insert then check PutItem command).
{
    TableName: 'Thread',
    Items: [
        {ForumName: 'Product 1',Subject:'How to return item?',PostId:1, LastPostDateTime:'2015-01-01',PostCategory:'Product',Tags:['Tag1','Tag2','Tag3'], Cost: 1200.50 },
        {ForumName: 'Product 1',Subject:'How to order item?',PostId:2,LastPostDateTime:'2015-01-02',PostCategory:'Product',Tags:['Tag2','Tag3'], Cost: 100.50 },
        {ForumName: 'Service 1',Subject:'How to use item?',PostId:1,LastPostDateTime:'2015-01-03',PostCategory:'Service',Tags:[]}
    ]
}
```


**`[BatchDelete]`: Bulk delete (Multiple documents)**

This example shows how to delete multiple documents. Just include key columns in the JSON documents and it will delete matching documents. (If you need advanced option for insert then check DeleteItem command).

```html
{
    TableName: 'Thread',
    Items: [
        {ForumName: 'Product 1',PostId:1},
        {ForumName: 'Service 1',PostId:1}
    ]
}
```


**`[Query]`: Query documents (In SCAN mode)**

This example shows how to query DynamoDB documents with simple SQL like query. This example uses SCAN API which means you can query on any field without needing index but this type of requests are expensive. For more information about SCAN mode visit this link http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Scan.html

```html
SELECT top 10 * 
FROM Thread 
WHERE Subject LIKE 'H%'
WITH (SCAN)
[Query]: Query documents (In QUERY mode)
This example shows how to query DynamoDB documents with simple SQL like query. This example uses QUERY API which means you must HASH column in Where condition. For more information about QUERY mode visit this link http://docs.aws.amazon.com/amazondynamodb/latest/APIReference/API_Query.html
SELECT top 10 * 
FROM Thread 
WHERE ForumName = 'Product 1' AND PostId >= 1 
WITH (QUERY)
```


## See Also

- [SSIS JSON Source Connector](https://zappysys.com/onlinehelp/ssis-powerpack/scr/json-source.htm)
- [SSIS Export JSON File Task](https://zappysys.com/onlinehelp/ssis-powerpack/scr/export-json-file-task.htm)
- [SSIS MongoDB Source Adapter](https://zappysys.com/onlinehelp/ssis-powerpack/scr/mongodb-source.htm)
- [SSIS Azure Table Storage Source Adapter](https://zappysys.com/onlinehelp/ssis-powerpack/scr/azure-table-storage-source.htm)
- [SSIS Amazon S3 Storage Task](https://zappysys.com/onlinehelp/ssis-powerpack/scr/amazon-s3-storage-task.htm)
- [SSIS Amazon Storage Connection Manager](https://zappysys.com/onlinehelp/ssis-powerpack/scr/amazon-storage-connection-manager.htm)


## Articles / Tutorials

