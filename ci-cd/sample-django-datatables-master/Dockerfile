FROM python:3.14.0a4-alpine3.21

ENV PYTHONUNBUFFERED=1
ENV PYTHONDONTWRITEBYTECODE=1

COPY . .
RUN pip3 install --upgrade pip && pip3 install --no-cache-dir -r requirements.txt
RUN python manage.py makemigrations && python manage.py migrate
EXPOSE 5005
CMD ["gunicorn", "--config", "gunicorn-cfg.py", "core.wsgi"]