FROM python:3
COPY ./requirements.txt /app/requirements.txt
RUN pip install --no-cache-dir --upgrade -r /app/requirements.txt
COPY ./src/.env /app/.env
COPY ./src/HelloWorldApp.py /app/HelloWorldApp.py