Week 2:

The S3 uploader policy allows updates, additions, and reads related to any object within the S3 bucket associated with my name. It was scoped this way to allow access to objects within the bucket following least privilege. This is important because if the ARN does not contain the suffix "/*", the ARN identifies the bucket itself and not objects inside of it. 