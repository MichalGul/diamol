FROM python:3.8

# create workdir in containter image and set it as current dir
WORKDIR /app

#copy all files in django project folder to workdir
COPY bookmarks .

# install libs in requirements
RUN pip install -r requirements.txt

# declares that container must have persistent volume mounted to /data -> sqllite3 database file in this dir
VOLUME /data

# collect and collect static files for wsgi server 
RUN python manage.py collectstatic 


CMD ["uwsgi", "bookmarks_uwsgi.ini"]
