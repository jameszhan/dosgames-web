

```bash
# pip3 install flask uwsgi
# pip3 freeze > requirements.txt
$ cd ..
$ docker build -t dosgames-web:0.0.1 --file docker/Dockerfile .
$ docker run --rm -it --entrypoint bash dosgames-web:0.0.1

$ docker run --rm -p 8080:8080 -v `pwd`/static/games/bin/:/app/static/games/bin/ --name dosgames dosgames-web:0.0.1
# docker exec -it dosgames bash
$ open http://localhost:8080

$ docker tag ess-base-builder:0.0.3 172.20.8.205:5000/ess-base-builder:0.0.3
$ docker push 172.20.8.205:5000/ess-base-builder:0.0.3
```



COPY . /code

WORKDIR /code

COPY app.py.example app.py

RUN pip install -i https://pypi.tuna.tsinghua.edu.cn/simple -U redis flask

CMD ["python", "app.py"]%




# Copy the current directory contents into the container at /app


# Install the dependencies

# run the command to start uWSGI
CMD ["uwsgi", "app.ini"]