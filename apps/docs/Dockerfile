# Set the value from --build-arg during docker build
ARG TURBO_TEAM

# Set the value from --build-arg during docker build
ARG TURBO_TOKEN

FROM node:18-alpine AS base

# Stage: Prune the codes except the docs workspace 
FROM base AS builder

WORKDIR /app

RUN npm install --global turbo

COPY . .

RUN turbo prune docs --docker

# Stage: Install the docs dependencies workspace & running the apps
FROM base AS installer

ARG TURBO_TEAM
ENV TURBO_TEAM=$TURBO_TEAM

ARG TURBO_TOKEN
ENV TURBO_TOKEN=$TURBO_TOKEN

EXPOSE 3000

WORKDIR /app

RUN npm install --global pnpm

## Install the dependencies
COPY --from=builder /app/out/json/ .
RUN pnpm install

COPY --from=builder /app/out/full/ .

## Build the project
RUN pnpm build

WORKDIR /app/apps/docs

CMD ["pnpm", "run", "start"]
