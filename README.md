# Docker Workspace

Workspaces using [Visual Studio Code Remote Development](https://code.visualstudio.com/docs/remote/remote-overview).  
Of course, `Dockerfile` can be used by itself.

Each workspace provides an environment for development, but it does not contain a git repository clone. You should clone it by yourself :-)

## Using workspace in any directory

At first, you should build a docker image that you want to work into. If the docker image is already pushed into [DockerHub](https://hub.docker.com/), this step can be skipped.

```bash
docker build -t scala-sandbox ws-sandbox-scala/.devcontainer
```

You can use the image in any directory like below.

```bash
docker run -it --mount src="$(pwd)",target=/opt/workspace,type=bind -w /opt/workspace scala-sandbox
```

## OSS

### `ws-sbt-website`

This is a workspace for [sbt/website](https://github.com/sbt/website).

## Sandbox

### `ws-sandbox-scala`

This is a workspace for `Scala` & `sbt`.