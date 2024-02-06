FROM node:18 as build
# docker build -t home .
# docker run -p 6500:6000 -ti --rm --init home
# http://localhost:6500
WORKDIR /app
COPY package.json ./
RUN npm install
COPY index.js ./

FROM gcr.io/distroless/nodejs:18-arm64

COPY --from=build /app /
EXPOSE 6000
CMD ["index.js"]
