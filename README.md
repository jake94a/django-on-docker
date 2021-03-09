adapted from [tutorial](https://testdriven.io/blog/dockerizing-django-with-postgres-gunicorn-and-nginx/)

- Django, postgresql, gunicorn, nginx, on docker
  - Django - a python web framework
  - PostgreSQL - database management
  - Gunicorn - WSGI server ("green unicorn") (Django uses WSGI spec)
  - NGINX - web server [adapted to Django](https://docs.nginx.com/nginx/admin-guide/web-server/app-gateway-uwsgi-django/)

(from entrypoint.sh)
To remove all data from db and re-execute post-synchronization handlers
Then re-run migrations
after docker containers have been spun up run:

- docker-compose exec web python manage.py flush --no-input
- docker-compose exec web python manage.py migrate
