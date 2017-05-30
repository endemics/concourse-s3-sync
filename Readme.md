# S3 Sync resource

Reverse-engineered from [`tobyirvine/concourse-s3-sync` docker image](https://hub.docker.com/r/tobyirvine/concourse-s3-sync/).

## Source Configuration

- `access_key_id`: Your AWS access key ID.

- `secret_access_key`: Your AWS secret access key.

- `region_name`: The AWS region for the bucket. Defaults to "us-east-1" if not specified.

- `bucket`: the bucket in AWS to sync from/to.

- `path`: the path in AWS to sync from/to.

- `options`: A list of options for the `aws s3` command. See [the aws s3 sync command documentation](http://docs.aws.amazon.com/cli/latest/reference/s3/sync.html) for more information on supported options.

If `aws_access_key_id` and `aws_secret_access_key` are both absent, AWS CLI will fall back to other authentication mechanisms. See [Configuration setting and precedence](http://docs.aws.amazon.com/cli/latest/userguide/cli-chap-getting-started.html#config-settings-and-precedence)

## Behaviour

### `check`: Check for latest modified file

Consider the most recent `LastModified` timestamp as the most recent version

#### Parameters

*None.*

### `in`: Sync the S3 content locally

TBD

#### Parameters
- `target`: The path, relative to the work directory, to sync with S3. If omitted, uses the work directory.

### `out`: Sync the local content to S3

TBD

#### Parameters

- `source`: The path to sync to S3, relative to the work directory. If omitted, uses the work directory.
