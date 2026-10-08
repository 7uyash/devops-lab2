FROM python:3.12-alpine

ARG APP_VERSION=1.0
ENV APP_VERSION=${APP_VERSION} \
    PYTHONUNBUFFERED=1

WORKDIR /app
COPY app.py .

RUN adduser -D appuser
USER appuser

EXPOSE 8080
HEALTHCHECK CMD wget -qO- http://localhost:8080/health || exit 1

CMD ["python", "app.py"]
