# Use a slim version of the Node.js image as the base
FROM node:14-slim

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to the working directory
COPY package*.json ./

# Install npm dependencies
RUN npm install 

# Copy only necessary files for the application
COPY . .


# Expose the port the app runs on
EXPOSE 3000

# Define the command to run the app
CMD ["npm", "start"]
