FROM python:3-bullseye

MAINTAINER James Zhan <zhiqiangzhan@gmail.com>

WORKDIR /app

RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade pip

ADD docker/requirements.txt /app
ADD docker/app.ini /app
ADD static/css /app/static/css
ADD static/js /app/static/js
ADD static/games/img /app/static/games/img
ADD static/emularity /app/static/emularity
ADD templates /app/templates
ADD app.py /app
ADD game_infos.py /app
ADD games.json /app

RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirements.txt

CMD ["uwsgi", "app.ini"]
