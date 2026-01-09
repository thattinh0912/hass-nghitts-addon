FROM python:3.10-slim

WORKDIR /app

RUN apt-get update && apt-get install -y \
    git \
    ffmpeg \
    sox \
    && rm -rf /var/lib/apt/lists/*

RUN git clone https://github.com/nghimestudio/nghitts .

RUN pip install --no-cache-dir -r requirements.txt

COPY run.sh /run.sh
RUN chmod +x /run.sh

EXPOSE 5000
CMD ["/run.sh"]
