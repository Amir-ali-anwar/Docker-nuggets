FROM node:20-alpine

# Create a non-root user
RUN addgroup app && adduser -S -G app app

# Set the user to 'app' and set working directory
USER app
WORKDIR /app

# Copy package files and install dependencies
COPY package*.json ./
USER root
RUN chown -R app:app .
USER app
RUN npm install

# Copy the application code
COPY . .

# Expose the specified port
EXPOSE 5173

# Define the default command to run the application
CMD ["npm", "run", "dev"]
