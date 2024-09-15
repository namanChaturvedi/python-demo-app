FROM python:3.9-slim-buster

LABEL Name="Python Demo App" Version=1.4.2

ARG srcDir=src
WORKDIR /app
COPY $srcDir/requirements.txt .
RUN pip install --no-cache-dir -r requirements.txt

COPY $srcDir/run.py .
COPY $srcDir/app ./app

EXPOSE 8000

CMD ["gunicorn", "-b", "0.0.0.0:8000", "run:app"]
