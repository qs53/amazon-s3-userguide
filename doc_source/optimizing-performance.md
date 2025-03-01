# Best practices design patterns: optimizing Amazon S3 performance<a name="optimizing-performance"></a>

Your applications can easily achieve thousands of transactions per second in request performance when uploading and retrieving storage from Amazon S3\. Amazon S3 automatically scales to high request rates\. For example, your application can achieve at least 3,500 PUT/COPY/POST/DELETE or 5,500 GET/HEAD requests per second per partitioned [prefix](https://docs.aws.amazon.com/general/latest/gr/glos-chap.html#keyprefix)\. There are no limits to the number of prefixes in a bucket\. You can increase your read or write performance by using parallelization\. For example, if you create 10 prefixes in an Amazon S3 bucket to parallelize reads, you could scale your read performance to 55,000 read requests per second\. Similarly, you can scale write operations by writing to multiple prefixes\. For more information about creating and using prefixes, see [Organizing objects using prefixes](using-prefixes.md)\.

Some data lake applications on Amazon S3 scan millions or billions of objects for queries that run over petabytes of data\. These data lake applications achieve single\-instance transfer rates that maximize the network interface use for their [Amazon EC2](https://docs.aws.amazon.com/ec2/index.html) instance, which can be up to 100 Gb/s on a single instance\. These applications then aggregate throughput across multiple instances to get multiple terabits per second\. 

Other applications are sensitive to latency, such as social media messaging applications\. These applications can achieve consistent small object latencies \(and first\-byte\-out latencies for larger objects\) of roughly 100–200 milliseconds\.

Other AWS services can also help accelerate performance for different application architectures\. For example, if you want higher transfer rates over a single HTTP connection or single\-digit millisecond latencies, use [Amazon CloudFront](https://docs.aws.amazon.com/cloudfront/index.html) or [Amazon ElastiCache](https://docs.aws.amazon.com/elasticache/index.html) for caching with Amazon S3\.

Additionally, if you want fast data transport over long distances between a client and an S3 bucket, use [Configuring fast, secure file transfers using Amazon S3 Transfer Acceleration](transfer-acceleration.md)\. Transfer Acceleration uses the globally distributed edge locations in CloudFront to accelerate data transport over geographical distances\. If your Amazon S3 workload uses server\-side encryption with AWS Key Management Service \(SSE\-KMS\), see [AWS KMS Limits](https://docs.aws.amazon.com/kms/latest/developerguide/limits.html) in the AWS Key Management Service Developer Guide for information about the request rates supported for your use case\. 

The following topics describe best practice guidelines and design patterns for optimizing performance for applications that use Amazon S3\. Refer to the [Performance Guidelines for Amazon S3](optimizing-performance-guidelines.md) and [Performance Design Patterns for Amazon S3](optimizing-performance-design-patterns.md) for the most current information about performance optimization for Amazon S3\. 

**Topics**
+ [Performance Guidelines](optimizing-performance-guidelines.md)
+ [Performance Design Patterns](optimizing-performance-design-patterns.md)

  
