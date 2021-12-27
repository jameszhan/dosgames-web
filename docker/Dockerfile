FROM python:3-bullseye

LABEL maintainer="James Zhan <zhiqiangzhan@gmail.com>"

RUN adduser --ingroup users --shell /bin/bash --gecos 'User for managing of deployment' --home /app --uid 1000 --disabled-password --quiet deploy

USER deploy

WORKDIR /app

ENV PATH /app/.local/bin:$PATH

RUN /usr/local/bin/python -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple --upgrade pip

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

RUN /usr/local/bin/python -m pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -r requirements.txt

CMD ["uwsgi", "app.ini"]
