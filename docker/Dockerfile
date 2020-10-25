FROM python:3.8-alpine as base


FROM base as builder

WORKDIR /install

COPY requirements.txt /requirements.txt

RUN pip install --prefix=/install -r /requirements.txt


FROM base

LABEL maintainer="camelot58@gmail.com"

COPY --from=builder /install /usr/local

COPY server.py /opt/my_server/server.py

ENTRYPOINT ["python", "/opt/my_server/server.py"]

EXPOSE 8000