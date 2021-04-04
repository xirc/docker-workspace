# Docker Workspace

Workspaces using [Visual Studio Code Remote Development](https://code.visualstudio.com/docs/remote/remote-overview).  

Each workspace provides an environment for development.

## Using workspace in any directory

At first, you have to build a docker image that you want to use.
If you already have pushed the docker image into [DockerHub](https://hub.docker.com/), You can skip this step.

```bash
docker build -t scala-sandbox ws-sandbox-scala/.devcontainer
```

You can use the image in any directory like below.

```bash
docker run -it --rm --mount src="$(pwd)",target=/opt/workspace,type=bind -w /opt/workspace scala-sandbox
```

## Workspaces

### `ws-sbt-website`

A workspace for [sbt/website](https://github.com/sbt/website)

### `ws-sandbox-scala`

A workspace for `Scala` and `sbt`