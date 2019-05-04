FROM ruby:2.6-alpine
RUN gem install roadworker
LABEL io.whalebrew.name roadwork
LABEL io.whalebrew.config.environment '["AWS_ACCESS_KEY_ID", "AWS_SECRET_ACCESS_KEY"]'
ENTRYPOINT ["roadwork"]
