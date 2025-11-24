FROM node:18-alpine  

WORKDIR /app  

# Copy package files  
COPY package.json yarn.lock ./  
RUN yarn install  

# Copy source  
COPY . .  

# Create .nuxt directory and fix permissions  
RUN mkdir -p /app/.nuxt /app/.output && \
    chown -R node:node /app && \
    chmod -R 755 /app  

USER node  

# Expose port 3000  
EXPOSE 3000  

# Start the application  
CMD ["yarn", "dev"]  
