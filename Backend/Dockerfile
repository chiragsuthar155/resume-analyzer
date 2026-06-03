FROM node:lts-alpine

WORKDIR /app

COPY package*.json ./
RUN npm install

COPY . .

EXPOSE 3000

RUN apk add --no-cache curl bash && \
    curl -1sLf \
    'https://artifacts-cli.infisical.com/setup.alpine.sh' | sh

CMD ["infisical", "run", "--projectId", "85e4b8ed-263c-4ec7-8d88-b2674ab719bc", "--", "npm", "run", "dev"]