release: python manage.py migrate
web: daphne channels_celery_heroku_project.asgi:application --port $PORT --bind 0.0.0.0 -v2
celery: celery -A channels_celery_heroku_project.celery worker -l info
celerybeat: celery -A channels_celery_heroku_project beat -l INFO 
celeryworker2: celery -A channels_celery_heroku_project.celery worker & celery -A channels_celery_heroku_project beat -l INFO & wait -n