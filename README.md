s3cmd-signed-url
================

Create temporary signed urls for private S3 buckets.

This is a fork of https://github.com/hajoeichler/s3cmd-signed-url
with the following changes:

- no longer depends on s3cmd (uses openssl instead)
- adds "-p" for "path-based" naming instead of "virtual-host" naming
- sets the host base URL properly for non-AWS endpoints
- allows using a different s3cfg configuration file

#### Dependencies

The `s3cmd-signed-url` tool depends on the `openssl` command line tool.

#### Usage

    s3cmd-signed-url -b bucket -o object_uri [-c s3cfg] [-p] [-a access_key] [-s method] [-s seconds]

#### Options

    -b bucket_name: bucket name (example: my-bucket)
    -o object_uri: URI part of object in S3 bucket (example: somefolder/somefile.ext)
    -m http_method: HTTP method to sign - e.g. PUT (default GET)
    -a access_key: S3 Access Key (default ${S3_ACCESS_KEY})
    -s seconds: how long the signed url will be valid (default 3600)
    -p: use path style (e.g. https://example.com/bucket) for buckets instead of the default hosted style (e.g. https://bucket.example.com)
    -c configfile: which s3cfg configuration file to use
    -h: see this usage information
