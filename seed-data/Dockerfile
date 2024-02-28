FROM python:3.11-rc-slim
WORKDIR /app
COPY . .
RUN apt-get update
RUN apt-get install --no-install-recommends -y apache2-utils
RUN python make-data.py
CMD sh generate-votes.sh
