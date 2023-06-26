FROM alpine:latest

LABEL MAINTAINER = "Fedorov"


# 替换apk使用的源
COPY repositories /etc/apk/repositories

# Install required packages and remove the apt packages cache when done.
RUN apk update && apk add --no-cache --update-cache libuv\
    nodejs \
	gcc \
	make \
	g++ \
	npm

WORKDIR /workspaces/typescript_test

RUN npm install -g cnpm --registry=https://registry.npm.taobao.org
RUN cnpm install -g typescript

# EXPOSE 8888

CMD ["tsc", "--version"]