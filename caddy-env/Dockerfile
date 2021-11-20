FROM caddy:alpine

RUN apk add tini

COPY --chmod=755 docker-entrypoint /

ENTRYPOINT ["tini", "/docker-entrypoint"]

CMD ["caddy"]
