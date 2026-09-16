# Microsoft's devcontainer base: ships a non-root `vscode` user, git, and the
# tooling GitHub Codespaces expects. Rolling our own from python:slim means
# recreating all of that by hand, and getting it subtly wrong.
FROM mcr.microsoft.com/devcontainers/python:1-3.12-bookworm

COPY requirements.txt /tmp/requirements.txt

# Baked into the image rather than run via postCreateCommand: container start-up
# stays fast and works offline. Rebuild if requirements.txt changes.
RUN pip install --no-cache-dir --upgrade pip \
 && pip install --no-cache-dir -r /tmp/requirements.txt
