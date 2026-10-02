FROM nvcr.io/nvidia/base/ubuntu:24.04

RUN apt-get update && apt-get install -y --no-install-recommends \
    ca-certificates curl git gh

RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.40.8/install.sh | bash \
    && . "$HOME/.nvm/nvm.sh" \
    && nvm install 24 \
    && ln -s "$NVM_DIR/versions/node/$(nvm version 24)/bin/"* /usr/local/bin/

RUN npm install -g --prefix /usr/local \
    @anthropic-ai/claude-code \
    @opencode/cli \
    @github/copilot
