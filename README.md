# Sandboxing AI coding agents with NVIDIA OpenShell

Materials for a hands-on workshop.

A coding agent can be redirected by instructions hidden in anything it reads, for example a web page, an installed dependency or a comment on an issue.
It acts with all the permissions of the user who started it.
You can't reliably prevent the agent from being tricked, but you can limit the damage it can cause.

In this workshop, you run an agent in an [OpenShell](https://docs.nvidia.com/openshell/latest/about/overview) sandbox.
At the end, the agent can work on your GitHub repository and reach its LLM provider.

## Contents

| # | Chapter | What you do |
| --- |---|---|
| 0 | [Prerequisites](chapters/00-prerequisites/README.md) | Prepare your computer before the workshop. |
| 1 | [Introduction](chapters/01-intro/README.md) | Learn the risks and the parts of OpenShell. |
| 2 | [Gateway and drivers](chapters/02-gateway-and-drivers/README.md) | Check the control plane and pin the Docker driver. |
| 3 | [Sandboxes](chapters/03-sandboxes/README.md) | Create sandboxes and manage their lifecycle. |
| 4 | [Custom base image](chapters/04-custom-base-image/README.md) | Build an image with tools and agents. |
| 5 | [Providers and profiles](chapters/05-providers-and-profiles/README.md) | Give access to a single repository without exposing your token. |
| 6 | [Custom policy](chapters/06-custom-policy/README.md) | Allow the agent to reach its LLM provider and save the policy. |

Each chapter explains the key concepts first, then guides you step by step.

## Start

Go to [Prerequisites](chapters/00-prerequisites/README.md).
