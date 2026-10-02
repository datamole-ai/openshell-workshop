# Custom base image

## Goal

Build an image with the tools and agents you need, and create a sandbox from it.

## Official docs

- [Sandbox images](https://docs.nvidia.com/openshell/latest/how-it-works/sandboxes/overview#sandbox-images)

## Key concepts

### Sandbox image

A sandbox starts from an image, the same kind of image that Docker uses for containers.
The image defines the operating system, tools, libraries and configuration available in the sandbox.

The default image is a minimal Ubuntu.
It doesn't contain `git` or any agent.

### Custom image

You build a custom image with everything the agent needs.

You can use an image that you built locally or an image from a container registry.

## Instructions

### 1. Read the Dockerfile

The [Dockerfile](./Dockerfile) is a minimal example.
It builds the workshop image in three layers:
- System tools: `git`, `gh` (GitHub CLI), `curl` and CA certificates.
- Node.js 24, installed with nvm.
- Agent CLIs: Claude Code, OpenCode and GitHub Copilot.

The image is based on the default sandbox image, so the sandbox behaves the same as in the previous chapter.

### 2. Build the image

Build the image and tag it as `openshell-workshop`.
It takes a few minutes.

🖥️ Host

```shell
docker build -t openshell-workshop chapters/04-custom-base-image
```

Check that the image exists.

🖥️ Host

```shell
docker image ls openshell-workshop
```

> [!TIP]
> If the build fails, run it again with full output and without cache to see the error:
> ```shell
> docker build -t openshell-workshop --progress=plain --no-cache chapters/04-custom-base-image
> ```

### 3. Create a sandbox from the image

Create an ephemeral sandbox from the `openshell-workshop` image.

🖥️ Host

```shell
openshell sandbox create --no-keep --from openshell-workshop
```

> [!TIP]
> To use an image from a container registry, give its full reference (replace `<org>/<repo>` with actual values):
> ```shell
> openshell sandbox create --from ghcr.io/<org>/<repo>:latest
> ```

### 4. Check the tools

Check that the tools and agents from the image are available in the sandbox.

📦 Sandbox

```shell
which git gh claude opencode copilot
```

`which` prints a path for each tool.

Exit the sandbox.
OpenShell deletes it, because it is ephemeral.

📦 Sandbox

```shell
exit
```

## Target state

- [ ] The `openshell-workshop` image exists on your host.
- [ ] A sandbox created from it contains `git`, `gh`, `claude`, `opencode` and `copilot`.

## Next chapter

[Providers and profiles](../05-providers-and-profiles/README.md)
