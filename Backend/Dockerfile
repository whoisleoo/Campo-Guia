FROM node:22-slim

RUN apt-get update && apt-get install -y \
    poppler-utils \
    ghostscript \
    graphicsmagick \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /app

COPY package*.json ./
RUN npm ci --omit=dev

COPY . .

EXPOSE 8080

CMD ["node", "server.js"]
