FROM node:12.14.1-stretch

LABEL image=codejamninja/nginx:latest \
  maintainer="Jam Risser <jam@codejam.ninja>" \
  base=ubuntu

COPY entrypoint.sh /usr/local/sbin/entrypoint
RUN chmod +x /usr/local/sbin/entrypoint

WORKDIR /opt/app

COPY package.json /opt/app/package.json
RUN npm install

EXPOSE 4000

ENV POSTGRES_DATABASE=data \
  POSTGRES_HOST=postgres \
  POSTGRES_PASSWORD=postgres \
  POSTGRES_PORT=5432 \
  POSTGRES_USERNAME=postgres

ENTRYPOINT ["/bin/sh", "/usr/local/sbin/entrypoint"]
