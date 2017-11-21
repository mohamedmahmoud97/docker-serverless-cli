# svls/serverless

Docker image containing NodeJS, Serverless Framework and Yarn.

## Usage

```bash
# build image, tag image, push image, update git tag with latest serverless release (one-time task)
$ make release

# Run serverless deploy in the image.
$ docker run --rm -it -v $(PWD):/opt/app -v ~/.aws:/root/.aws -v ~/.ssh:/root/.ssh $(IMAGE_NAME) bash
bash-4.3# sls deploy
```

## Example

`example/apigw` is an example on how to use `amaysim/serverless`.

## Docker image

The Docker image has the following:

- Node 8.4 (Alpine): we leverage Babel to be compatible with AWS Lambda runtime
- [Serverless Framework](https://serverless.com)
- [yarn](https://github.com/yarnpkg/yarn)
- zip: handy to zip your own serverless artefact
- [AWS CLI](https://github.com/aws/aws-cli): required by some Serverless plug-ins to work
