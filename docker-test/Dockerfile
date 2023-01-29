FROM ubuntu:20.04

# build 즉 생성될 때 반영 => 이미지에 반영
RUN apt update && apt install -y python3

WORKDIR /var/www/html

COPY ["index.html", "."]

# 실행 될 때 반영 => 컨테이너에 반영
CMD ["python3", "-u", "-m", "http.server"]