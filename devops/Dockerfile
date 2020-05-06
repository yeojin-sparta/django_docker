FROM        python:3.8.2-slim

EXPOSE      8000
ENV         DJANGO_SETTINGS_MODULE=config.settings
ENV         PYTHONUNBUFFERED=1

RUN         mkdir /project
RUN         mkdir /project/app

WORKDIR     /project

# 소스 코드 이외 중요 설정 파일들은 도커파일에서 복사
COPY        ./requirements.txt  .
RUN         pip install -r ./requirements.txt

# uwsgi 패키지는 윈도우를 공식 지원하지 않으므로 도커 내에서 직접 설치
RUN         apt-get update
RUN         apt-get install gcc -y
RUN         pip install uwsgi

WORKDIR     /project/app
