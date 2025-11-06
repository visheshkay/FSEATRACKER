# Use Node.js 18 as the base image
FROM node:18

# Set working directory inside the container
WORKDIR /app

# Copy dependency files
COPY package*.json ./

# Install production dependencies
RUN npm ci --omit=dev

# Copy the rest of the app code
COPY . .

# Set environment variables
ENV PORT=4000 \
    DB_URL=mongodb://localhost:27017 \
    FILE_DB_URL=mongodb://localhost:27017/fseaFiledb \
    SECRET_KEY=vnrvjiet

# Expose the app port
EXPOSE 4000

# Start the app
CMD ["node", "server.js"]
