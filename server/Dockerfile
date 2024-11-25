FROM node:18-alpine

WORKDIR /app

# Install dependencies
COPY package*.json ./
RUN npm ci

# Copy source files
COPY . .

# Generate Prisma client and build
RUN npx prisma generate
RUN npm run build

# Expose port
EXPOSE 3001

# Start application
CMD ["npm", "start"]