# Use the official Node.js 20 Alpine image as the base image
FROM node:20-alpine

# Create a non-root user
RUN addgroup app && adduser -S -G app app

# Set the user to 'app' and set the working directory
USER app
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json .
RUN npm install

# Copy the application code
COPY --chown=app:app . .

# Expose the specified port
EXPOSE 5173

# Define the default command to run the application
CMD ["npm", "run", "dev"]
