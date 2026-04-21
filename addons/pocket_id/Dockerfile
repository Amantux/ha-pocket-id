ARG BUILD_FROM
FROM ${BUILD_FROM}

ARG BUILD_ARCH
ARG POCKET_ID_VERSION=v2.6.0

# Download the correct Pocket ID binary for this architecture
RUN set -eux; \
    case "${BUILD_ARCH}" in \
        amd64)   POCKET_ARCH="linux-amd64"  ;; \
        aarch64) POCKET_ARCH="linux-arm64"  ;; \
        armv7)   POCKET_ARCH="linux-armv7"  ;; \
        *) echo "Unsupported arch: ${BUILD_ARCH}" && exit 1 ;; \
    esac; \
    wget -qO /usr/bin/pocket-id \
        "https://github.com/pocket-id/pocket-id/releases/download/${POCKET_ID_VERSION}/pocket-id-${POCKET_ARCH}"; \
    chmod +x /usr/bin/pocket-id

COPY rootfs /

RUN chmod a+x /etc/services.d/pocket_id/run

LABEL \
    io.hass.version="${POCKET_ID_VERSION}" \
    io.hass.type="addon" \
    io.hass.arch="amd64|aarch64|armv7"
