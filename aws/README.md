## What is Boto3?

Boto3 is the AWS SDK for Python. It enables Python Developers to create, configure and manage AWS services, such as Amazon EC2 and Amazon S3. Boto3 provides an easy-to-use, object-oriented API, as well as a low-level access to AWS services.

## Install Boto3 Package

```
pip3 install boto3
```

## Configure AWS CLI

**Default:**

```
aws configure
```

**Custom:**

```
aws configure --profile $profile
```

## Usage

```
import boto3
```

### Creating a Custom Session

Session refers to AWS Management Console access

```
session = boto3.session.Session(profile_name="$profile_name")
```

## Client vs Resources

### Client

-   Original boto3 API abstraction
-   Provides low-level AWS service access
-   All AWS service operations are supported by clients

### Resource

-   Newer boto3 API abstraction
-   Provides high-level, object-oriented API
-   Does not provide 100% API coverage of AWS services

## Waiters

Allows you to block code until a process is complete.

## Paginator

When using the `Client` certains operations returns incomplete results, to get the complete results you need to send subsequent

### Limits

**Default:** 50
**IAM:** 100
**S3:** 1000

## Meta

Meta allows you to access Client only methods when using Resource

```
import boto3

ec2 = boto3.resource('ec2')

regions = ec2.meta.client.describe_regions()
```
