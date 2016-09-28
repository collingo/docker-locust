# docker-locust

Standing on the [shoulders of giants](https://github.com/hakobera/docker-locust)

## Example locustfile

Will hit the root of the site. Please see [http://docs.locust.io/en/latest/writing-a-locustfile.html](http://docs.locust.io/en/latest/writing-a-locustfile.html) for more on writing your own.

## Usage

1. Build the image

  `docker build -t locust-test .`

2. Run the tool

  `docker run --name locust -p 0.0.0.0:8089:8089 -e LOCUST_MODE=standalone -e TARGET_URL=http://www.address.com/ -v $(pwd)/test:/test locust-test`

  ... or for local apps running on the host ...

  `docker run --name locust -p 0.0.0.0:8089:8089 -e LOCUST_MODE=standalone -e TARGET_URL=http://[host-ip]:[port]/ -v $(pwd)/test:/test locust-test`

3. Trigger a test from the client

  [http://127.0.0.1:8089/](http://127.0.0.1:8089/)

## Shutdown

In another tab `docker rm -f locust`
