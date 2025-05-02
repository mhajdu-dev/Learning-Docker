FROM node:22-bookworm-slim as base

WORKDIR /src
COPY package*.json ./
ARG API_PORT
ENV PORT=${API_PORT}
EXPOSE ${API_PORT}

FROM base as production
ENV NODE_ENV=production
RUN npm ci
COPY ./ ./
CMD ["node", "app"]

FROM base as dev
ENV NODE_ENV=development

# Add this line to install curl
RUN apt-get update && apt-get install -y curl && rm -rf /var/lib/apt/lists/*


RUN npm install -g nodemon && npm install
COPY ./ ./
CMD ["nodemon", "app"]