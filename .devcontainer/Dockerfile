# See here for image contents: https://github.com/microsoft/vscode-dev-containers/tree/v0.245.2/containers/python-3-anaconda/.devcontainer/base.Dockerfile

FROM olwimo/datascience-notebook:latest

# [Choice] Node.js version: none, lts/*, 16, 14, 12, 10
ARG NODE_VERSION="none"
USER jovyan
RUN if [ "${NODE_VERSION}" != "none" ]; then curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash && export NVM_DIR="$HOME/.nvm" && . "$NVM_DIR/nvm.sh" && nvm install ${NODE_VERSION} 2>&1; fi
# RUN if [ "${NODE_VERSION}" != "none" ]; then su jovyan -c "umask 0002 && . /usr/local/share/nvm/nvm.sh && nvm install ${NODE_VERSION} 2>&1"; fi

# Copy environment.yml (if found) to a temp location so we update the environment. Also
# copy "noop.txt" so the COPY instruction does not fail if no environment.yml exists.
# COPY environment.yml* .devcontainer/noop.txt /tmp/conda-tmp/
# RUN if [ -f "/tmp/conda-tmp/environment.yml" ]; then umask 0002 && /opt/conda/bin/conda env update -n base -f /tmp/conda-tmp/environment.yml; fi \
#     && rm -rf /tmp/conda-tmp

# [Optional] Uncomment this section to install additional OS packages.
# RUN apt-get update && export DEBIAN_FRONTEND=noninteractive \
#     && apt-get -y install --no-install-recommends <your-package-list-here>
