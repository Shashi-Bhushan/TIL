# GetShardIterator error resolution

if you would get an error like this in reading Kinesis stream
```
ERROR worker.InitializeTask: Caught exception:
com.amazonaws.services.kinesis.model.InvalidArgumentException: StartingSequenceNumber 49551532098093284204238000035066183240246145871536717826 used in GetShardIterator on shard shardId-000000000000 in stream <AWS-Stream-Name> under account <AWS-Account-ID> is invalid because it did not come from this stream. (Service: AmazonKinesis; Status Code: 400; Error Code: InvalidArgumentException; Request ID: <REQUEST-ID>)
```

it's happening because you are using KCL, which internally uses DynamoDB table to maintain shard processing state. Basically, Amazon maintains a DynamoDB table associated with each application name, which stores information about the stream and the data the application has received or needs to receive.
In order to resolve the issue, you could 
- either change the application name. This will in turn create a new Dynamo DB table for maintaining shard processing state. 
- remove the row from Dynamo DB table.


