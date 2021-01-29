# Use Python 3.9.1
FROM python:3.9.1-slim AS development

# Build arguments to set non-root user
ARG USER_ID=1000
ARG GROUP_ID=1000

# Environment variables to configure JupyterLab
ENV JUPYTER_HOST="0.0.0.0" \
    JUPYTER_PORT="8888" \
    JUPYTER_GROUP="jovyan" \
    JUPYTER_USER="jovyan" \
    JUPYTER_HOME_DIR="/home/jovyan" \
    JUPYTER_NB_DIR="/usr/src/notebooks"

# Work directory inside container
WORKDIR ${JUPYTER_NB_DIR}

# Install Debian Slim packages
ADD packages.txt .
RUN apt-get update -y -qq && xargs -ra packages.txt apt-get install -y -qq

# Install JupyterLab
RUN pip install jupyterlab

# Install Python packages
ADD requirements.txt .
RUN pip install -r requirements.txt

# Add all other files to the container
ADD . .

# Create non-root user jovyan and give appropriate permissions
RUN groupadd -g ${GROUP_ID} ${JUPYTER_GROUP} \
  && useradd -u ${USER_ID} -g ${JUPYTER_GROUP} ${JUPYTER_USER} \
  && mkdir ${JUPYTER_HOME_DIR} \
  && chown ${USER_ID}:${GROUP_ID} ${JUPYTER_HOME_DIR} ${JUPYTER_NB_DIR}

# Set non-root user jovyan to run JupyterLab
USER ${USER_ID}:${GROUP_ID}

# Expose JupyterLab to outside the container
EXPOSE ${JUPYTER_PORT}

# By default, execute JupyterLab
CMD jupyter notebook --ip ${JUPYTER_HOST} --port ${JUPYTER_PORT} --no-browser --notebook-dir ${JUPYTER_NB_DIR}
