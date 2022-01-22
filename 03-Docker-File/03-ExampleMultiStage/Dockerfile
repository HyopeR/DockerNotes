FROM python:3.9.6-alpine3 as base
FROM base as builder
RUN mkdir /install
WORKDIR /install
COPY requirements.txt /requirements.txt
RUN pip install --install-option="--prefix" -r /requirements.txt

FROM base
COPY --from=builder /install /usr/local
COPY src /app
WORKDIR /app
CMD ["gunicorn", "-w 4", "main:app"]
