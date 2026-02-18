FROM node:20-alpine

RUN apk add --no-cache git python3 make g++ tini

WORKDIR /app

COPY . .

RUN corepack enable
RUN corepack prepare pnpm@9 --activate

ENV CI=true

RUN pnpm install
RUN pnpm build

EXPOSE 5678

CMD ["pnpm", "start"]
