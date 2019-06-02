# Docker

## Docker Build

Usage

```
docker build [OPTIONS] PATH | URL | -
```

Example

```console
docker build -t <image_name> .
```

| Option      | Effect                                                |
| :---------- | :---------------------------------------------------- |
| --file , -f | Name of the Dockerfile (Default is ‘PATH/Dockerfile’) |
| --no-cache  | Do not use cache when building the image              |
| --tag , -t  | Name and optionally a tag in the ‘name:tag’ format    |

- [docker build | Docker Documentation](https://docs.docker.com/engine/reference/commandline/build/)

## Docker Run

Usage

```console
docker run [OPTIONS] IMAGE [COMMAND] [ARG...]
```

Example

```console
docker run -it --rm -p 3000:3000 <image_name>
```

Options

| Option             | Effect                                           |
| :----------------- | :----------------------------------------------- |
| --rm               | Automatically remove the container when it exits |
| --volume , -v      | Bind mount a volume                              |
| --workdir , -w     | Working directory inside the container           |
| --publish , -p     | Publish a container’s port(s) to the host        |
| --interactive , -i | Keep STDIN open even if not attached             |
| --tty , -t         | Allocate a pseudo-TTY                            |

- [docker run | Docker Documentation](https://docs.docker.com/engine/reference/commandline/run/)
- [docker run reference| Docker Documentation](https://docs.docker.com/engine/reference/run/)
