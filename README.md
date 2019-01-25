# ad2dispatch

A web-based platform for managing and operating drunk driving reduction programs.

## Development Setup

### Setup mysql docker container

```bash
$ docker build . -t ad2dispatch_db:latest
$ docker run --rm -d -v $(pwd)/mysql:/var/lib/mysql -p 127.0.0.1:3306:3306 ad2dispatch_db # May take a minute to init container after creation
```

### Setup the django environment

```bash
$ pip3 install --user virtualenv 
$ virtualenv venv 
$ source venv/bin/activate

(venv) $ source env_setup.py && cd ad2dispatch
(venv) $ python manage.py migrate # create database schema for app
(venv) $ python manage.py loaddata seed # seed the database with basic data
(venv) $ python manage.py runserver
# open browser and go to localhost:8000
```

## License

[Licensed Under Apache 2.0](https://www.apache.org/licenses/LICENSE-2.0)
