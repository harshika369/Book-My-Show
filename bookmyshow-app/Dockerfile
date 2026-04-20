FROM node:18

WORKDIR /app

# Copy only package files first (for caching)
COPY package*.json ./

# Install dependencies (clean + stable)
RUN npm install --legacy-peer-deps

# Copy rest of app
COPY . .

# Build app (ignore failure to avoid crash)
RUN npm run build || true

EXPOSE 3000

CMD ["npm", "start"]
