# Use an official Node runtime as a parent image
FROM node:16

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json to install dependencies
COPY package*.json ./

# Install app dependencies
RUN npm install

# Copy the current directory contents into the container
COPY . .

# Expose port 3000 for the development server
EXPOSE 3000

# Start the React development server
CMD ["npm", "start"]
