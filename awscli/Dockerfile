FROM python:alpine
RUN apk add --no-cache groff less mailcap curl
RUN pip install awscli
RUN curl -sS "https://s3.amazonaws.com/session-manager-downloads/plugin/latest/mac/sessionmanager-bundle.zip" -o "sessionmanager-bundle.zip" \
      && unzip sessionmanager-bundle.zip \
      && ./sessionmanager-bundle/install -i /usr/local/sessionmanagerplugin -b /usr/local/bin/session-manager-plugin \
      && rm -rf ./sessionmanager-bundle ./sessionmanager-bundle.zip
RUN apk del --purge curl
LABEL io.whalebrew.name aws
LABEL io.whalebrew.config.environment '["AWS_ACCESS_KEY_ID", "AWS_SECRET_ACCESS_KEY", "AWS_SESSION_TOKEN", "AWS_DEFAULT_REGION", "AWS_DEFAULT_PROFILE", "AWS_CONFIG_FILE"]'
LABEL io.whalebrew.config.volumes '["~/.aws:/.aws"]'
ENTRYPOINT ["aws"]
