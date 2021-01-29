# Use Python 3.9.1
FROM python:3.9.1-slim AS development

# Build arguments to set non-root user
ARG USER_ID=1000
ARG GROUP_ID=1000

# Environment variables to configure Flask
ENV API_HOST="0.0.0.0" \
    API_PORT="5000" \
    API_GROUP="flask" \
    API_USER="flask" \
    API_DIR="/usr/src/api" \
    FLASK_ENV="development" \
    FLASK_APP="api.py"

# Work directory inside container
WORKDIR ${API_DIR}

# Install Debian Slim packages
ADD packages.txt .
RUN apt-get update -y -qq && xargs -ra packages.txt apt-get install -y -qq

# Install Python packages
ADD requirements.txt .
RUN pip install -r requirements.txt

# Add all other files to the container
ADD . .

# Create non-root user flask and give appropriate permissions
RUN groupadd -g ${GROUP_ID} ${API_GROUP} \
  && useradd -u ${USER_ID} -g ${API_GROUP} ${API_USER} \
  && chown ${USER_ID}:${GROUP_ID} ${API_DIR}

# Set non-root user flask to run Flask
USER ${USER_ID}:${GROUP_ID}

# Expose Flask to outside the container
EXPOSE ${API_PORT}

# By default, execute Flask
CMD flask run --host ${API_HOST} --port ${API_PORT}
