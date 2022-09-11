Source: https://stackoverflow.com/questions/39496564/docker-volume-custom-mount-point

```
docker volume create --driver local --opt type=none --opt device=<host location> --opt o=bind <volume_name>
```

For example, after created volume:
```
docker run --gpus all -it --rm --mount src=<volume_name>,target=/workspace nvcr.io/nvidia/tensorrt:22.08-py3
```
