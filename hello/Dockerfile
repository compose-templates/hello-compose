FROM node:18 as build
# docker build -t hello .
# docker run -p 6100:6000 -ti --rm --init hello
# http://localhost:6100
WORKDIR /app
COPY package.json ./
RUN npm install
COPY index.js ./

FROM gcr.io/distroless/nodejs:18-arm64

COPY --from=build /app /
EXPOSE 6000
CMD ["index.js"]
