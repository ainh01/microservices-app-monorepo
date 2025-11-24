# Use a lightweight Node.js 18 image as the base
FROM node:18-alpine  

WORKDIR /app  

# Copy package files  
COPY package.json yarn.lock ./  
RUN yarn install  

# Copy source  
COPY . .  

# Fix permissions - run as node user  
RUN chown -R node:node /app  

USER node  
# Expose port 3000 (Adjust this if your app runs on a different port, e.g., 5173 for Vite)
EXPOSE 3000

# Start the application
CMD ["yarn", "dev"]
