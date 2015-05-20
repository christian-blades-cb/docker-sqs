# Fake SQS Docker Image #

Docker image for the [fake_sqs gem](https://github.com/iain/fake_sqs).

This image provides a fake sqs server on container port 4567.

## Usage ##

Ex:
```shell
$ docker run -p 4567:4567 --name fake_sqs christianbladescb/fake_sqs
$ curl -i http://$(docker-machine ip dev):$(docker port fake_sqs | cut -d':' -f2)/?Action=CreateQueue&QueueName=testQueue&Attribute.1.Name=VisibilityTimeout&Attribute.1.Value=40&Version=2012-11-05&Expires=2012-10-18T22%3A52%3A43PST
```
