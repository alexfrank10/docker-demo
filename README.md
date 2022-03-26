cd /path/to/python-docker

pip3 install Flask

pip3 freeze | grep Flask >> requirements.txt

touch app.py

python -m flask run

touch Dockerfile

docker build --tag docker-python .

docker images

docker tag docker-python:latest docker-python:v1.0.0

docker rmi docker-python:v1.0.0