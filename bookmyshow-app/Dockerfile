FROM node:18

WORKDIR /app

# Copy package files first
COPY package.json package-lock.json ./

# Clean install dependencies
RUN npm cache clean --force && \
    rm -rf node_modules package-lock.json && \
    npm install --legacy-peer-deps

# Copy full project
COPY . .

EXPOSE 3000

CMD ["npm", "start"]
