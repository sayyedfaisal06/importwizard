FROM node:16 as build
WORKDIR /app
COPY package*.json ./
RUN npm install
COPY . .
RUN npm install playwright
ENV PLAYWRIGHT_BROWSERS none
RUN apt-get update && \
    apt-get install -y \
        libnss3 \
        libxkbcommon-x11-0 \
        libgbm1 \
        libgtk-3-0 \
        libx11-xcb1 \
        libdrm2 \
        libxcomposite1 \
        libxcursor1 \
        libxi6 \
        libxtst6 \
        libnotify4 \
        libasound2 \
        libatk1.0-0 \
        libatk-bridge2.0-0 \
        libpangocairo-1.0-0 \
        libjpeg62-turbo \
        fonts-noto-color-emoji  
COPY . .
RUN npm run testcase