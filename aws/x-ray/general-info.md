# X-Ray

A monitoring tool for tracing the paths of your infastructure

## Cost

## Implementation

X-ray exists as a layer on top of your existing code base. It comes in the form of an SDK.

For Lambda the SDK is optional, but is helpful in configuring the monitoring

### Plugins

If you are using X-Ray with a non-serverless architecture, you need to configure the plug ins. There are 3 possible options right now, EC2, EBS, and ECS

Plug in the config service as follows:

`AWSXRay.config([AWSXRay.plugins.EC2Plugin,AWSXRay.plugins.ElasticBeanstalkPlugin]);`

### Lambda

To use the X-Ray SDK on Lambda, bundle it with your function code each time you create a new version. You can instrument your Lambda functions with the same methods that you use to instrument applications running on other services.

The primary difference is that you don't use the SDK to instrument incoming requests, make sampling decisions, and create segments.

#### Tracing

[Tracing Methods](https://docs.aws.amazon.com/lambda/latest/dg/enabling-x-ray.html#lambda-xray-tracing)

### Build

[Sam supports X-Ray](https://aws.amazon.com/about-aws/whats-new/2017/06/aws-serverless-application-model-aws-sam-now-supports-x-ray/) now.

- [Using !ref to access resources dynamically](https://docs.aws.amazon.com/lambda/latest/dg/enabling-x-ray.html#lambda-xray-tracing)
