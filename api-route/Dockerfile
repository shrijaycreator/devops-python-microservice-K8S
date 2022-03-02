FROM python:3.7

RUN mkdir /home/app
WORKDIR /home/app
ADD . /home/app
EXPOSE 8080

RUN pip install flask
RUN pip install flask_restful

CMD ["python","/home/app/api-route.py"]

