FROM node:13 AS build
WORKDIR /build

COPY . .

RUN npm install
# RUN npm install -g webpack
# RUN npm install -g webpack-cli
RUN npx webpack --mode="production"

FROM nginx:1.29
WORKDIR /app

COPY --from=build /build/dist /app/dist
COPY --from=build /build/html /app/html
COPY --from=build /build/css /app/css
COPY --from=build /build/nginx.conf.template /etc/nginx/templates/e2e-site.conf.template