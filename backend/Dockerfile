# Use a base image
FROM node:14-slim

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application files
COPY . .

# Expose the port on which the application will run
EXPOSE 5000

# Command to run the application
CMD ["node", "server.js"]
