# Thoughts on AWS Lambda Usage

## New Uses

### Aliasing

- allow A / B testing by splitting traffic between 2 versioned Lamabdas
  - does not allow `$latest`, publish `$latest` to use it
