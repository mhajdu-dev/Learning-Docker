FROM node:22-bookworm-slim

WORKDIR /src
COPY package*.json ./
ARG CLIENT_PORT
ENV PORT=${CLIENT_PORT}
EXPOSE ${CLIENT_PORT}

COPY ./ ./
RUN npm i
CMD ["npm", "run", "start"]