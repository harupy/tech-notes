# Docker

## docker build

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

## docker run

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

## docker compose

Usage

```console
docker-compose [-f <arg>...] [options] [COMMAND] [ARGS...]
```

Example

```console
docker run -it --rm -p 3000:3000 <image_name>
```

Options

| Option                  | Effect                                                          |
| :---------------------- | :-------------------------------------------------------------- |
| -f, --file FILE         | Specify an alternate compose file (default: docker-compose.yml) |
| -p, --project-name NAME | Specify an alternate project name (default: directory name)     |

Commands

| Command | Action                      |
| :------ | :-------------------------- |
| build   | Build or rebuild services   |
| up      | Create and start containers |

`docker-compose up` options

| Option       | Effect                                                                     |
| :----------- | :------------------------------------------------------------------------- |
| -d, --detach | Detached mode: Run containers in the background, print new container names |

[Overview of docker-compose CLI | Docker Documentation](https://docs.docker.com/compose/reference/overview/)

## Dockerfile

Example

```
FROM ubuntu:18.04
COPY . /app
RUN make /app
CMD python /app/app.py
```

Each instruction creates one layer:

- `FROM` creates a layer from the `ubuntu:18.04` Docker image.
- `COPY` adds file from your Docker client's current directory.
- `RUN` builds your application with `make`.
- `CMD` specifies what command to run within the container.

### RUN

```
# shell form, the command is run in a shell
# which by default is /bin/sh -c on Linux or cmd /S /C on Window
RUN <command>

# exec form
RUN ["executable", "param1", "param2"]
```

### CMD

```
# exec form, this is the preferred form
CMD ["executable","param1","param2"]

# as default parameters to ENTRYPOINT
CMD ["param1","param2"]

CMD command param1 param2` (shell form)
```

<span style="color: red">There can only be one CMD instruction in a Dockerfile.</span> If you list more than one CMD then only the last CMD will take effect.

[| Docker Documentation](https://docs.docker.com/engine/reference/builder/)

### EXPOSE

```
EXPOSE <port> [<port>/<protocol>...]
```

The `EXPOSE` instruction informs Docker that the container listens on the specified network ports at runtime.

Regardless of the `EXPOSE`, you can override them at runtime by using the `-p` flag. For example:

```console
docker run -p 80:80 ...
```

### COPY

```
COPY [--chown=<user>:<group>] <src>... <dest>

# this form is required for paths containing whitespace
COPY [--chown=<user>:<group>] ["<src>",... "<dest>"]
```

The `COPY` instruction copies new files or directories from `<src>` and adds them to the filesystem of the container at the path `<dest>`

### WORKDIR

```
WORKDIR /path/to/workdir
```

The `WORKDIR` instruction sets the working director for any `RUN`, `CMD`, `ENTRYPOINT`, `COPY` and `ADD` instructions that follow in the `Dockerfile`. If the `WORKDIR` doesn't exist, <span style="color: red">it will be created even if it's not used in any subsequent</span> `Dockerfile` instruction.

The WORKDIR instruction can be used multiple times in a Dockerfile. If a relative path is provided, it will be relative to the path of the previous WORKDIR instruction. For example:

```
WORKDIR /a
WORKDIR b
WORKDIR c
RUN pwd
```

The output of the final `pwd` command in this Dockerfile would be `/a/b/c`.

### ENV

```
# set a single variable
ENV <key> <value>

# set multiple variables
ENV <key>=<value> ...
```

The `ENV` instruction sets the environment variable `<key>` to the value `<value>`. This value will be in the environment for all subsequent instructions in the build stage and can be replaced inline in many as well.
