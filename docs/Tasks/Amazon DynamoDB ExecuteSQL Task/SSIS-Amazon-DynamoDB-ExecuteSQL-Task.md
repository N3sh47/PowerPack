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

```h
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