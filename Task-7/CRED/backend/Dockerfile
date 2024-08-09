# Use the latest Ubuntu image as the base
FROM ubuntu:latest

# Set author label
LABEL authors="amr"

# Install necessary packages
RUN apt-get update \
    && apt-get install -y curl \
    && apt-get -y autoclean

# Install nvm and Node.js
ENV NVM_DIR /usr/local/nvm
ENV NODE_VERSION 14.17.0

# Create NVM_DIR directory
RUN mkdir -p $NVM_DIR

# Install nvm with bash script and activate nvm
RUN curl -o- https://raw.githubusercontent.com/nvm-sh/nvm/v0.39.1/install.sh | bash \
    && . $NVM_DIR/nvm.sh \
    && nvm install $NODE_VERSION \
    && nvm alias default $NODE_VERSION \
    && nvm use $NODE_VERSION

# Set environment variables for Node.js
ENV NODE_PATH $NVM_DIR/versions/node/v$NODE_VERSION/lib/node_modules
ENV PATH $NVM_DIR/versions/node/v$NODE_VERSION/bin:$PATH

# Confirm installation by printing Node.js version
RUN node -v

# Copy the backend directory from the host to the image
COPY . /backend

# Set the working directory
WORKDIR /backend

# Command to run when the container starts
CMD ["npm", "start"]

# Expose port 5000
EXPOSE 5000
