# Build stage
FROM node:20-alpine AS build
WORKDIR /app
<<<<<<< HEAD
COPY backend/package*.json ./
RUN npm install
COPY backend/ ./
# Test
=======
COPY package*.json ./
RUN npm install
COPY . .
>>>>>>> 372958d (commit des dockerfiles)
RUN npm test -- --passWithNoTests

# Production stage
FROM node:20-alpine
WORKDIR /app
COPY --from=build /app/package*.json ./
RUN npm install --only=production
COPY --from=build /app/server.js ./
EXPOSE 3000
CMD ["npm", "start"]
