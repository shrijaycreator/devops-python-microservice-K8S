FROM python:3.7

RUN mkdir /home/app
WORKDIR /home/app
ADD . /home/app
EXPOSE 8080
RUN pip install requests


CMD ["python","/home/app/job2.py"]
