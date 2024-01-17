FROM python:latest as builder

RUN apt-get update && apt-get install -y \
    python3-dev \
    python3-pip \
    && apt-get clean \
    && rm -rf /var/lib/apt/lists/*

WORKDIR /build
COPY ./requirements.txt .

RUN pip3 install --upgrade pip \
    && pip3 install --no-cache-dir --prefix="/install" -r /build/requirements.txt

# RUNTIME 
FROM python:latest as release

WORKDIR /usr/src/app

COPY --from=builder /install /usr/local

COPY ./player.py .
COPY ./images/ ./images

CMD ["python", "./player.py", "172.17.0.1"]
