FROM python:3.9

WORKDIR /app

COPY requirements/requirements.txt .

RUN pip install -r requirements.txt --no-cache-dir

COPY . .

COPY setup/entrypoint.sh .
RUN chmod +x ./entrypoint.sh

ENTRYPOINT ["/app/entrypoint.sh"]
CMD ["gunicorn", "--bind", "0.0.0.0:9000", "kittygram_backend.wsgi"]
