# Nested Stacks in CloudFormation

This guide is a painstakingly detailed walkthrough on how to make a nested CloudFormation stack.

## Who this is for

People who are tired of other walkthroughs being too brief. So many tutorials passover what they deem to be miniscule details which not eveyone is aware of.

## Getting Started

You can clone or fork [this] repository. It's a NodeJS runtime, and has 2 branches.

- `starter` which just has a skeleton of a project
  - Minimal comments, basically just the bare bones
- `finished` a completed project for reference
  - Heavily commented, which explicit details
  - If you don't like specific things or explanations which you already may or may not know, this isn't the guide for you

Or

You can obviously just make your own

## Setup

Technically this can be done with just one S3 bucket. It's nice to separate the 2 templates, so I'd recommend making 2.

### S3 Buckets

Make the 1st bucket to house your templates. Name it something like `master-templates` or `output-templates`, whatever.

The second bucket is for housing your packaged code. This bucket contains your packaged runetime code for the lambdas to execute.

The second bucket will contain a bunch of random key names, and will mostly just be for reading.

### Templates
