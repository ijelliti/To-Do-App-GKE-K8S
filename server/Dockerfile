FROM node:14 AS build-env
ADD . /app
WORKDIR /app
RUN npm ci --only=production

FROM gcr.io/distroless/nodejs:14
COPY --from=build-env /app /app
WORKDIR /app
EXPOSE 5000
CMD ["app_hooked.js"]