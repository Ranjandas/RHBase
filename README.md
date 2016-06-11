# RHBase Docker Container

## Usage

Clone this repo and build docker image.

```
git clone https://github.com/Ranjandas/RHBase
cd RHBase
docker build -t rhbase .
```

Alternatively if you dont want to build you can pull the pre-built docker image

```
docker pull Ranjandas/RHBase
```

To run the image use docker run which will drop you to the R console.

```
docker run -it Ranjandas/RHBase
```
