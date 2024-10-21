# Optimize Layer Caching 

# FROM node:20.18.0-alpine3.20
# EXPOSE 8080
# ENV DB_HOST="mysql"
# RUN addgroup -S expense && adduser -S expense -G expense 
# RUN mkdir /opt/server
# RUN chown -R expense:expense /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# USER expense
# CMD ["node", "index.js"]

# FROM node:20.18.0-alpine3.20
# EXPOSE 8080
# ENV DB_HOST="mysql"
# RUN addgroup -S expense && adduser -S expense -G expense 
# RUN mkdir /opt/server
# RUN chown -R expense:expense /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# USER expense
# EXPOSE 8081 
# RUN echo "hello world"
# RUN echo "hello docker" 
# CMD ["node", "index.js"]

# FROM node:20.18.0-alpine3.20
# EXPOSE 8080
# ENV DB_HOST="mysql"
# RUN addgroup -S expense && adduser -S expense -G expense &&  \
# 	mkdir /opt/server && \
# 	chown -R expense:expense /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# USER expense
# CMD ["node", "index.js"]

# Multi stage builds

FROM node:20 AS builder
WORKDIR /opt/server
COPY package.json .
COPY *.js .
RUN npm install

FROM node:20.18.0-alpine3.20
EXPOSE 8080
ENV DB_HOST="mysql"
RUN addgroup -S expense && adduser -S expense -G expense &&  \
	mkdir /opt/server && \
	chown -R expense:expense /opt/server
WORKDIR /opt/server
COPY --from=builder /opt/server /opt/server
USER expense 
CMD ["node", "index.js"]

#  Run as Non-Root User 

# FROM node:20.18.0-alpine3.20
# EXPOSE 8080
# ENV DB_HOST="mysql"
# RUN addgroup -S expense && adduser -S expense -G expense 
# RUN mkdir /opt/server
# RUN chown -R expense:expense /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# USER expense
# CMD ["node", "index.js"]


# Use Official and Verified Images

# FROM node:20.18.0-alpine3.20
# EXPOSE 8080
# ENV DB_HOST="mysql"
# RUN mkdir /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# CMD ["node", "index.js"]



# Before best practice implemented 

# FROM node:20
# EXPOSE 8080
# ENV DB_HOST="mysql"
# # ENV DB_HOST="localhost"
# RUN mkdir /opt/server
# WORKDIR /opt/server
# COPY package.json .
# COPY *.js .
# RUN npm install
# CMD ["node", "index.js"]