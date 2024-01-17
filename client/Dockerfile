FROM python:latest as builder

RUN  apt-get update && apt-get install -y python3-dev \
    && apt-get install -y python3-pip \
    && pip3 install --upgrade pip

WORKDIR /build
COPY ./requirements.txt .

RUN python3 -m venv /build/venv
RUN . /build/venv/bin/activate && \
    python3 -m ensurepip --upgrade && \
    python3 -m pip install -r /build/requirements.txt

# RUNTIME 
FROM python:latest as release

WORKDIR /usr/src/app

COPY --from=builder /build /build
COPY ./player.py .
COPY ./images/ ./images
RUN . /build/venv/bin/activate

CMD ["python", "./player.py", "172.17.0.1"]
