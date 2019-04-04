# CloudWatchLogs-Export

## Description
Create AWS Step Functions State Machine at AWS CloudFormation.

State Machine export all CloudWatch Logs Log Groups to S3.

All Log Groups in the same region as State Machine are exported.

The export time range is from 9:00 (UTC) yesterday to 9:00 (UTC) today.

## Usage

### 1. Upload CloudFormation Template
"CWLogs-Export.yml"

### 2. Create and Enter Parameter to CloudFormation Stack
If Create New S3 Bucket:
* CreateNewS3Bucket：true
* DestinationS3BucketName：<font color="Red">NewBucketName</font>

If Use Existing S3 Bucket:
* CreateNewS3Bucket：false
* DestinationS3BucketName：<font color="Red">ExistingBucketName</font>

!! The Bucket Policy settings are required for the existing S3 Bucket. Please see belew
https://docs.aws.amazon.com/ja_jp/AmazonCloudWatch/latest/logs/S3ExportTasksConsole.html#S3PermissionsConsole

### 3. Execute State Machine
Execute State Machine "CloudWatchLogs-ExportJob-(Region name)".

### 4. (Option) Export the log of the specified date
Can be exported by passing the date to be exported as an Input Parameter.


    {
      "TargetDate": "2018-08-20"
    }

## License
This software is released under the MIT License, see LICENSE.