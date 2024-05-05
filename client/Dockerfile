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

# Build the frontend for production
RUN npm run build

# Expose the port on which the application will run
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]
