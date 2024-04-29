# # Use a slim version of the Node.js image as the base
# FROM node:14-slim

# # Set the working directory in the container
# WORKDIR /app

# # Copy package.json and package-lock.json to the working directory
# COPY package*.json ./

# # Install npm dependencies
# RUN npm install 

# # Copy only necessary files for the application
# COPY src/ ./src

# # Build the frontend for production
# RUN npm run build

# # Expose the port the app runs on
# EXPOSE 3000

# # Serve the production build
# CMD ["npm", "run", "start"]
# Use a base image
FROM node:14-slim

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install dependencies
RUN npm install

#Build server for production
RUN npm build
# Copy the rest of the application files
COPY . .

# Expose the port on which the application will run
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]
