FROM registry.gitlab.com/timvisee/send:latest

USER root

RUN apk add tini && \
  mkdir /uploads && \
  chown app:app /uploads

USER app

ENTRYPOINT ["tini"]

CMD ["node", "server/bin/prod.js"]
