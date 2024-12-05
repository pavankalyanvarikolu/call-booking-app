

# FROM node:17.9.0-slim

# WORKDIR /app

# COPY . .

# RUN npm install

# CMD [ "npm", "start"]

# EXPOSE 3000

# Stage 1: Build Stage
FROM node:17.9.0-slim as builder

# Set the working directory in the container
WORKDIR /app

# Copy package.json and package-lock.json first (to cache dependencies)
COPY package*.json ./

# Install dependencies
RUN npm install

# Copy the rest of the application code
COPY . .

# Build the application if necessary (e.g., for React, Vue, etc.)
# Uncomment the following if applicable:
# RUN npm run build

# Stage 2: Production Stage
FROM node:17.9.0-slim

# Set the working directory in the production container
WORKDIR /app

# Copy only necessary files from the builder stage
COPY --from=builder /app .

# Install only production dependencies
RUN npm install --production

# Expose the application port
EXPOSE 3000

# Command to run the application
CMD ["npm", "start"]



