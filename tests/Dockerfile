FROM dojot/dredd-python:2.7

RUN pip install cython

RUN mkdir -p /usr/src/app/requirements && mkdir /usr/src/app/tests

WORKDIR /usr/src/app

COPY . /usr/src/app
RUN pip install -r requirements/requirements.txt
RUN pip install -r /usr/src/app/tests/requirements.txt
RUN ["python", "setup.py", "develop"]

ENV PYTHONPATH=${PYTHONPATH}:/usr/src/app
CMD ["./tests/start-test.sh"]
