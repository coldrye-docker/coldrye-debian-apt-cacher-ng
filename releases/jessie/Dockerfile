FROM coldrye/debian-tini:0-9-0-jessie-latest

RUN set -ex \
    && export APT_LISTCHANGES_FRONTEND=none \
    && apt-get update \
    && apt-get -q -y -o Dpkg::Options::="--force-confdef" -o Dpkg::Options::="--force-confold" -t jessie-backports install apt-cacher-ng \
    && update-rc.d apt-cacher-ng disable \
    && sed 's/# ForeGround: 0/ForeGround: 1/' -i /etc/apt-cacher-ng/acng.conf \
    && ln -s /dev/stdout /var/log/apt-cacher-ng/apt-cacher.log \
    && ln -s /dev/stderr /var/log/apt-cacher-ng/apt-cacher.err \
    && apt-get clean \
    && rm -Rf /var/lib/apt/lists/* 2>/dev/null

VOLUME "/etc/apt-cacher-ng" "/var/cache/apt-cacher-ng"

EXPOSE 3142/tcp

CMD /usr/sbin/apt-cacher-ng -c /etc/apt-cacher-ng

