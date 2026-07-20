#FROM node:20
# IC-1
FROM node:20.18.3-alpine3.21
# On top of IC-1 instruction-2 is executed, and save this layer 2 image. IC-1 is removed
RUN addgroup -S expense && adduser -S expense -G expense && \
# create IC-2, on top of ic-2 instraction-3 is execucted and save this as layer3 image. IC-2 is removed 
    mkdir /opt/backend && \
    chown -R expense:expense /opt/backend
WORKDIR /opt/backend
COPY package.json ./
COPY *.js ./
RUN npm install
ENV DB_HOST="mysql"
#ENV DB_HOST="localhost"
USER expense
CMD ["node", "index.js"]