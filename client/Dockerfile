FROM frolvlad/alpine-glibc:alpine-3.9

RUN apk add --no-cache nfs-utils rpcbind bash tini

ENV NFS_SERVER=server \
  NFS_SERVER_DIRS='/nfs/share' \
  NFS_CLIENT_DIRS='/mnt/share'

COPY docker-entrypoint.sh /docker-entrypoint.sh

ENTRYPOINT ["tini", "--", "/docker-entrypoint.sh"]
