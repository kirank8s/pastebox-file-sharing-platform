FROM node:20-alpine AS dependencies

WORKDIR /app

COPY package*.json ./

RUN npm install --omit=dev


############### Production stage

FROM node:20-alpine AS production

WORKDIR /app

ENV NODE_ENV=production

COPY --from=dependencies /app/node_modules ./node_modules

COPY . . 

EXPOSE 6600

CMD ["npm", "start"]
