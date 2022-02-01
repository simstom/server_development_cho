curl -fsSL https://get.docker.com/ | sudo sh
sudo usermod -aG docker $USER # 현재 접속중인 사용자에게 권한주기

mkdir docker-server

# requirements.txt
asgiref==3.2.7
Django==3.0.5
pytz==2019.3
sqlparse==0.3.1
uwsgi


docker build -t server_dev/django .

docker run -p 8000:8000  server_dev/django​

# ~/docker-server/nginx/nginx.conf

# ~/docker-server/nginx/nginx-app.conf

# ~/docker_server/nginx/Dockerfile

docker build -t server_dev/nginx .

docker run -p 80:80 server_dev/nginx​

# docker-compose.yml

docker-compose up -d --build