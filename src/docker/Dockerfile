# Vulnerable Dockerfile with 2 key security issues
FROM python:3.12-slim
COPY app/ /app/
WORKDIR /app
RUN pip install flask requests

RUN useradd -m -u 1000 appuser && \
    chown -R appuser:appuser /app
USER appuser

EXPOSE 5000

HEALTHCHECK CMD curl --fail http://localhost:5000/health || exit 1

CMD ["python", "main.py"]
