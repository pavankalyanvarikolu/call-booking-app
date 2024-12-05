# FROM node:17.9.0-slim
# #LABEL maintainer="DeekshithSN"
# RUN useradd adminapi
# WORKDIR /app
# RUN chown adminapi /app /home
# COPY . .
# RUN npm install 
# EXPOSE 1004
# USER adminapi
# ENV MONGO_URL="mongodb+srv://pavanvarikolu:OD3QmKf8bb7AlVfZ@callbooking.x8z88.mongodb.net/?retryWrites=true&w=majority&appName=CallBooking"
# CMD ["npm","start"]

# Use the official Node.js slim image as the base image
FROM node:17.9.0-slim

# Create a non-root user for security
RUN useradd --create-home --shell /bin/bash adminapi

# Set the working directory
WORKDIR /app

# Change ownership of the application directory
RUN chown adminapi:adminapi /app

# Copy application files and set ownership
COPY --chown=adminapi:adminapi . .

# Install only production dependencies to reduce image size
RUN npm install --production

# Expose application port and MongoDB URI for monitoring and debugging
EXPOSE 1004
ENV MONGO_URL="mongodb+srv://pavanvarikolu:OD3QmKf8bb7AlVfZ@callbooking.x8z88.mongodb.net/?retryWrites=true&w=majority&appName=CallBooking"

# Switch to the non-root user
USER adminapi

# Start the application
CMD ["npm", "start"]
