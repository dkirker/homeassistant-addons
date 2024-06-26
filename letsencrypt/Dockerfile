ARG BUILD_FROM
FROM $BUILD_FROM

# setup base
ARG \
    BUILD_ARCH \
    CRYPTOGRAPHY_VERSION \
    CERTBOT_VERSION \
    CERTBOT_DNS_AZURE_VERSION \
    CERTBOT_DNS_CLOUDNS_VERSION \
    CERTBOT_DNS_DESEC_VERSION \
    CERTBOT_DNS_DIRECTADMIN_VERSION \
    CERTBOT_DNS_DREAMHOST_VERSION \
    CERTBOT_DNS_DUCKDNS_VERSION \
    CERTBOT_DNS_DYNU_VERSION \
    CERTBOT_DNS_EASYDNS_VERSION \
    CERTBOT_DNS_GOOGLE_DOMAINS_VERSION \
    CERTBOT_DNS_HE_VERSION \
    CERTBOT_DNS_HETZNER_VERSION \
    CERTBOT_DNS_INFOMANIAK_VERSION \
    CERTBOT_DNS_INWX_VERSION \
    CERTBOT_DNS_JOKER_VERSION \
    CERTBOT_DNS_MULTI_VERSION \
    CERTBOT_DNS_NAMECHEAP_VERSION \
    CERTBOT_DNS_TRANSIP_VERSION \
    CERTBOT_DNS_PORKBUN_VERSION \
    CERTBOT_DNS_WEBSUPPORT_VERSION \
    CERTBOT_NETCUP_VERSION \
    CERTBOT_NJALLA_VERSION \
    CERTBOT_GANDI_VERSION \
    CERTBOT_DNS_DOMAINOFFENSIVE_VERSION \
    ACME_VERSION

RUN \
    set -x \
    && apk add --no-cache --update \
        libffi \
        musl \
        openssl \
        lego \
   && apk add --no-cache --virtual .build-dependencies \
        build-base \
        libffi-dev \
        musl-dev \
        openssl-dev \
        cargo \
        go \
    && pip install --no-cache-dir \
        cryptography==${CRYPTOGRAPHY_VERSION} \
        certbot==${CERTBOT_VERSION} \
        certbot-dns-multi==${CERTBOT_DNS_MULTI_VERSION} \
        acme==${ACME_VERSION} \
    && apk del .build-dependencies

# Copy data
COPY rootfs /
