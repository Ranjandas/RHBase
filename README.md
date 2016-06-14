# RHBase Docker Container

## Usage

Clone this repo and build docker image.

The directory layout is based on Thrift version packaged inside the image.

This will be fixed soon.

```
git clone https://github.com/Ranjandas/RHBase
cd RHBase/<thrift-version>
docker build -t rhbase:<thrift-version> .
```

Alternatively if you dont want to build you can pull the pre-built docker image

```
docker pull ranjandas/rhbase
```

To run the image use docker run which will drop you to the R console.

```
docker run -it ranjandas/rhbase
```
