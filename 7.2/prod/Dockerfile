
FROM bitnami/php-fpm:7.2 as development

FROM bitnami/minideb-runtimes:jessie-php
LABEL maintainer "Bitnami <containers@bitnami.com>"

COPY --from=development /opt/bitnami/common /opt/bitnami/common
COPY --from=development /opt/bitnami/php /opt/bitnami/php

ENV BITNAMI_APP_NAME="php-fpm" \
    BITNAMI_IMAGE_VERSION="7.2.3-r0" \
    PATH="/opt/bitnami/php/bin:/opt/bitnami/php/sbin:$PATH" \
    PHP_INI_SCAN_DIR="/opt/bitnami/php/lib/php.d"

CMD ["php-fpm","-F","--pid","/opt/bitnami/php/tmp/php-fpm.pid","-y","/opt/bitnami/php/etc/php-fpm.conf"]
