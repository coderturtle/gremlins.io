---
title: 'Static Sites'
weight: 2
draft: false
# search related keywords
keywords: ['static site', 's3', 'cloudfront', 'certificate manager']
---

### High Level Architecture & Flow

![Architecture](images/architecture.png 'Architecture')

1. The viewer requests the website at www.example.com.
2. If the requested object is cached, CloudFront returns the object from its cache to the viewer.
3. If the object is not in CloudFront’s cache, CloudFront requests the object from the origin (an S3 bucket).
4. S3 returns the object to CloudFront, which triggers the Lambda@Edge origin response event.
5. The object, including the security headers added by the Lambda@Edge function, is added to CloudFront’s cache.
6. (Not shown) The objects is returned to the viewer. Subsequent responses for the object are served from the CloudFront cache.

[![Launch CFN stack](https://s3.amazonaws.com/cloudformation-examples/cloudformation-launch-stack.png)](https://console.aws.amazon.com/cloudformation/home?region=us-east-1#/stacks/new?templateURL=https://s3.amazonaws.com/solution-builders-us-east-1/amazon-cloudfront-secure-static-site/latest/main.yaml)

### Dive deeper into the architecture

To dive deeper into the architecture and build out the solution yourself please checkout cloud gremlins [Static sites architectural Walkthrough](https://gremlins.io/cloud/static-sites)
